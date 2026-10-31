---
name: yemen-jobs
description: Yemen jobs, from search to application. Use for vacancies in Yemen, Sanaa or Aden (NGO, UN, bank), today's or latest jobs (وظائف اليوم), and applying or tailoring a CV to a posting (كيف أقدم).
---

# Yemen Jobs

Data comes from the `yemen-jobs` MCP tools and refreshes hourly. Answer in Arabic when the user writes Arabic, using `ai_summary_ar` for summaries.

## Reference

- Source IDs: `yemenhr`, `eoi`, `reliefweb`, `unjobnet`, `qtb`, `yldf`, `rss`. `list_sources` lists them with counts.
- Job fields used: `title`, `company`, `location`, `deadline`, `source_url`, `ai_summary_ar`, `category`, `posted_date`, `how_to_apply`, `application_links`.
- Null fields stay out of the answer. Every job, deadline and link shown comes from a tool result.

## Find

For a keyword, title, company, source or Telegram post number.

1. Call `search_jobs` with `query`; `get_latest_jobs` with `source` when only a source is named; `get_job_by_number` for a number like "#42".
2. On an empty result, retry with the other-language form ("محاسب" and "accountant"), at most twice.

Done when the user has up to 10 jobs, one line each (title, company, location, deadline, link), or a clear "no match" with one broader keyword to try.

## Digest

For today's or the latest jobs.

1. Call `get_latest_jobs` with `limit` 20.
2. Keep jobs posted today or yesterday. With fewer than 5, show the latest 10 and say so.
3. Group by `category`, falling back to `source`.

Done when every job is one line and the answer ends with a count such as "12 new jobs from 4 sources". For a daily routine, the user can schedule this with `/loop`.

## Apply

For how to apply, CV fit, or a cover letter.

1. Call `get_job` (or `get_job_by_number`) and read `how_to_apply`, `application_links` and `deadline`.
2. Quote the link or email exactly as the listing gives it.
3. With a CV: list requirements met, gaps, and 3 to 5 edits that fit the posting. Draft a cover letter on request, in the posting's language, from the CV and the listing only.

Done when the answer has the quoted application route, the deadline status (passed, within 3 days, or open), and a reminder to verify the vacancy on its `source_url` before sending personal documents.
