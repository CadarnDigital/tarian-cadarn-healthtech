# Task: generate-m2m-report

## Objective
Generate a Markdown report listing all files that were skipped or could not be processed during the conversion. Includes recovery tracking for previously failed PDFs now processable via the CLI-agnostic extraction engine.

## Input
- `exceptions_list`: List of failed/ignored files (name, extension, path, reason).
- `recovery_list` (optional): List of previously failed files now successfully processed after engine change.

## Output
- `relatorio-nao-suportados.md` in the target directory.

## CLI-Agnostic Mandate

> **NON-NEGOTIABLE:** The M2M extraction engine has migrated from PowerShell/shell commands to native `Read` (read_file) for content extraction.
> - PDF and text content is extracted via `Read` (read_file) — NEVER via PowerShell (`Get-Content`), `cat`, or shell pipes.
> - File discovery uses `Glob` — NEVER `Get-ChildItem`, `find`, or `dir`.
> - Report generation uses `Write` — NEVER shell redirects or `Out-File`.
> - This change recovers previously failed PDFs that broke under PowerShell encoding issues.
> Cross-platform compatibility (Windows, macOS, Linux) is guaranteed without shell dependencies.

## Workflow
1. **Consolidation**: Gather all exception data from the previous ETL run.
2. **Recovery Check**: Compare current exceptions against previous run — identify files that were previously failed but are now successfully processed (recovered via read_file engine).
3. **Formatting**: Apply the `m2m-exception-report-tmpl.md` template.
4. **Recovery Section**: If `recovery_list` is non-empty, append a "Recovered Files" section listing files that previously failed under PowerShell but succeeded with native read_file.
5. **Writing**: Save the report to the root of the target directory using `Write`.
6. **Summary**: Display a brief summary of total processed vs skipped vs recovered files to the user.
