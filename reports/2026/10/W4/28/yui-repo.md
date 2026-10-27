---
source: "yui-repo"
date: "2026-10-28"
generated_at: "2026-10-28T08:00:13+09:00"
summary: "YUI repository: 20 updates in the last 24 hours, including closed issues, merged pull requests, features, and review requests for Youngwoo."
sources:
  - {name: "github.com/yw0nam/YUI", status: "ok", last_ok: "2026-10-27T23:00:13Z"}
---

# YUI repository: 20 updates in the last 24 hours, including closed issues, merged pull requests, features, and review requests for Youngwoo.

1. [fix: /signals accepts a request without an envelope again, as a deprecated immediate group](<https://github.com/yw0nam/YUI/pull/1644>)
   pull_request · 2026-10-27T14:37:48Z
   ## Summary v0.4.0 accepted `POST /signals` without an `envelope` (or with `"envelope": null`) and delivered it as a legacy group that behaved like `immediate`; its `docs/reference/signals-ingress.md` documented that request. #1309 made the envelope required, so on main that requ…
2. [docs: bring the guide and docs home up to date for v0.5.0](<https://github.com/yw0nam/YUI/pull/1632>)
   pull_request · 2026-10-27T14:19:45Z
   ## Summary The docs site (`docs/guide/`, the VitePress home) described the v0.4.0 product. This PR corrects what the code contradicts and documents the user-facing features added since v0.4.0. ``` commit A docs: correct the guide for v0.5.0 ├── cards.md:3, getting-started.md:31 …
3. [docs: bring the README up to date for v0.5.0](<https://github.com/yw0nam/YUI/pull/1631>)
   pull_request · 2026-10-27T14:19:38Z
   ## Summary README.md and README.ja.md described the v0.4.0 product. This PR makes both true for `main` (0.5.0) and gives them the same content. ``` README.md / README.ja.md ├── Quickstart chat model is connected during install or later (install.md:41 "Backend (optional)", :109) …
4. [docs: reference, plugin, and glossary docs match the code for v0.5.0](<https://github.com/yw0nam/YUI/pull/1643>)
   pull_request · 2026-10-27T14:17:36Z
   ## Summary Pre-release docs drift fixes for v0.5.0. A read-only audit compared every doc outside the README and the guide with the code at `f871dd4f`; each fix below cites the code it was checked against. The README and guide drift is fixed on #1631 and #1632. | Area | Doc | Was…
5. [fix: the hermes plugin manifest declares the post_api_request hook](<https://github.com/yw0nam/YUI/pull/1641>)
   pull_request · 2026-10-27T14:17:28Z
   ## Summary `register()` in the YUI Hermes platform plugin registers six hooks; `plugin.yaml` declared five under `provides_hooks`. The missing one is `post_api_request`, which fills the `usage` field (`integrations/hermes/platform/yui/__init__.py:64`, `docs/behaviour.md:88-94`).…
6. [\[bug\] The unified chat window cannot be dragged while two characters are open](<https://github.com/yw0nam/YUI/issues/1637>)
   issue · 2026-10-27T07:16:01Z
   ## Symptoms With two or more characters open, the unified chat window does not move when the owner drags it. The only drag handle is the cast row's empty space (`src/ui/unified/cast-chips.ts`, the row's `pointerdown`). The cast chips fill that row, so almost no empty space is le…
7. [fix: the unified window drags from a grip in the cast row and from the box's name plate](<https://github.com/yw0nam/YUI/pull/1639>)
   pull_request · 2026-10-27T07:15:59Z
   ## Summary The unified chat window's only drag handle was the cast row's empty space. Two characters' chips left about 8 to 16px of it, so the window did not move. ``` cast row: [chip][chip][everyone] [grip] [×] grip: 28px round, flex: none box: name plate ── mousedown → startDr…
8. [\[bug\] The History page labels every character's lines "YUI" instead of the character's name](<https://github.com/yw0nam/YUI/issues/1638>)
   issue · 2026-10-27T07:15:56Z
   ## Symptoms The settings window's History page labels each assistant line and each signal line with the fixed string `history.who_yui` ("YUI", "유이"). It does not use the name of the preset whose transcript the page shows. `src/ui/quick-controls/history/history-section.ts:86`: `w…
9. [fix: the History page labels the character's lines with its preset's name](<https://github.com/yw0nam/YUI/pull/1640>)
   pull_request · 2026-10-27T07:15:55Z
   ## Summary The settings window's History page labelled every character line with the fixed `history.who_yui` string ("YUI", "유이", "ユイ"). It now shows the name the edited character goes by, the same name the message window's backlog uses. ``` history-tab.ts characterName: () => e…
10. [\[feature\] The dialogue box types at a fixed rate, independent of the voice](<https://github.com/yw0nam/YUI/issues/1635>)
   issue · 2026-10-27T06:18:33Z
   ## Work description Since #1616 a voiced line in the dialogue box types each sentence only once that sentence's audio starts, over the audio's duration (`src/ui/message/typewriter.ts` `pace()`, DESIGN.md:234). When synthesis lags, the text waits: on 2026-10-27 14:45 (owner's run…
11. [feat: the dialogue box types at a fixed rate, independent of the voice](<https://github.com/yw0nam/YUI/pull/1636>)
   feature · 2026-10-27T06:18:32Z
   ## Summary A voiced line in the dialogue box typed each sentence only once that sentence's audio started (#1616). When synthesis lagged, the text stood still. The line now types at 40 ms per character as its text arrives, voiced or not, and the voice plays on its own. The pacing…
12. [chore: pnpm gates runs every check CI runs with one exit line per gate](<https://github.com/yw0nam/YUI/pull/1633>)
   pull_request · 2026-10-27T05:16:13Z
   ## Summary `pnpm gates` runs every app check CI runs, in order, and prints one line per gate with its exit code; it exits 1 when any gate failed, and a failed gate's line names its log. ``` scripts/ci/gates.sh 13 gates: vitest, typecheck:test, build, biome, map / css / logger / …
13. [\[bug\] A window may paint Dawn for a frame before Hearth under a dark OS](<https://github.com/yw0nam/YUI/issues/1618>)
   issue · 2026-10-27T04:39:33Z
   ## Symptoms Possible: under a dark OS appearance a window that opens may paint Dawn for a frame before `applyTheme` sets `data-theme="hearth"`. `:root` in `src/ui/tokens.css` holds Dawn, and the stored or OS-resolved theme is applied by the window's module script. Since #1617 ev…
14. [fix: the settings window opens on the panel colour of the theme in effect](<https://github.com/yw0nam/YUI/pull/1629>)
   pull_request · 2026-10-27T04:39:32Z
   ## Summary Under Hearth the settings window no longer shows a white frame and then the Dawn panel before its theme paints. ``` settings.html html, body { background: var(--yui-panel-bg) } → html[data-theme], html[data-theme] body { … } io/window/openers/settings-window.ts backgr…
15. [\[feature\] Right-click opens a quick card beside the character; the pet-window settings popover goes](<https://github.com/yw0nam/YUI/issues/1610>)
   issue · 2026-10-27T03:50:46Z
   ## Work description Part of #1599. Mock: https://claude.ai/artifact/AmUmq3aNDkqoNMwYDd8Knd, board "Quick card beside the character". Right-clicking a character opens a small quick card beside her instead of the whole settings panel. The settings panel inside the pet window (the …
16. [feat: right-click opens a quick card in its own window that travels beside the character](<https://github.com/yw0nam/YUI/pull/1625>)
   feature · 2026-10-27T03:50:45Z
   ## Summary Right-clicking the character opens the **quick card** in its own small window beside her, in place of the settings popover. The card is docked: it travels with her (a drag, a stroll, a fall, a climb); dragging its head detaches it, and dropping it within 24px of her l…
17. [\[feature\] The unified chat window names each character once: the cast row picks the recipient](<https://github.com/yw0nam/YUI/issues/1627>)
   issue · 2026-10-27T02:50:18Z
   ## Work description Part of #1599. Mock: https://claude.ai/artifact/DJE9W21SHMcfzZLEAh256m, board "A". The unified chat window shows the same character name in four places: the cast chip, the box's name plate, the quote ("You → Bea @Bea are you up?") and the recipient chip under…
18. [feat: the unified chat window's cast row picks the recipient](<https://github.com/yw0nam/YUI/pull/1628>)
   feature · 2026-10-27T02:50:17Z
   ## Summary The unified chat window names each character once in its controls: the cast row is now the recipient picker, and the recipient chip row under the box is gone. ``` before after [Aki •][Bea •] [×] [Aki •][Bea •][everyone] [×] ← radiogroup: pick here ┌[Bea •]────────────…
19. [\[feature\] Voice goes to the unified window's recipient, and speaking interrupts any character](<https://github.com/yw0nam/YUI/issues/1619>)
   issue · 2026-10-27T02:08:49Z
   ## Work description Part of #1599; second half of #1608 (split out so the window, box and suppression ship first). While the unified chat window is shown, the user's voice goes to the recipient selected in that window, and speaking interrupts whichever character is talking. - Ma…
20. [feat: voice goes to the unified window's recipient, and speaking stops every window](<https://github.com/yw0nam/YUI/pull/1626>)
   feature · 2026-10-27T02:08:48Z
   ## Summary While the unified chat window shows, the user's voice goes to the recipient that window would pick for typed text, the quote carries the mic glyph, and starting to speak stops every window's running turn. ``` main pet window (STT) onVoiceSegment ─ unified shown? ─ yes…
