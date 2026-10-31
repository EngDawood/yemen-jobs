# ChatGPT app: Yemen Jobs

ChatGPT does not use a plugin file like Claude. It connects to a remote MCP server as an app (connector). The server already exists and is public:

| Field | Value |
|---|---|
| MCP server URL | `https://jobs.engdawood.com/mcp` |
| Auth | None (read-only public tools) |
| Privacy policy | https://jobs.engdawood.com/privacy |
| Terms of service | https://jobs.engdawood.com/terms |
| Domain verification | `https://jobs.engdawood.com/.well-known/openai-apps-challenge` (already served by the worker) |

All tools are read-only (`readOnlyHint: true`, `destructiveHint: false`, `openWorldHint: false`):
`get_latest_jobs`, `search_jobs`, `get_job`, `get_job_by_number`, `list_sources`, `get_stats`.

## Try it yourself (developer mode)

1. ChatGPT: Settings, Apps and Connectors, Advanced, enable Developer mode.
2. Create a connector, paste the MCP server URL above, set auth to none.
3. In a chat, enable the connector and run the test prompts below.

The exact menu names change often. If they differ, check OpenAI's current "Apps SDK" documentation.

## Listing text

Name: `Yemen Jobs | وظائف اليمن`

Description (350 chars max):

```
ابحث عن وظائف اليمن من داخل ChatGPT: وظائف صنعاء وعدن من Yemen HR وEOI وReliefWeb وUNjobnet وQTB Bank وYLDF، منظمات وأمم متحدة وبنوك، ملخصة بالعربية ومحدّثة كل ساعة. Search & track Yemen jobs in ChatGPT: Sanaa and Aden vacancies from Yemen HR, EOI, ReliefWeb, UNjobnet, QTB Bank and YLDF. NGO, UN, and bank jobs with Arabic summaries, updated hourly.
```

## Test prompts (should call the tool)

1. "What are the latest jobs in Yemen?"
2. "Find accountant jobs at NGOs in Sanaa."
3. "ابحث لي عن وظائف في عدن."
4. "Show me the newest ReliefWeb jobs for Yemen."
5. "Give me job #42 from the Telegram channel."
6. "How many jobs does each source have?"

## Prompts that should NOT call the tool

1. "Write me a cover letter template." (no job lookup needed)
2. "What is the weather in Sanaa?"
3. "Find jobs in Canada."

## Before submitting

- Confirm the server answers `tools/list` without a token (it does at the time of writing).
- Do not set `MCP_ADMIN_TOKEN` in any public connector config: it unlocks admin tools.
- Submission needs a verified OpenAI organization and an account with submit rights. I could not verify the current review requirements, so read OpenAI's current app submission guidelines first.
