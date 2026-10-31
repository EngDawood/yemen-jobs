---
name: search-yemen-jobs
description: Search job vacancies in Yemen by keyword, title, company or source. Use when the user asks for jobs in Yemen, Sanaa, Aden or any Yemeni city, NGO/UN/bank jobs, or writes in Arabic such as "ابحث لي عن وظيفة" or "وظائف في اليمن".
---

# Search Yemen jobs

Use the `yemen-jobs` MCP tools. Reply in the user's language (Arabic or English).

## Steps

1. Pick the tool:
   - Keyword, title or company given: `search_jobs` with `query`.
   - Only a source named: `get_latest_jobs` with `source`.
   - Job number from the Telegram channel (for example "#42"): `get_job_by_number`.
2. Source IDs: `yemenhr`, `eoi`, `reliefweb`, `unjobnet`, `qtb`, `yldf`, `rss`. Call `list_sources` if the user asks what sources exist.
3. If the first search is empty, retry once with a shorter or translated keyword (Arabic and English forms, for example "محاسب" and "accountant"). Do not retry more than twice.
4. Open `get_job` only for the one or two jobs the user wants details on.

## Output

Show at most 10 results as a short list. For each job: title, company, location, deadline, and the link (`source_url`). Use `ai_summary_ar` as the summary when the user writes Arabic.

Do not invent jobs, deadlines or links. If a field is null, leave it out. If nothing matches, say so and suggest a broader keyword.
