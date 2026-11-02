---
source: "yui-repo"
date: "2026-11-03"
generated_at: "2026-11-03T08:00:13+09:00"
summary: "YUI repository: 24 updates in the last 24 hours, including closed issues, merged pull requests, features, and review requests for Youngwoo."
sources:
  - {name: "github.com/yw0nam/YUI", status: "ok", last_ok: "2026-11-02T23:00:12Z"}
---

# YUI repository: 24 updates in the last 24 hours, including closed issues, merged pull requests, features, and review requests for Youngwoo.

1. [\[feature\] A rate-limited turn says so in plain words](<https://github.com/yw0nam/YUI/issues/1800>)
   issue · 2026-11-02T16:07:41Z
   ## Work description A free hosted chat tier has limits, and a person on the first conversation path will reach them. A user turn that ends on HTTP 429 today shows `429 <server text>` under the input (`src/ui/notices/turn-error.ts:37`, `input.error_http`). Show a plain line inste…
2. [feat: a rate-limited turn shows a plain line](<https://github.com/yw0nam/YUI/pull/1801>)
   feature · 2026-11-02T16:07:39Z
   ## Summary ```diff turnErrorMessage("network_drop", detail) + status 429 → input.error_rate_limit status present → "{status} {message}" no status → server text ``` Why 429 only: it is the status a free tier returns at its limit. The other statuses keep the server's text, which h…
3. [\[feature\] Google Gemini chat preset that fills the URL and the model](<https://github.com/yw0nam/YUI/issues/1798>)
   issue · 2026-11-02T16:07:30Z
   ## Work description Add a Google Gemini entry to the chat provider presets, and let a preset fill the model as well as the URL. `gemini-3.5-flash-lite` is the default free chat model (owner decision, 2026-11-02). `CHAT_PROVIDER_PRESETS` has no Gemini entry and no preset fills a …
4. [feat: the Google Gemini chat preset fills the URL and the model](<https://github.com/yw0nam/YUI/pull/1799>)
   feature · 2026-11-02T16:07:29Z
   ## Summary ```diff handleChatPresetChange commit chat_base_url + commit chat_model, when the preset names one commit chat_api, when the preset names one CHAT_PROVIDER_PRESETS groq + gemini: url + model hermes ``` Why these values: - `models/gemini-3.5-flash-lite`: the form `GET …
5. [\[bug\] Chat Completions tool loop fails on Gemini: dropped signature, silent cue-only turns](<https://github.com/yw0nam/YUI/issues/1795>)
   issue · 2026-11-02T14:26:19Z
   ## Symptoms The Chat Completions tool loop does not work against Gemini's OpenAI-compatible endpoint. Two separate defects show up on a `gemini-3.5-flash-lite` turn: 1. A tool round trip fails with HTTP 400, because the client drops the signature Gemini attaches to a tool call. …
6. [fix!: Chat Completions answers no-text cue-only responses and keeps call extras](<https://github.com/yw0nam/YUI/pull/1796>)
   pull_request · 2026-11-02T14:26:17Z
   ## Summary Gemini's OpenAI-compatible endpoint ends a tool-calling response on `finish_reason: "stop"` and requires its per-call signature back on the next request. This PR makes the Chat Completions tool loop work with both. ``` streamChatCompletions ├─ reducer: keeps a call's …
7. [\[bug\] Copying inside tmux in a Terminal never reaches the system clipboard](<https://github.com/yw0nam/YUI/issues/1792>)
   issue · 2026-11-02T09:00:59Z
   ## Symptoms Copying inside tmux in a Terminal never reaches the system clipboard. The text stays in tmux's own paste buffers. ## Steps to reproduce 1. Open a Terminal in the Threads window. Run `tmux`. 2. Enter copy mode, select text, and copy it (`y`, or `Enter`). 3. Paste in a…
8. [fix: copying inside tmux in a Terminal reaches the system clipboard](<https://github.com/yw0nam/YUI/pull/1793>)
   pull_request · 2026-11-02T09:00:57Z
   ## Summary A Terminal now answers OSC 52, so a copy inside tmux reaches the system clipboard. Option drag forces a native selection when tmux has the mouse. ```diff tmux copy -> ESC ] 52 ; ; <base64> BEL PTY -> terminal_attach channel -> xterm parser - no handler, frame dropped …
9. [\[feature\] The Threads chip hides while its window is open, and a transcript opens at its newest entry](<https://github.com/yw0nam/YUI/issues/1790>)
   issue · 2026-11-02T06:50:50Z
   ## Work description Two Threads window changes the owner decided on 2026-11-02. 1. Main's Threads chip hides while the Threads window is open, on either tab. It shows "Waiting for you" beside the character while the same count and an Amber tab dot already show in the window, and…
10. [feat: the Threads chip hides while its window is open, and a transcript opens at its newest entry](<https://github.com/yw0nam/YUI/pull/1791>)
   feature · 2026-11-02T06:50:48Z
   ## Summary Two Threads window changes. **The Threads chip hides while its window is open.** It showed "Waiting for you" beside the character while the window showed the same count, and it took no pointer events then (`interactive-overlay.ts:23`). ``` threadsWindow.open() ─▶ noti…
11. [\[feature\] The speech bubble keeps only the elements Markdown produces](<https://github.com/yw0nam/YUI/issues/1786>)
   issue · 2026-11-02T03:14:20Z
   ## Work description The speech bubble and the message backlog render backend text through `renderMarkdownInline` (`src/ui/message/markdown.ts`), whose DOMPurify config is DOMPurify's default plus a `data:` hook. That default lets through elements and attributes Markdown never pr…
12. [feat: the speech bubble keeps only the elements Markdown produces](<https://github.com/yw0nam/YUI/pull/1789>)
   feature · 2026-11-02T03:14:18Z
   ## Summary The speech bubble and the backlog rendered backend text through DOMPurify's default config, which keeps elements Markdown never produces (`srcset`, `<picture>`, `<video>`/`<audio>` with autoplay, SVG `<image href>`, `style`, `td background`, `<input type="image">`, `<…
13. [\[bug\] The settings hint dot shows no cursor change on macOS 26.2](<https://github.com/yw0nam/YUI/issues/1787>)
   issue · 2026-11-02T03:13:09Z
   ## Symptoms The settings hint dot (`.yui-hint-dot`, the small `?` beside a setting) sets `cursor: help` (`src/ui/quick-controls/quick-controls.css:374`). WebKit 26.2 does not show `help` (measured in the #1777 diagnosis; WebKit bug 303845), so the pointer stays the arrow over it…
14. [fix: the settings hint dot shows the pointer cursor on macOS 26.2](<https://github.com/yw0nam/YUI/pull/1788>)
   pull_request · 2026-11-02T03:13:07Z
   ## Summary The settings hint dot (`.yui-hint-dot`) set `cursor: help`, which WebKit 26.2 does not show (WebKit bug 303845; measured in the #1777 diagnosis). It now uses `pointer`, like the app's other buttons. ``` src/ui/quick-controls/quick-controls.css:374 cursor: help → point…
15. [\[feature\] Render Thread entries as Markdown](<https://github.com/yw0nam/YUI/issues/1779>)
   issue · 2026-11-02T02:58:27Z
   ## Work description Render Thread entries as Markdown in the Threads window. Today `richText` (`src/ui/threads/window/rich-text.ts`, called from `thread-pane.ts:31`) styles only fenced code blocks and `code` spans and leaves every other character as text, so a table arrives as r…
16. [feat: Thread entries render as Markdown](<https://github.com/yw0nam/YUI/pull/1785>)
   feature · 2026-11-02T02:58:26Z
   ## Summary Thread entries showed producer text as plain text (only code fences and `code` spans were styled), so a Markdown table arrived as raw `| a | b |` lines. Entries now render as Markdown through the speech bubble's renderer. Built on #1784 (#1776, merged): its surface to…
17. [\[feature\] Threads window: transcript follows the pane width, sections on distinct surfaces](<https://github.com/yw0nam/YUI/issues/1776>)
   issue · 2026-11-02T02:53:35Z
   ## Work description Make the Threads window readable at any size and its sections easy to tell apart. This covers both the Threads tab and the Terminal tab. 1. The transcript follows the pane width. `.yui-threads-entry { max-width: 72ch; }` (`src/ui/threads/window/thread-pane.cs…
18. [feat: the Threads window's sidebar, head and body sit on distinct surfaces, and the transcript fills the pane](<https://github.com/yw0nam/YUI/pull/1784>)
   feature · 2026-11-02T02:53:33Z
   ## Summary The Threads window's sidebar, head and body were nearly one colour (Hearth: list `--yui-panel-bg` L 0.16, head and body `--yui-scrim-strong` L 0.18 at alpha 0.9), the desktop showed through the panel, and the transcript stopped at 72ch however wide the window was. Bui…
19. [\[bug\] Korean IME input is wrong in the Terminal tab](<https://github.com/yw0nam/YUI/issues/1778>)
   issue · 2026-11-02T02:38:14Z
   ## Symptoms Korean input through the macOS IME does not work correctly in the Threads window's Terminal tab (xterm.js 6.0.0). The exact failure (lost, duplicated or split syllables) is not measured yet. ## Steps to reproduce 1. Open the Threads window, Terminal tab, and open a t…
20. [fix: the Terminal tab sends whole Hangul syllables typed through WebKit's Korean IME](<https://github.com/yw0nam/YUI/pull/1783>)
   pull_request · 2026-11-02T02:38:12Z
   ## Summary Korean typed into the Terminal tab reached the shell as lone jamo (`안녕하세요` → `ㅇㄴㅎ세`). With the macOS Korean 2-Set IME, WebKit fires no composition events: it inserts a syllable as an `insertText` input and rewrites it in place as `insertReplacementText` inputs, and xt…
21. [\[bug\] The Threads window's resize edges show no resize cursor](<https://github.com/yw0nam/YUI/issues/1777>)
   issue · 2026-11-02T02:28:25Z
   ## Symptoms The pointer does not change to a resize cursor on the Threads window's edges and corners, so the resize is hard to find. The handles set `ns-resize`, `ew-resize`, `nwse-resize` and `nesw-resize` in `src/ui/threads/window/resize-handles.css`. The cause is not measured…
22. [fix: the Threads window's resize edges and corners show a resize cursor on macOS 26.2](<https://github.com/yw0nam/YUI/pull/1782>)
   pull_request · 2026-11-02T02:28:23Z
   ## Summary On macOS 26.2 the Threads window's resize edges and corners showed the arrow: WebKit 26.2 does not show `ew-resize`, `ns-resize`, `nwse-resize` or `nesw-resize` ([WebKit bug 303845](https://bugs.webkit.org/show_bug.cgi?id=303845), regression in 300377@main; measured i…
23. [\[feature\] Picking a waiting Thread clears it from the Threads chip](<https://github.com/yw0nam/YUI/issues/1780>)
   issue · 2026-11-02T02:28:13Z
   ## Work description A waiting Thread keeps the Threads chip's count and nod until the user answers it. `createThreadsChip` counts every Thread with `state === "input-required"` (`src/ui/threads/chip/threads-chip.ts:113`). A user who has read a Thread but does not want to answer …
24. [feat: picking a waiting Thread clears it from the Threads chip](<https://github.com/yw0nam/YUI/pull/1781>)
   feature · 2026-11-02T02:28:11Z
   ## Summary A waiting Thread kept the Threads chip's count and nod until the user answered it. Now picking a Thread with an open ask in the Threads window's list or rail records that ask as seen, and main's Threads chip stops counting it. The Threads window itself still shows the…
