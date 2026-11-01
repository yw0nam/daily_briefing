---
source: "yui-repo"
date: "2026-11-02"
generated_at: "2026-11-02T08:00:10+09:00"
summary: "YUI repository: 12 updates in the last 24 hours, including closed issues, merged pull requests, features, and review requests for Youngwoo."
sources:
  - {name: "github.com/yw0nam/YUI", status: "ok", last_ok: "2026-11-01T23:00:10Z"}
---

# YUI repository: 12 updates in the last 24 hours, including closed issues, merged pull requests, features, and review requests for Youngwoo.

1. [\[feature\] UI text size: one setting that scales the app's text](<https://github.com/yw0nam/YUI/issues/1770>)
   issue · 2026-11-01T12:27:53Z
   ## Work description YUI has no way to change text size. No setting exists, and webview zoom keys are off (Tauri's `zoom_hotkeys_enabled` defaults to false, `tauri-utils-2.9.2/src/config.rs:2342`, and YUI does not set it). The UI's type tokens (`--yui-fs-*` in `src/ui/tokens.css`…
2. [feat: a text size setting that scales the text in every window](<https://github.com/yw0nam/YUI/pull/1775>)
   feature · 2026-11-01T12:27:51Z
   ## Summary A user-set text size (90%, 100%, 112.5%, 125%, 140%; 100% by default) that scales the text in every window that applies the theme. Spacing and boxes keep their size; the terminal keeps its own font keys. ``` src/settings/appearance/text-size-settings.ts yui.text-size …
3. [\[bug\] The delegation chip shows a cut label glyph in a narrow pet window](<https://github.com/yw0nam/YUI/issues/1766>)
   issue · 2026-11-01T10:51:42Z
   ## Symptoms In a narrow pet window (about 198 pt wide), the delegation chip shows its dot and a fragment of its label with no ellipsis, and the signal chip shrinks to its dot and cross. Neither leaves the window, but the delegation chip's label fragment reads as a broken glyph. …
4. [fix: the delegation chip folds in a narrow pet window instead of showing a cut label](<https://github.com/yw0nam/YUI/pull/1773>)
   pull_request · 2026-11-01T10:51:40Z
   ## Summary In a pet window narrower than 24rem the delegation chip folds to its dot and the count badge, the shape a held press already gives (`is-mini`), instead of a dot beside a label cut to a few pixels. The same threshold folds the Threads chip (#1765). ``` src/ui/chips/del…
5. [\[bug\] yui-notify: the Thread label repeats the project with middle dots, and commands render as prose](<https://github.com/yw0nam/YUI/issues/1769>)
   issue · 2026-11-01T10:51:37Z
   ## Symptoms Threads that yui-notify posts read poorly in the Threads window: 1. The label joins its parts with " · " and repeats the project already in the title: "mbp · tmux yui:2 · YUI (…)" under the title "YUI (…)". 2. A system entry that carries a shell command shows it as p…
6. [fix: yui-notify labels a Thread by host and tmux, and fences a pending command](<https://github.com/yw0nam/YUI/pull/1772>)
   pull_request · 2026-11-01T10:51:35Z
   ## Summary yui-notify's Threads read better in the Threads window. ``` plugins/yui-notify/yui_notify/host/label.py make_label: host and tmux only, ", "-joined; None when neither plugins/yui-notify/yui_notify/hook/event.py a pending tool call is "<tool>:\n```\n<detail>\n```" ``` …
7. [\[feature\] Threads tab density: list width, row height, type scale, and a layout that holds at the minimum size](<https://github.com/yw0nam/YUI/issues/1768>)
   issue · 2026-11-01T10:45:31Z
   ## Work description The Threads window's Threads tab reads cramped and, at small sizes, breaks. A UX audit on the real app (verify bundle, seven seeded Threads from three sources, 724/880/640/420/360 px panels, ko and en, Dawn and Hearth) measured the problems below. This issue …
8. [fix: Threads tab density and a layout that holds at the minimum size](<https://github.com/yw0nam/YUI/pull/1771>)
   pull_request · 2026-11-01T10:45:30Z
   ## Summary The Threads tab's density and its minimum-size layout, from the mock the owner approved (#1768). Stacked on #1764 (base `feat/1763-terminal`), because the Terminal tab shares the window, the pane and the list classes. ``` src/ui/threads/window/ thread-pane.css pane is…
9. [\[feature\] Terminal tab: host terminals the user and the backend share, with per-terminal access on the user's Allow](<https://github.com/yw0nam/YUI/issues/1763>)
   issue · 2026-11-01T10:37:51Z
   ## Work description Add host terminals to YUI. The user opens, uses, and closes terminals in a new **Terminal** tab of the Threads window. The backend agent reaches the same terminals through client tools: it opens and closes terminals freely, and it reads or writes a terminal o…
10. [feat: Terminal tab: host terminals the user and the backend share, with per-terminal access on the user's Allow](<https://github.com/yw0nam/YUI/pull/1764>)
   feature · 2026-11-01T10:37:49Z
   ## Summary Host terminals in YUI that the user and the backend share. The user opens, types into and closes terminals in a new **Terminal** tab of the Threads window. The backend opens and closes its own terminals through client tools; reading or writing any terminal waits on th…
11. [\[bug\] The Threads chip is cut off at the right edge of a narrow pet window](<https://github.com/yw0nam/YUI/issues/1765>)
   issue · 2026-11-01T10:37:33Z
   ## Symptoms In a narrow pet window, the Threads chip runs past the window's right edge and is cut off. The pill shows only its left part. ## Steps to reproduce 1. Run a build whose main pet window is about 200 x 300 pt (a small character scale; the verify bundle on main opens at…
12. [fix: the Threads chip folds in a narrow pet window instead of running off its edge](<https://github.com/yw0nam/YUI/pull/1767>)
   pull_request · 2026-11-01T10:37:32Z
   ## Summary In a narrow pet window the Threads chip folds instead of running past the window edge: under a 24rem window it shows its newest mark and the count, under 16rem the count alone. ``` src/ui/threads/chip/threads-chip.css two @media rules after the is-mini fold DESIGN.md …
