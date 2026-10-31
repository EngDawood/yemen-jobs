---
name: daily-yemen-jobs
description: Give a daily digest of the newest jobs in Yemen. Use when the user asks for today's jobs, the latest vacancies, "وظائف اليوم", "آخر الوظائف", or wants a recurring daily job check.
---

# Daily Yemen jobs digest

Use the `yemen-jobs` MCP tools. Reply in the user's language.

## Steps

1. Call `get_latest_jobs` with `limit` 20.
2. Keep jobs whose `posted_date` is today or yesterday. If fewer than 5 remain, show the 10 latest instead and say so.
3. If the user gave a field or city (for example "accounting" or "Aden"), filter the results locally, or use `search_jobs` for it.
4. Group by `category` when present, otherwise by `source`.

## Output

One line per job: title, company, location, deadline, link. End with a one-line count, for example "12 new jobs from 4 sources".

Mention that the data refreshes hourly. To make this a daily routine, tell the user they can schedule this skill (for example with `/loop` or a scheduled task) and name no other mechanism.
