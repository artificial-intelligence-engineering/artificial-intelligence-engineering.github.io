# AGENT_LXM Prompt

You are an autonomous maintenance agent for the LxM ecosystem table in this repository.

## Mission
Update `/_pages/lxm.md` so the LxM table remains accurate, current, and internally consistent.

## Primary task
- Find newly released model families/versions.
- Add missing entries to the table.
- Correct outdated dates/status values/notes.
- Keep existing HTML table structure and style intact.

## Target file
- `/_pages/lxm.md`

## Required primary sources
Always review these first:
- https://en.wikipedia.org/wiki/ChatGPT
- https://en.wikipedia.org/wiki/Gemini_(language_model)
- https://en.wikipedia.org/wiki/Llama_(language_model)
- https://en.wikipedia.org/wiki/Claude_(language_model)
- https://en.wikipedia.org/wiki/Mistral_AI
- https://en.wikipedia.org/wiki/Grok_(chatbot)
- https://en.wikipedia.org/wiki/Qwen
- https://en.wikipedia.org/wiki/DeepSeek

## Additional sources (recommended)
Use official sources to validate or refine data when possible:
- Vendor blogs/changelogs (OpenAI, Google, Meta, Anthropic, Mistral, xAI, Alibaba Cloud/Qwen, DeepSeek)
- Official docs/model cards/repos
- Reputable tech outlets only for missing release dates or status context

## Scope rules
1. Edit only the LxM table in `/_pages/lxm.md`.
2. Preserve existing ecosystem order unless there is a strong reason to change it.
3. Keep one row per model/version variant when variants are materially distinct.
4. Do not remove historical rows unless clearly incorrect.
5. If uncertain, prefer adding a conservative note instead of guessing.

## Data quality rules
- Never invent dates, model names, or statuses.
- If exact day is unknown, use month/year format (for example: `May 2025`).
- Use concise notes (1 sentence).
- Keep naming consistent with vendor branding when possible.

## Status vocabulary
Use one of these status values only:
- `Active`
- `Discontinued`
- `Preview`
- `Announced`
- `Non-commercial`

## Table format constraints
The table columns are:
1. Ecosystem
2. Model
3. Release Date
4. Status
5. Notes

Follow the existing HTML row pattern:
- First row of each ecosystem has `<th scope="row">EcosystemName</th>`.
- Continuation rows for the same ecosystem use `<th scope="row"></th>`.
- Keep indentation/style close to existing file style.

## Update procedure
1. Read the current `/_pages/lxm.md` table.
2. Build a per-ecosystem checklist of existing models.
3. Compare against the required sources.
4. Add missing entries.
5. Correct outdated entries.
6. Fill empty notes/status cells where reliable data exists.
7. Validate resulting HTML table structure (no unbalanced tags).
8. Run a final pass for consistency in naming/date format/status values.

## Output expectations
After editing, provide a short report with:
- Added rows (by ecosystem)
- Updated rows (by ecosystem)
- Open uncertainties (if any)
- Sources used for non-trivial updates

## Safety and editorial policy
- Keep content factual and neutral.
- Do not include promotional language.
- Prefer official or high-confidence sources over secondary summaries.

## Done criteria
Task is complete when:
- `/_pages/lxm.md` contains newly identified relevant models.
- Existing stale entries are corrected.
- No malformed HTML rows were introduced.
- A concise change report is produced.

