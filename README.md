# Yemen Jobs | وظائف اليمن

Search and track jobs in Yemen from Claude and ChatGPT. Live data from Yemen HR, EOI, ReliefWeb, UNjobnet, QTB Bank and YLDF, with Arabic summaries, updated hourly.

ابحث عن وظائف اليمن وتابع جديدها من داخل Claude وChatGPT. بيانات حيّة من Yemen HR وEOI وReliefWeb وUNjobnet وQTB Bank وYLDF، بملخصات عربية، تتحدث كل ساعة.

Telegram channel / قناة تلغرام: [@hr_yemen](https://t.me/hr_yemen)

## Sources / المصادر

| Source | Type | Update |
|---|---|---|
| Yemen HR (yemenhr.com) | Local job board | Hourly |
| EOI Yemen (eoi-ye.com) | NGO listings | Hourly |
| ReliefWeb (reliefweb.int) | Humanitarian jobs | Every 6 hours |
| UNjobnet | UN and international orgs | Every 6 hours |
| QTB Bank (jobs.qtbbank.com) | Banking | Daily |
| YLDF (erp.yldf.org) | Development foundation | Daily |
| RSS feeds | Catch-all | Hourly |

## Claude

```bash
/plugin marketplace add EngDawood/yemen-jobs
```

```bash
/plugin install yemen-jobs@yemen-jobs
```

Includes the MCP server and three skills:

- `search-yemen-jobs`: search by keyword, company or source.
- `daily-yemen-jobs`: daily digest of the newest jobs.
- `job-application-helper`: how to apply, CV and cover letter tailoring.

Example prompts / أمثلة:

- "Show me today's jobs in Sanaa" / "اعرض لي وظائف اليوم في صنعاء"
- "Find accountant jobs at NGOs" / "ابحث عن وظائف محاسب في المنظمات"
- "What are the latest ReliefWeb jobs for Yemen?"

## ChatGPT

See [chatgpt/README.md](chatgpt/README.md). Same MCP server, added as an app (connector).

## MCP server

`https://jobs.engdawood.com/mcp` (public, read-only, no token needed).
Tools: `get_latest_jobs`, `search_jobs`, `get_job`, `get_job_by_number`, `list_sources`, `get_stats`.

Privacy: https://jobs.engdawood.com/privacy · Terms: https://jobs.engdawood.com/terms
