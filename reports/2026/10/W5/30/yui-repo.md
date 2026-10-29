---
source: "yui-repo"
date: "2026-10-30"
generated_at: "2026-10-30T08:00:12+09:00"
summary: "YUI repository: 33 updates in the last 24 hours, including closed issues, merged pull requests, features, and review requests for Youngwoo."
sources:
  - {name: "github.com/yw0nam/YUI", status: "ok", last_ok: "2026-10-29T23:00:12Z"}
---

# YUI repository: 33 updates in the last 24 hours, including closed issues, merged pull requests, features, and review requests for Youngwoo.

1. [fix: yui-notify posts a channel answer once and closes a Claude Code Thread at session end (#1725)](<https://github.com/yw0nam/YUI/pull/1735>)
   pull_request · 2026-10-29T16:34:55Z
   ## Summary Two yui-notify fixes found by the e2e on `feat/threads` with a real Claude Code session (#1725). - **F1 — a channel answer was recorded twice.** A next instruction answered in the Threads window reaches Claude Code as a channel message; YUI's store already records it …
2. [docs: yui-thread-producer settles failure re-asks, release, and the GitHub check rules (#1725)](<https://github.com/yw0nam/YUI/pull/1734>)
   pull_request · 2026-10-29T16:11:21Z
   ## Summary Fixes to the `yui-thread-producer` skill from its e2e (#1725). An agent that knew only the skill built an n8n GitHub-PR producer from it; the build worked end to end (Thread posted, answer swept, comment posted, merge refused and reported as a partial failure), and th…
3. [feat: Threads reach the main character's backend through threads_list, threads_search and the threads line (#1725)](<https://github.com/yw0nam/YUI/pull/1733>)
   feature · 2026-10-29T15:34:53Z
   ## Summary The main character's backend can see Threads (#1725). Threads still fire no turn; the backend reads them only when it chooses to. - **`threads_list`** — waiting Threads by default (`state: "all"` for every one, `source` to filter), at most 20 rows newest first, each w…
4. [feat: answers route for scheduled Thread producers and the yui-thread-producer skill (#1725)](<https://github.com/yw0nam/YUI/pull/1732>)
   feature · 2026-10-29T15:07:44Z
   ## Summary Producers other than the coding agents (GitHub PRs, Gmail, any source) get one route and one skill (#1725). - **`GET /threads/answers?source=<source>`** — a scheduled producer (cron, n8n, a CI step) collects every pending answer of its source in one call per run: `200…
5. [feat: yui-notify answers Claude Code through a channel server (#1725)](<https://github.com/yw0nam/YUI/pull/1731>)
   feature · 2026-10-29T14:24:48Z
   ## Summary Claude Code answers come back from the Threads window through a **channel server** that ships in yui-notify (#1725). Hook text is not followed when it conflicts with the user's prompt; a channel message is (spike, 2026-10-29). The server is built on the MCP Python SDK…
6. [feat: Threads window and Threads chip (#1725)](<https://github.com/yw0nam/YUI/pull/1730>)
   feature · 2026-10-29T14:16:48Z
   ## Summary The main character gets a **Threads chip** and a **Threads window** (#1725). The user reads outside conversations (Claude Code and Codex sessions, PRs, mail) and answers them; the answer goes to the store from #1728, and the producer collects it. ``` src/ io/threads/t…
7. [feat!: yui-notify posts Threads and Codex answers through its hooks](<https://github.com/yw0nam/YUI/pull/1729>)
   pull_request · 2026-10-29T13:59:08Z
   ## Summary yui-notify becomes the coding-agent **Thread** producer (#1725). It stops sending `/signals` and posts Threads to `PUT /threads/<id>`; Codex answers come back through its synchronous hooks. ``` integrations/yui-notify/ hooks/hooks.json Stop + PermissionRequest synchro…
8. [feat: Thread store and /threads routes in the shell](<https://github.com/yw0nam/YUI/pull/1728>)
   feature · 2026-10-29T13:48:57Z
   ## Summary The Rust shell keeps **Threads**: outside conversations a producer posts and the user answers in YUI (#1725). This PR is the store and its loopback routes; the window and chip come in the next PR. ``` src-tauri/src/ threads/ the store: model, rules, disk, commands, wi…
9. [\[bug\] emotion_text schema allows one tag while the instructions and the TTS take a sequence](<https://github.com/yw0nam/YUI/issues/1726>)
   issue · 2026-10-29T13:30:09Z
   ## Symptoms In enum mode (a TTS provider with a tag table, such as Irodori), the `emotion_text` schema accepts only one tag. The instructions and the TTS accept a sequence of tags. The two contradict each other: - `configs/endpoints.json` `chat_instructions`: "Repeat a tag to in…
10. [fix: enum-mode emotion_text takes a sequence of table tags](<https://github.com/yw0nam/YUI/pull/1727>)
   pull_request · 2026-10-29T13:30:08Z
   ## Summary In enum mode, `emotion_text` declared the TTS tag table as an `enum`, so the schema took one tag. The instructions (`configs/endpoints.json` `chat_instructions`: "Repeat a tag to intensify; combine tags freely"), the Irodori TTS, and the Hermes gate (`tokenize_emotion…
11. [\[feature\] claude-routines Integration: a Claude Code routine as a character's Brain over push](<https://github.com/yw0nam/YUI/issues/1724>)
   issue · 2026-10-29T11:42:23Z
   ## Work description Add the **claude-routines Integration** under `integrations/claude-routines/`: a small process on the user's PC that makes a Claude Code routine a character's Brain. To YUI it is a push backend (`chat_api: "push"`, `docs/reference/push-transport.md`). To the …
12. [Wayfinder: a cloud agent as a character's Brain](<https://github.com/yw0nam/YUI/issues/1712>)
   issue · 2026-10-29T08:51:27Z
   ## Destination A hand-off spec, filed as a `feature_task` issue, for a Claude Code routines Integration under `integrations/claude-routines/` that makes a routine a character's Brain: the Integration, a process on the user's PC, speaks the push transport to YUI, starts routine r…
13. [Security review of the claude-routines Integration spec](<https://github.com/yw0nam/YUI/issues/1723>)
   issue · 2026-10-29T08:47:31Z
   Part of #1712 ## Question An independent reviewer threat-models the spec: the public MCP endpoint and its header secret, the fire tokens and config file, the routine's connectors and built-in tools, prompt injection through user text and `client_context` into the routine, replie…
14. [Spec review of the claude-routines Integration spec](<https://github.com/yw0nam/YUI/issues/1722>)
   issue · 2026-10-29T08:47:28Z
   Part of #1712 ## Question Run `dev-workflow:spec-review` on the spec with a fresh reviewer. Answer every finding in the spec issue (accepted and changed, or rejected with the reason).
15. [Write the hand-off spec for the claude-routines Integration](<https://github.com/yw0nam/YUI/issues/1721>)
   issue · 2026-10-29T08:16:53Z
   Part of #1712 ## Question Write the hand-off spec as a `feature_task` issue from the map's Decisions so far: process layout under `integrations/claude-routines/`, push frames handled, fire text format, the `reply` tool schema, transcript store, config file, security measures, th…
16. [Direction sentence for README.md and AGENTS.md](<https://github.com/yw0nam/YUI/issues/1719>)
   issue · 2026-10-29T08:12:36Z
   Part of #1712 ## Question Which sentence states that YUI is the body for always-on cloud agents, beside local models and self-hosted agents? Where does it go in `README.md` and `AGENTS.md`, and how does it stay within the backend-agnostic rule (`README.md` may name an agent that…
17. [Security of the Integration's public MCP endpoint](<https://github.com/yw0nam/YUI/issues/1718>)
   issue · 2026-10-29T07:59:15Z
   Part of #1712 ## Question The Integration's MCP endpoint is public through a tunnel. What protects it (secret header, per-installation token, tunnel access control)? What can a caller who holds the URL make the character do? Where are the routine fire token and the endpoint secr…
18. [How one push turn maps onto routine runs](<https://github.com/yw0nam/YUI/issues/1717>)
   issue · 2026-10-29T07:42:10Z
   Part of #1712 ## Question Map each push-transport frame (`docs/reference/push-transport.md`) onto bridge actions: `turn` to the fire body; the run's reply through the MCP `reply` tool to `render` and `turn_end`; silence (empty text or `[SILENT]`); `stop`, `reset`, and `chat_id`;…
19. [One routine round trip: API fire in, MCP reply out](<https://github.com/yw0nam/YUI/issues/1716>)
   issue · 2026-10-29T07:24:05Z
   Part of #1712 ## Question With a throwaway stub (never merged), run one round trip on Claude Code routines: fire a routine (model `claude-haiku-5-5`) with a message, and have the run call a `reply` tool on a tunnelled MCP server that claude.ai reaches as a custom connector. Reco…
20. [Muse Spark as a Brain: model API and agent surfaces](<https://github.com/yw0nam/YUI/issues/1720>)
   issue · 2026-10-29T07:02:54Z
   Part of #1712 ## Question Can Meta's Muse Spark be a character's Brain, and through which route? (1) Model route: does the Meta Model API (Muse Spark 1.1, public preview) accept Chat Completions or Responses requests that YUI already sends, with streamed tool calls, image input …
21. [Tunnels for a public MCP endpoint on the user's PC](<https://github.com/yw0nam/YUI/issues/1715>)
   issue · 2026-10-29T07:00:31Z
   Part of #1712 ## Question Compare cloudflared (quick and named tunnels), ngrok, and Tailscale Funnel for exposing a local HTTP MCP server to Grok Bot: a URL that survives restarts on a free plan, HTTPS, streamed responses (SSE / Streamable HTTP), access control, install on macOS…
22. [Grok Bot remote MCP plugins: transport, auth, and unattended tool calls](<https://github.com/yw0nam/YUI/issues/1714>)
   issue · 2026-10-29T06:59:34Z
   Part of #1712 ## Question For a remote MCP server attached to Grok Bot as a plugin: (1) Which MCP transports and protocol versions does it accept (Streamable HTTP, SSE)? (2) Which auth does it support (static headers, OAuth)? (3) Does a tool call need approval in the Grok Bot ap…
23. [Grok Bot webhook wake: payload, latency, and conversation continuity](<https://github.com/yw0nam/YUI/issues/1713>)
   issue · 2026-10-29T06:56:54Z
   Part of #1712 ## Question For a Grok Bot routine with a webhook trigger: (1) Does the POST JSON body reach the bot's run, and in what form? (2) Does a run that a webhook starts continue the bot's earlier conversation and memory, or start fresh? (3) How long from the POST to the …
24. [\[feature\] Docs site: reader-first page groups, new Start pages, and readable item lists](<https://github.com/yw0nam/YUI/issues/1709>)
   issue · 2026-10-29T06:45:49Z
   ## Work description The docs site (`docs/`, VitePress, deployed by `.github/workflows/pages.yml` when a release is published) is hard to read, and its pages do not match what a reader looks for. This issue reorganises the pages and restyles how they read. The work is in one PR b…
25. [docs: short picture-led pages with Mermaid diagrams, fresh captures, and reader-first groups](<https://github.com/yw0nam/YUI/pull/1710>)
   pull_request · 2026-10-29T06:45:47Z
   ## Summary The docs site is regrouped by who reads it, and its item lists read as definition rows. ``` Guide sidebar Reference sidebar Start Install (new) Backend contract Client Context Install with a coding agent Client Tools Connect a backend (new) Push transport (was linked …
26. [Plugin author guide and glossary](<https://github.com/yw0nam/YUI/issues/1671>)
   issue · 2026-10-29T01:47:08Z
   Part of #1657 ## Question Write the plugin author guide (layout, `.mcp.json`, the `_meta` keys for preset and wait, the three sources and how to list a community plugin by PR, local testing) and check that YUI-hosted in `GLOSSARY.md` § Plugins and tools matches the shipped code.…
27. [docs: plugin author guide and community catalog listing](<https://github.com/yw0nam/YUI/pull/1708>)
   pull_request · 2026-10-29T01:47:07Z
   ## Summary A published author guide for YUI-hosted plugins, and the procedure to list a community plugin. ``` docs/guide/write-a-plugin.md (new, Guide sidebar after Plugins) Layout · Servers · Tools · Skills · Test locally · Publish CONTRIBUTING.md § Plugins (new) community list…
28. [\[bug\] Plugins page shows a plugin's tool count twice](<https://github.com/yw0nam/YUI/issues/1706>)
   issue · 2026-10-29T01:24:00Z
   ## Symptoms On the Plugins page (#1668, PR #1705), a running plugin shows its tool count twice: once on the server status line and once on the tool-list disclosure. With one server the two numbers are the same fact said twice, which the page's own polish rule ("each fact is said…
29. [fix: the Plugins page says a plugin's tool count once](<https://github.com/yw0nam/YUI/pull/1707>)
   pull_request · 2026-10-29T01:23:58Z
   ## Summary A running plugin said its tool count twice on the Plugins page: once on the server status line (`main Running Tools: 4`) and once on the tools disclosure (`Tools: 4, skills: 1`). The server line now shows the state alone; the disclosure keeps the count. ``` serverHtml…
30. [Plugins page in the settings window](<https://github.com/yw0nam/YUI/issues/1668>)
   issue · 2026-10-29T00:55:50Z
   Part of #1657 ## Question Build the Plugins page from the approved mock over the host's snapshots and commands: catalog list, installed list, Install / Update / Remove, Enable with the two-step consent, per-server status and log tail, Add from folder. Done when every control wor…
