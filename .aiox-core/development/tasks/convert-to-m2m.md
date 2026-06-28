# Task: convert-to-m2m

## Objective
Convert raw files from a source directory into M2M (Machine-to-Machine) optimized Markdown files in a target directory.

## Guardrails
- **READ-ONLY SOURCE**: Never modify or delete files in the source path.
- **NO CONVERSATIONAL FILLER**: Output files must contain only extracted data.
- **M2M OPTIMIZATION**: Use structural tags (e.g., `<content>`, `<metadata>`) and remove visual noise.
- **FILE SIZE LIMIT**: Skip files > 50MB.

## Input
- `source_path`: Directory containing raw files.
- `target_path`: Directory where `.md` clones will be created.

## Workflow (CLI-Agnostic — v2.0)
1. **Validation**: Use `glob` to verify `source_path` exists. List supported files.
2. **Checkpoint Check**: Use `glob` on `target_path` to identify already-converted files. Read existing .md files to verify valid content (not placeholder). Create "Skip List".
3. **Scanning**: Use `glob("**/*.{pdf,docx,doc,txt,md,rtf,pptx,png,jpg}")` on `source_path`.
4. **Filtering**: Identify files to process vs. ignore based on extensions and size.
5. **Processing (CLI-Agnostic Cascade)**:
   For each valid file NOT in the Skip List:
   - **PRIMARY: Native `read_file`** — Read the file directly using the framework's native read_file tool. The LLM host handles PDF rendering, DOCX parsing, and image OCR natively. This recovers 100% of content that failed with PowerShell.
   - **For PDFs > 10 pages**: Use `read_file` with `pages` parameter to read in chunks (e.g., pages "1-10", "11-20").
   - **For images (PNG/JPG)**: `read_file` renders the image and the LLM performs visual OCR.
   - **SECONDARY: `grep_search`** — For very large text files, use grep_search to extract structured content.
   - **EXCEPTION**: If read_file returns empty or error, do NOT create a placeholder. Log as EXCEPTION.
   - Extract content and wrap in M2M structural tags.
   - Add YAML frontmatter with: source_path, converted_at, agent_id, extraction_quality (full|partial|failed).
6. **Exception Handling**: Record details for the exception report.
7. **Finalization**: Trigger `generate-m2m-report.md`.

## IMPORTANT: CLI-Agnostic Mandate
- **NEVER** use PowerShell (`Get-Content`, `iTextSharp`, `System.IO`).
- **NEVER** use bash commands (`cat`, `pdftotext`, `tesseract`).
- **ONLY** use native framework tools: `read_file`, `glob`, `grep_search`, `write_file`, `edit_file`.
- The intelligence of the LLM host (Claude, Gemini, etc.) handles all content understanding.

## Output
- `.md` files in `target_path`.
- In-memory list of exceptions.
