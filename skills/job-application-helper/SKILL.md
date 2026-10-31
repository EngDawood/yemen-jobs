---
name: job-application-helper
description: Help apply to a Yemen job found with the yemen-jobs tools. Use when the user wants to apply, tailor a CV or cover letter to a posted job, check fit, or find out how to apply ("كيف أقدم", "عدّل سيرتي لهذه الوظيفة").
---

# Job application helper

## Steps

1. Get the job with `get_job` (by id) or `get_job_by_number`. Read `how_to_apply`, `application_links`, `deadline`, and the description fields.
2. Tell the user how to apply exactly as the listing says. Quote the link or email from `application_links` or `how_to_apply`. Never guess an address.
3. If the user shares a CV, list: requirements they meet, gaps, and 3 to 5 concrete edits to make the CV fit the posting.
4. If asked, draft a short cover letter in the language of the posting. Use only facts from the user's CV and the listing.

## Rules

- Warn if the deadline has passed or is within 3 days.
- Never state salary, benefits or requirements that are not in the listing.
- Remind the user to verify the vacancy on the original source link before sending personal documents.
