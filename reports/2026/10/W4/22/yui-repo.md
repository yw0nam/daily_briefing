---
source: "yui-repo"
date: "2026-10-22"
generated_at: "2026-10-22T08:00:12+09:00"
summary: "YUI repository: 10 updates in the last 24 hours, including closed issues, merged pull requests, features, and review requests for Youngwoo."
sources:
  - {name: "github.com/yw0nam/YUI", status: "ok", last_ok: "2026-10-21T23:00:12Z"}
---

# YUI repository: 10 updates in the last 24 hours, including closed issues, merged pull requests, features, and review requests for Youngwoo.

1. [chore: bump to 0.5.0 and install from the latest release tag](<https://github.com/yw0nam/YUI/pull/1525>)
   pull_request · 2026-10-21T11:26:36Z
   ## Summary Prepares the v0.5.0 tag. `main` is 227 commits ahead of v0.4.0 (`git log --oneline v0.4.0..HEAD | wc -l`). ```diff package.json version 0.4.0 → 0.5.0 src-tauri/tauri.conf.json version 0.4.0 → 0.5.0 src-tauri/Cargo.toml version 0.4.0 → 0.5.0 src-tauri/Cargo.lock app 0.…
2. [\[feature\] browser tool relays JavaScript to ego lite: one task space per preset, every pet window, screenshots as images, CDP module deleted](<https://github.com/yw0nam/YUI/issues/1523>)
   issue · 2026-10-21T11:26:24Z
   ## Work description Replace the client `browser` tool's engine. Today the tool drives a client-owned Chrome over CDP from Rust with five fixed actions, declared only in `main`. After this work it relays a backend-written JavaScript snippet to a locally installed ego lite (`ego-b…
3. [feat: browser tool relays JavaScript to ego lite from every pet window](<https://github.com/yw0nam/YUI/pull/1524>)
   feature · 2026-10-21T11:26:22Z
   ## Summary The client `browser` tool now relays a backend-written JavaScript snippet to the locally installed ego lite CLI, in one task space per preset, from every pet window, and returns the script's output with its screenshots as images. The owned-Chrome CDP module is deleted…
4. [docs: rename the glossary to GLOSSARY.md, move the review traps into CONTRIBUTING.md, and add Merge danger to the PR template](<https://github.com/yw0nam/YUI/pull/1522>)
   pull_request · 2026-10-21T05:43:45Z
   ## Summary The agent skills the workflow loads (domain-modeling, tdd, diagnosing-bugs, code-review) read fixed file names and standards docs. This PR lines the repo up with them. ```diff -CONTEXT.md # glossary +GLOSSARY.md # glossary, the name the skills read CLAUDE.md ### Domai…
5. [\[spike\] ego lite behind a relay browser tool: arbitrary JS, one task space per pet window, a sandbox and login boundary](<https://github.com/yw0nam/YUI/issues/1521>)
   issue · 2026-10-21T05:43:11Z
   ## Uncertainty / question Can the client's `browser` tool become a relay that hands a backend-written JavaScript snippet to a locally installed ego lite (`citrolabs/ego-lite`), so that a backend agent on a remote server drives a browser on the user's machine, each pet window in …
6. [\[feature\] Path-based ingress routing: /presets/<id>/signals and /presets/<id>/avatar/* to the bound window, with setup docs and skill](<https://github.com/yw0nam/YUI/issues/1518>)
   issue · 2026-10-21T01:55:17Z
   ## Work description Path-based routing on the single loopback ingress, and the setup guidance for it. The listener and its port do not change. `POST /signals` and `/avatar/*` keep their meaning and go to `main`. New routes `POST /presets/<id>/signals` and `/presets/<id>/avatar/{…
7. [\[feature\] Owner model for bound pet windows: main keeps hotkey, tray and microphone; per-window settings and message windows; bridge envelope preset tag](<https://github.com/yw0nam/YUI/issues/1517>)
   issue · 2026-10-21T01:55:17Z
   ## Work description Owner model and per-window companions for bound pet windows. `main` registers the global resources (summon hotkey, tray, microphone); a bound window registers none. Each pet window has its own settings window and message window. The cross-window bridge envelo…
8. [feat: settings and message windows per bound pet window, a preset-scoped bridge, and /presets/<id>/ ingress routes](<https://github.com/yw0nam/YUI/pull/1520>)
   feature · 2026-10-21T01:55:16Z
   ## Summary Stacked on #1519 (base branch `bound-pet-window`). Two issues land together because their commits interleaved during review: per-window companions and the owner model (#1517), and path-based ingress routing with the setup guidance (#1518). ### Companions and the owner…
9. [\[feature\] Pet window bound to one preset: query-bound keys, opener, yui.windows, registry rules](<https://github.com/yw0nam/YUI/issues/1516>)
   issue · 2026-10-21T01:47:39Z
   ## Work description A pet window bound to one preset. An extra pet window has label `pet-<id>` and URL `index.html?preset=<id>`; it reads the query once at boot and resolves its storage keys under that preset, ignores `yui://preset-changed`, and shows a scope line instead of the…
10. [feat: pet window bound to one preset, with main-only global resources and a desired-window list main reconciles](<https://github.com/yw0nam/YUI/pull/1519>)
   feature · 2026-10-21T01:47:37Z
   ## Summary A pet window can be bound to one preset. A bound window has the label `pet-<id>` and the URL `index.html?preset=<id>`; every per-preset store in it resolves `yui.<id>.*`, so it talks to that preset's backend with that preset's VRM, voice and transcript. The window wit…
