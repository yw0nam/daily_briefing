---
source: "yui-repo"
date: "2026-10-31"
generated_at: "2026-10-31T08:00:11+09:00"
summary: "YUI repository: 14 updates in the last 24 hours, including closed issues, merged pull requests, features, and review requests for Youngwoo."
sources:
  - {name: "github.com/yw0nam/YUI", status: "ok", last_ok: "2026-10-30T23:00:11Z"}
---

# YUI repository: 14 updates in the last 24 hours, including closed issues, merged pull requests, features, and review requests for Youngwoo.

1. [\[feature\] yui-notify: Claude Code takes Thread answers through its inbox socket, and the channel server goes](<https://github.com/yw0nam/YUI/issues/1747>)
   issue · 2026-10-30T14:37:04Z
   ## Work description Claude Code takes Thread answers through the yui-notify channel server when launched with `--dangerously-load-development-channels`, or, since #1746, through a Stop hook that holds the turn for up to `wait.stop`. The channel needs a research-preview flag, `uv…
2. [\[spike\] Claude Code Thread answers without the development channels flag](<https://github.com/yw0nam/YUI/issues/1742>)
   issue · 2026-10-30T14:37:04Z
   ## Uncertainty / question Claude Code receives Thread answers only through the yui-notify channel server, and the session must start with: ```bash claude --dangerously-load-development-channels plugin:yui-notify@yui ``` Can a Claude Code user receive Thread answers without this …
3. [feat!: Claude Code takes Thread answers through its inbox socket, and the channel server goes](<https://github.com/yw0nam/YUI/pull/1751>)
   pull_request · 2026-10-30T14:37:02Z
   ## Summary Claude Code now takes Thread answers through its own cross-session inbox socket. The channel server and its launch flag are gone, and so is the Stop hook that held the turn while it waited (#1746). Breaking for anyone launching with `--dangerously-load-development-cha…
4. [\[feature\] yui-notify: Claude Code Stop answers through a waiting hook when no channel is ready](<https://github.com/yw0nam/YUI/issues/1745>)
   issue · 2026-10-30T13:37:50Z
   ## Work description A Claude Code session takes Thread answers only through the yui-notify channel server. On a claude.ai Team account the channel never registers (`--dangerously-load-development-channels blocked by org policy`, measured 2026-10-30 on Claude Code 2.1.314), and a…
5. [feat: Claude Code Stop answers through a waiting hook when no channel is ready](<https://github.com/yw0nam/YUI/pull/1746>)
   feature · 2026-10-30T13:37:49Z
   ## Summary On a claude.ai Team account the yui-notify channel never registers (`--dangerously-load-development-channels blocked by org policy`), and a plain `claude` launch has no channel either. Until now such a session posted a `completed` Thread with no ask, so the user could…
6. [\[feature\] yui-notify: one package by feature, and a setup that proves the Claude Code answer path](<https://github.com/yw0nam/YUI/issues/1743>)
   issue · 2026-10-30T13:32:56Z
   ## Work description Two changes to `plugins/yui-notify`, in one PR. **Layout.** Today the code sits in two trees: `scripts/yui_notify/` lists 14 modules of several features side by side (`git ls-files plugins/yui-notify/scripts/yui_notify/*.py | grep -v test_ | wc -l` = 15 inclu…
7. [refactor: yui-notify moves into one package by feature, and setup proves the answer path](<https://github.com/yw0nam/YUI/pull/1744>)
   pull_request · 2026-10-30T13:32:55Z
   ## Summary **Layout.** `plugins/yui-notify` had two code trees: `scripts/yui_notify/` listed the modules of several features side by side, and `channel/` reached it by inserting `scripts/` into `sys.path`. One package now holds them, one sub-folder per feature, with tests in `te…
8. [\[feature\] Threads: read and answer outside conversations in YUI](<https://github.com/yw0nam/YUI/issues/1725>)
   issue · 2026-10-30T04:53:39Z
   ## Work description Add **Threads**: outside conversations the user reads and answers in YUI. A Thread is one conversation from a producer (a Claude Code or Codex session, a GitHub PR, a Gmail mail, a Notion comment) that can hold one open **ask**. The user answers the ask in th…
9. [feat!: Threads, outside conversations the user reads and answers in YUI (#1725)](<https://github.com/yw0nam/YUI/pull/1741>)
   pull_request · 2026-10-30T04:53:38Z
   ## Summary **Threads**: outside conversations the user reads and answers in YUI. A Thread is one conversation from a producer (a Claude Code or Codex session, a GitHub PR, a mail thread) that can hold one open ask; the user answers it in the Threads window with a choice, free te…
10. [fix: yui-notify names the agent from the payload, leaves on a signal, and starts no Codex MCP server (#1725)](<https://github.com/yw0nam/YUI/pull/1740>)
   pull_request · 2026-10-30T04:39:56Z
   ## Summary Fixes from the final e2e run of `feat/threads`, plus the yui-notify part of the line audit. yui-notify is now 0.6.1. - **N1: the payload names the agent.** Codex's SessionEnd payload has no `turn_id`. So a Codex session started from a Claude Code shell (`CLAUDECODE=1`…
11. [refactor: trim the Threads app side and fold the dock back into the quick card (#1725)](<https://github.com/yw0nam/YUI/pull/1739>)
   pull_request · 2026-10-30T04:36:06Z
   ## Summary This PR trims the app side of `feat/threads` without changing behaviour. The exceptions are listed under "Behaviour changes". The PR came out of a line audit of the sprint diff. - **Dock moved back into the quick card.** The Threads window stopped docking in #1738, so…
12. [feat: the Threads window resizes, remembers its frame, and lays out by width (#1725)](<https://github.com/yw0nam/YUI/pull/1738>)
   feature · 2026-10-30T02:21:21Z
   ## Summary The Threads window becomes a free, resizable window: it no longer docks to the character, it is not kept on top, it reopens where the user left it, and its layout follows its width. Decided with the owner on 2026-10-30 after the PR 8 (#1736) rung-3 run showed a 960 px…
13. [feat: the Threads window drags and docks like the quick card; first click lands; the chip keeps its count (#1725)](<https://github.com/yw0nam/YUI/pull/1736>)
   feature · 2026-10-30T01:14:29Z
   ## Summary The Threads window drags and docks to the character like the quick card, on one dock module the two windows share. Found by the e2e on `feat/threads`: a first click into an unfocused Threads window only focused it (F3), and with the character at the right screen edge …
14. [refactor: plugins/, skills/, integrations/<agent>/ hold one kind each; the Thread producer skill ships in yui-notify (#1725)](<https://github.com/yw0nam/YUI/pull/1737>)
   pull_request · 2026-10-30T00:35:29Z
   ## Summary One folder per kind: every Plugin in `plugins/`, every standalone Skill in `skills/`, agent-specific adapters only in `integrations/<agent>/`. The Thread producer skill ships inside yui-notify, so one marketplace install gives a coding agent both the hooks and the ski…
