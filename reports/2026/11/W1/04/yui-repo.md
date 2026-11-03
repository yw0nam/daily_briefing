---
source: "yui-repo"
date: "2026-11-04"
generated_at: "2026-11-04T08:00:12+09:00"
summary: "YUI repository: 22 updates in the last 24 hours, including closed issues, merged pull requests, features, and review requests for Youngwoo."
sources:
  - {name: "github.com/yw0nam/YUI", status: "ok", last_ok: "2026-11-03T23:00:12Z"}
---

# YUI repository: 22 updates in the last 24 hours, including closed issues, merged pull requests, features, and review requests for Youngwoo.

1. [chore: a red-run script and a guard on rule tests](<https://github.com/yw0nam/YUI/pull/1828>)
   pull_request · 2026-11-03T17:25:05Z
   ## Summary Two guards from the retro of the #1809/#1816/#1814 session. - **`scripts/red-run.sh <test-commit>`** checks a `test:` commit out in a throwaway worktree, runs the test files it adds or changes (vitest, and pytest for a plugin's `tests/test_*.py` through its uv project…
2. [\[feature\] Backend slash commands from the text input over the push transport](<https://github.com/yw0nam/YUI/issues/1814>)
   issue · 2026-11-03T17:07:24Z
   ## Work description Let the user run the backend's own slash commands (`/status`, `/usage`, `/model …`) from the text input, the way Telegram and Discord offer a Hermes gateway's commands. Push transport only. Today a typed `/usage` reaches the model as text, for two reasons mea…
3. [feat: backend commands in the unified chat window](<https://github.com/yw0nam/YUI/pull/1827>)
   feature · 2026-11-03T17:07:22Z
   ## Summary The unified chat window runs Backend commands for its one picked character, the second part of #1814 (#1826 shipped the pet and message windows). The `@` list and the `/` list now share one listbox, and only one opens on the field at a time. ``` unified composer, one …
4. [feat: backend slash commands from the text input over the push transport](<https://github.com/yw0nam/YUI/pull/1826>)
   feature · 2026-11-03T15:12:59Z
   ## Summary The user can run the backend's own slash commands (`/status`, `/usage`, `/model …`) from the text input over the push transport, the way Telegram and Discord offer a Hermes gateway's commands. Before, a typed `/usage` reached the model as text: the YUI plugin sends tu…
5. [\[bug\] A Hermes clarify question over the YUI platform never gets the user's answer](<https://github.com/yw0nam/YUI/issues/1816>)
   issue · 2026-11-03T13:03:24Z
   ## Symptoms When a Hermes character calls its clarify tool over the YUI platform, the user's next message does not answer the question. The agent stays blocked until `clarify.timeout` (default 3600 s, Hermes `tools/clarify_gateway.py:283-308`) and then sees `[user did not respon…
6. [feat: Hermes clarify questions reach the user as an Ask card](<https://github.com/yw0nam/YUI/pull/1822>)
   feature · 2026-11-03T13:03:22Z
   ## Summary A Hermes clarify question now reaches the user as the Ask card #1821 added, with its choices and a free-text field, and the user's answer resolves it from an `answer` frame. Before, the plugin did not override `send_clarify`, the user's typed reply arrived as an ordin…
7. [\[feature\] Tool-command approval prompts reach the user in YUI (buttons: once / session / deny)](<https://github.com/yw0nam/YUI/issues/1809>)
   issue · 2026-11-03T11:16:18Z
   ## Work description When a character runs an approval-gated command (for example an ssh command to a server) on the Hermes gateway, the user never sees the approval request and the command is denied at the timeout with `BLOCKED: Command timed out without user response.` Observed…
8. [feat: Hermes exec approvals reach the user as an Ask card over the push transport](<https://github.com/yw0nam/YUI/pull/1821>)
   feature · 2026-11-03T11:16:16Z
   ## Summary A Hermes exec approval (an approval-gated terminal command) now reaches the user as an Ask card in the character's window, and the user's choice resolves it. Before, the YUI plugin did not render approval prompts, Hermes's text fallback was dropped as an interim send,…
9. [\[feature\] A test keeps app commands, the app manifest and capability permissions in step](<https://github.com/yw0nam/YUI/issues/1819>)
   issue · 2026-11-03T08:29:25Z
   ## Work description A Tauri app command registered only in `src-tauri/src/commands.rs` passes every gate and CI job, then fails at runtime with "<command> not allowed. Command not found". It also needs an entry in `COMMANDS` in `src-tauri/build.rs` (the app manifest) and an `all…
10. [test: app commands stay in the app manifest and their capability permissions](<https://github.com/yw0nam/YUI/pull/1820>)
   pull_request · 2026-11-03T08:29:23Z
   ## Summary This PR adds `tests/app-commands.test.ts`, beside `tests/opener-capability.test.ts`. A command registered only in `src-tauri/src/commands.rs` passes every gate, then fails at runtime with "<command> not allowed. Command not found". On #1818 `thread_read` did this. The…
11. [\[feature\] Mark a waiting Thread read from the Threads window](<https://github.com/yw0nam/YUI/issues/1817>)
   issue · 2026-11-03T08:17:45Z
   ## Work description A waiting Thread stays waiting until it is answered or its producer posts another state. Some never get either: the user does not need to answer, or the session ended without a `SessionEnd` hook (a killed terminal). They keep the Waiting tab, the `{n} waiting…
12. [feat: Mark read clears a waiting Thread from the Threads window](<https://github.com/yw0nam/YUI/pull/1818>)
   feature · 2026-11-03T08:17:44Z
   ## Summary A **Mark read** button in the Threads window's thread pane clears a waiting Thread that will never be answered: a question the user does not need to answer, or a session that ended without a `SessionEnd` hook. ``` thread pane head ── Mark read ──▶ client.read(id) ──▶ …
13. [\[feature\] README leads with the installers and the first-run path](<https://github.com/yw0nam/YUI/issues/1806>)
   issue · 2026-11-03T06:41:49Z
   ## Work description Item 7 of the entry-barrier roadmap (#1804). The README Quickstart opens with "You need a coding agent" and lists Ollama and LM Studio as the way to talk with her. That contradicts the promise in `PRODUCT.md`: a person who can install a desktop app reaches a …
14. [docs: the README leads with the installers and the first-run path](<https://github.com/yw0nam/YUI/pull/1808>)
   pull_request · 2026-11-03T06:41:48Z
   ## Summary ``` README.md / README.ja.md Quickstart: installers → Connect → Quick start key → greeting coding agent and source build: one link to Install Known limitations: install line trimmed docs/guide/installation.md release build first; a First launch section ``` The Quickst…
15. [\[feature\] The Push description no longer says only Hermes Agent supports it](<https://github.com/yw0nam/YUI/issues/1810>)
   issue · 2026-11-03T06:31:58Z
   ## Work description Other agents speak the push contract now, so the claim that only Hermes Agent supports Push is false. Remove it from the settings text and from the docs, and remove the Hermes Agent link it carried. Measured on origin/main 2026-11-03: - `svc.chat_desc_push` i…
16. [feat: the Push description names no agent and carries no Hermes Agent link](<https://github.com/yw0nam/YUI/pull/1811>)
   feature · 2026-11-03T06:31:57Z
   ## Summary ``` src/ui/i18n/{en,ja,ko}.ts svc.chat_desc_push: drops "Currently only {agent} supports this" src/ui/quick-controls/connection/chat-type.ts description is plain text; the {agent} split and the link are gone src/ui/quick-controls/constants.ts HERMES_AGENT is gone; the…
17. [\[feature\] Quick start replays the first conversation](<https://github.com/yw0nam/YUI/issues/1807>)
   issue · 2026-11-03T06:26:51Z
   ## Work description After Quick start connects, the pet window runs the first conversation once: the card greeting (only on an empty session), then the input, then the controls hint with **Hear the controls** and **Hear what she can do** (`src/app/turn/wire-first-conversation.ts…
18. [\[feature\] Quick start voice step and default voices by language](<https://github.com/yw0nam/YUI/issues/1802>)
   issue · 2026-11-03T06:26:49Z
   ## Work description Part 2 of the first conversation setup (#1797, merged in #1803). The chat path ships first; this adds the optional voice step to Quick start's connected state, between the done line and Help. The step opens the Fish Audio key page in the default browser, take…
19. [feat: Quick start turns voice on with a default voice per language, and replays the first conversation](<https://github.com/yw0nam/YUI/pull/1812>)
   feature · 2026-11-03T06:26:48Z
   ## Summary Quick start's connected state turns voice on with a Fish Audio key and a default voice for the app language, a failed reply offers another voice under the bubble, and a Help row replays the first conversation. ```text Connection · Quick start (connected) ✓ Connected. …
20. [\[spike\] Plain words for Chat Completions, Responses and Push](<https://github.com/yw0nam/YUI/issues/1805>)
   issue · 2026-11-03T05:45:00Z
   ## Uncertainty / question How does YUI explain Chat Completions, Responses and Push to a person who does not know these words? Today's text states the mechanism: | Key | English text | |---|---| | `svc.chat_option_chat_completions` | Chat Completions · YUI sends the history | | …
21. [\[feature\] First conversation setup: Quick start on Connection, a free key to the first greeting](<https://github.com/yw0nam/YUI/issues/1797>)
   issue · 2026-11-03T04:37:01Z
   ## Work description A person who can install a desktop app reaches a first conversation with the character without a terminal, a coding agent, or knowing a URL or model name (`PRODUCT.md`, Users). Before this work a fresh install showed one bubble naming an OpenAI-compatible ser…
22. [feat: Quick start on Connection takes a free key to the first greeting](<https://github.com/yw0nam/YUI/pull/1803>)
   feature · 2026-11-03T04:37:00Z
   ## Summary A person with a free Gemini key reaches a first conversation from the Connection page, with no URL or model name. Connection has a **Quick start | Detailed settings** switch; Quick start is the free path, Detailed settings is the Connection page as it is on `main`. ``…
