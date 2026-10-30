# CertArc MCP server

CertArc is independent practice for the CISM, CISSP, CISA, AAISM and AAIA exams. This remote MCP server lets an AI assistant give a learner free CertArc practice questions. With the learner's sign-in, it also gives read-only access to their own CertArc study.

This repository holds no server code. It documents the hosted server and its MCP Registry entry ([`server.json`](server.json)).

- **Server URL:** `https://certarc.com/mcp/claude`
- **Transport:** Streamable HTTP
- **Registry name:** `com.certarc/certarc`
- **Website:** https://certarc.com

## Connect

| Assistant | How |
| --- | --- |
| ChatGPT | Add CertArc from its [ChatGPT listing](https://chatgpt.com/plugins/plugin_asdk_app_6ac10753370881918540799af4b9e5d7) |
| Claude | Add a custom connector with the URL `https://certarc.com/mcp/claude` |
| Other MCP clients | Add `https://certarc.com/mcp/claude` as a remote server. The free tools work without an account; see [Sign-in](#sign-in) |

Setup steps for each assistant are on [certarc.com/integrations](https://certarc.com/integrations).

## Tools

All 12 tools are read-only. None of them answers for the learner, finishes a session or changes a plan.

### Free, no account needed

| Tool | What it does |
| --- | --- |
| `practice_question` | Returns one scenario question from CertArc's free public practice set for a certification |
| `check_practice_answer` | After the learner chooses, returns whether the answer is correct, the correct option and CertArc's explanation for every option |
| `get_exam_domains` | Returns an exam's domains and their weights, with links to CertArc's public guides |
| `search_learning_resources` | Returns CertArc study-guide titles and links for a topic |

Ask the learner for an option and how sure they are (Confident, Unsure or Guess) before checking an answer. Never reveal an answer before they choose.

### The learner's own study (sign-in required)

| Tool | What it does |
| --- | --- |
| `open_study_panel` | Study overview: progress, saved schedule and next study option |
| `get_study_summary` | Sprint progress, target exam date and access status |
| `get_readiness` | Readiness Score, how it is built and how to raise it |
| `get_results` | Sprint, practice exam, baseline and final results |
| `get_result_review` | What happened in one sprint or exam: Incorrect answers, confidence, miss reasons and domains |
| `get_study_patterns` | Where confidence and results disagree, and the learner's miss reasons |
| `get_study_plan` | The study calendar, with each entry's date and status |
| `get_next_study_action` | The next eligible sprint in study order |

## Sign-in

The learner signs in to CertArc in their browser, with Google or a one-time code sent by email. The assistant never sees or enters the code. Assistants never create accounts.

Account sign-in currently works from ChatGPT and Claude. In other MCP clients only the free tools are available.

## Questions and data

- CertArc's questions are original scenarios. They are not official ISACA or ISC2 questions, or recalled exam content.
- CertArc is not affiliated with ISACA or ISC2, and does not promise any exam outcome.
- Privacy: https://certarc.com/privacy
- Support: https://certarc.com/support
