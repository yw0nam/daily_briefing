---
source: "yui-repo"
date: "2026-10-27"
generated_at: "2026-10-27T08:00:13+09:00"
summary: "YUI repository: 34 updates in the last 24 hours, including closed issues, merged pull requests, features, and review requests for Youngwoo."
sources:
  - {name: "github.com/yw0nam/YUI", status: "ok", last_ok: "2026-10-26T23:00:13Z"}
---

# YUI repository: 34 updates in the last 24 hours, including closed issues, merged pull requests, features, and review requests for Youngwoo.

1. [\[bug\] the unified chat window's × needs two clicks and Cmd+W does not close it](<https://github.com/yw0nam/YUI/issues/1622>)
   issue · 2026-10-26T18:11:52Z
   ## Symptoms The unified chat window does not close on its first input: - The × needs two clicks when the window is not focused. The first click only activates the window; the second closes it and logs `[wire-unified-close] unified_chat_toggle {"enabled":false,"via":"close"}`. - …
2. [fix: the unified chat window closes on the first click of its close button](<https://github.com/yw0nam/YUI/pull/1624>)
   pull_request · 2026-10-26T18:11:50Z
   ## Summary The unified chat window's × closes it on the first native click, even when the window is not focused. ``` src/io/window/openers/ unified-window.ts + acceptFirstMouse: true message-window.ts + acceptFirstMouse: true unified-window.test.ts, message-window.companion.test…
3. [feat: notices and chips open the settings window on their page](<https://github.com/yw0nam/YUI/pull/1623>)
   feature · 2026-10-26T17:48:28Z
   ## Summary Every place that opened the pet window's settings popover on a page now opens the settings window on that page, and the DevTools row moves to the settings window's General page. This is PR A of #1610; the right-click popover still exists until PR B replaces it with th…
4. [\[feature\] Crop a preset's profile photo to a circle and store the crop area](<https://github.com/yw0nam/YUI/issues/1611>)
   issue · 2026-10-26T17:12:42Z
   ## Work description Part of #1599. Mock: https://claude.ai/artifact/AmUmq3aNDkqoNMwYDd8Knd, board "Profile photo · crop to a circle". Today a picked photo is stored whole (`pick_preset_photo` in `src-tauri/src/card_import.rs`; a JPEG is fitted to 512 px, a PNG kept as is) and ev…
5. [feat: a preset's photo is framed in a circle by a stored crop](<https://github.com/yw0nam/YUI/pull/1621>)
   feature · 2026-10-26T17:12:41Z
   ## Summary A preset's photo gets a stored circular crop, and every face draws it. The manage list's photo button opens a photo dialog (a native modal `<dialog>` in the settings window) to frame it. ``` settings/preset/photo-crop.ts PhotoCrop {x, y, size}: x = left/width, y = top…
6. [\[feature\] Unified chat at message-window size as the only chat path while it is on](<https://github.com/yw0nam/YUI/issues/1608>)
   issue · 2026-10-26T16:49:37Z
   ## Work description Part of #1599. Mock: https://claude.ai/artifact/AmUmq3aNDkqoNMwYDd8Knd, board "Unified chat · message-window size (proposed)". Voice routing and cross-window barge-in are split out to #1619 (second PR). Rebuild the unified chat window at message-window size a…
7. [feat: the unified chat window shows one character's line at a time in a 340px column](<https://github.com/yw0nam/YUI/pull/1620>)
   feature · 2026-10-26T16:49:36Z
   ## Summary While the unified chat window shows (the Unified chat switch on, two or more open presets, a Tauri runtime), every pet window sends its chat over one shared stream, and the unified window plays it in one frameless 340px column. The column holds cast chips, one dialogu…
8. [\[feature\] Dialogue box message window with typing, backlog and a floating motion](<https://github.com/yw0nam/YUI/issues/1607>)
   issue · 2026-10-26T14:24:23Z
   ## Work description Part of #1599. Mock: https://claude.ai/artifact/AmUmq3aNDkqoNMwYDd8Knd, board "A · Dialogue box (one character)". Replace the speech bubble and message window look with a dialogue box, in both the docked mode and the separate message window (the per-character…
9. [feat: the speech bubble becomes a typed dialogue box](<https://github.com/yw0nam/YUI/pull/1616>)
   feature · 2026-10-26T14:24:22Z
   ## Summary The speech bubble becomes a dialogue box in both the character window and the message window: speech types out paced by each sentence's audio, a click on the box shows the rest of the line, a ▼ marks the end, the name plate rides the box's top edge, and a Backlog pill…
10. [feat: the theme follows the OS appearance until the user picks one](<https://github.com/yw0nam/YUI/pull/1617>)
   feature · 2026-10-26T13:21:15Z
   ## Summary A fresh install follows the OS appearance: Hearth under a dark OS, Dawn under a light one. Picking Dawn or Hearth in General → Appearance still pins it. ``` src/settings/appearance/theme-settings.ts defaults: { theme: "dawn" } → { theme: "system" } DESIGN.md the theme…
11. [\[feature\] Character-first settings window: nothing hidden by mode, search, activation with a cap of 4](<https://github.com/yw0nam/YUI/issues/1609>)
   issue · 2026-10-26T12:43:26Z
   ## Work description Part of #1599. Closes #1600. Mock: https://claude.ai/artifact/AmUmq3aNDkqoNMwYDd8Knd, boards "Settings window · character first, nothing hidden" and "Activate characters". Reorganise the settings window around the character, show every control in every transp…
12. [feat: settings pages follow the scope of their controls](<https://github.com/yw0nam/YUI/pull/1615>)
   feature · 2026-10-26T12:43:25Z
   ## Summary The settings panel is regrouped by scope: five pages for the edited character, six for every character. Transport-bound controls stay visible and say why they are off. At most four characters are open at once, and Together → Characters turns each one on or off the des…
13. [\[feature\] Dawn palette as the default theme, Hearth kept as the dark option](<https://github.com/yw0nam/YUI/issues/1606>)
   issue · 2026-10-26T11:59:52Z
   ## Work description Part of #1599. Mock (owner's account): https://claude.ai/artifact/AmUmq3aNDkqoNMwYDd8Knd, boards "Palette" and the `theme` tweak on every board. Add the Dawn palette as the default theme and keep today's Hearth palette as the dark option. - Dawn: light froste…
14. [feat: Dawn palette as the default theme, Hearth as the dark option](<https://github.com/yw0nam/YUI/pull/1614>)
   feature · 2026-10-26T11:59:50Z
   ## Summary Dawn, a light frosted-glass palette under dark ink, is the default theme; Hearth, today's dark scrim under light text, is the dark option; Follow system takes Hearth when the OS appearance is dark. ``` src/ui/tokens.css :root = Dawn · :root[data-theme="hearth"] = Hear…
15. [\[feature\] Remove the Android phone target](<https://github.com/yw0nam/YUI/issues/1612>)
   issue · 2026-10-26T07:55:16Z
   ## Work description Remove the Android phone target. The phone window (`phone.html`, `src/windows/phone-main.ts`, `src/ui/phone/**`, `src/app/phone/**`), the modules only it reaches (the stage background and its Rust import command, the touch camera and stage touch, the Android …
16. [chore: remove the Android phone target](<https://github.com/yw0nam/YUI/pull/1613>)
   pull_request · 2026-10-26T07:55:15Z
   ## Summary The Android phone target is gone. The tree keeps one window family, the desktop one. ``` deleted phone.html · src/windows/phone-main.ts · src/ui/phone/** · src/app/phone/** deleted src/io/assets/stage/** · src/io/lifecycle/** · src/io/stage/touch/** deleted src/settin…
17. [\[spike\] Settings panel information architecture: find a feature without knowing which tab holds it](<https://github.com/yw0nam/YUI/issues/1599>)
   issue · 2026-10-26T07:10:56Z
   ## Uncertainty / question The owner could not find how to open the unified chat window after making a third preset (2026-10-26). The switch exists: it is the **Unified chat** row in the Talk tab, in the first group under the reasoning-effort row (`src/ui/quick-controls/template.…
18. [chore: worktree setup installs node_modules, and a title edit reruns the PR-title check](<https://github.com/yw0nam/YUI/pull/1605>)
   pull_request · 2026-10-26T06:44:52Z
   ## Summary ```diff scripts/worktree-setup.sh <worktree> link VRM, motions, .claude; copy .env.local + package.json present and no node_modules → pnpm install --frozen-lockfile --prefer-offline .github/workflows/ci.yml - pr-title job (pull_request: opened, synchronize, reopened) …
19. [\[feature\] Card import and export carry the preset's filler phrases](<https://github.com/yw0nam/YUI/issues/1589>)
   issue · 2026-10-26T06:19:32Z
   ## Work description A preset's filler phrases are part of the character's voice, but a card does not carry them. Today `registry.create` copies the window preset's `yui.filler` key into a new preset (`src/settings/preset/preset-registry.ts:74-78`, `PRESET_COPIED_KEYS` in `src/se…
20. [feat: card import and export carry the preset's filler phrases](<https://github.com/yw0nam/YUI/pull/1603>)
   feature · 2026-10-26T06:19:30Z
   ## Summary A card carries the preset's filler phrases under `data.extensions.yui.filler` (Tavern Card V2, the app's own extension key, the shape of `FillerSettings.customPools`). Import writes them into the new preset's filler settings; export writes the preset's pools back. ```…
21. [docs: an addressed turn records no user half in the receiver's transcript](<https://github.com/yw0nam/YUI/pull/1604>)
   pull_request · 2026-10-26T06:13:26Z
   ## Summary ```diff -The receiver's transcript records the background marker as the turn's user half, -so the user's message appears once in the unified chat window. +On Chat Completions and Responses the receiver's request carries the background +marker as its user message; on p…
22. [\[feature\] Unified chat: a typed @name or @everyone without a pick routes like a pick](<https://github.com/yw0nam/YUI/issues/1590>)
   issue · 2026-10-26T06:12:16Z
   ## Work description #1583 decided that a typed `@name` without an autocomplete pick stays plain text and routes by the no-`@` rule (to the last speaker). In use this sends a message to the wrong character, and the right one never hears it. Observed on 2026-10-26 with two open pr…
23. [feat: a leading typed @name routes like a pick, and Tab picks in the @ list](<https://github.com/yw0nam/YUI/pull/1601>)
   feature · 2026-10-26T06:12:14Z
   ## Summary In the unified chat window, a leading typed `@name` routes like a pick, the target chip follows it while the user types, and Tab picks the highlighted option in the @ list. ```diff composer field input + chipTarget() = countedMention(pick, cast) ?? typedMention(field,…
24. [\[feature\] Stream a running reply into the unified chat window](<https://github.com/yw0nam/YUI/issues/1586>)
   issue · 2026-10-26T06:02:15Z
   ## Work description The unified chat window (#1583) adds a row when a turn is recorded in its preset's transcript, so a reply shows only once it is complete. A reply should stream into the window the way it streams into the speech bubble: the row for the running turn appears on …
25. [feat: a running reply streams into the unified chat window](<https://github.com/yw0nam/YUI/pull/1602>)
   feature · 2026-10-26T06:02:14Z
   ## Summary A running reply streams into the unified chat window: its row appears on the first pushed text, grows, and is replaced by the transcript record when the turn is recorded. ```diff pet window speech-playback delta(text, identity) - surfaces.beginSpeech() / pushSpeech(te…
26. [\[feature\] Device-wide reading dictionary applied to speech text before TTS](<https://github.com/yw0nam/YUI/issues/1594>)
   issue · 2026-10-26T05:45:54Z
   ## Work description The owner reports that the Japanese TTS does not read the character names 秧秧 and 穂穂 as ヤンヤン and スイスイ. The persona workaround (2026-10-26) writes those names in katakana in the Hermes SOUL.md files and the cards. That keeps the speech right, but it also change…
27. [feat: a reading dictionary rewrites the text sent to the TTS service](<https://github.com/yw0nam/YUI/pull/1598>)
   feature · 2026-10-26T05:45:53Z
   ## Summary A device-wide **Reading dictionary** rewrites the text sent to the TTS service; the bubble keeps the original. The Japanese TTS reads 秧秧 as ヤンヤン without a katakana name in the persona or the card. ```diff wireVoicePipeline + readings = createReadings(() => readingsSet…
28. [\[feature\] Handoff: address_character passes the user's message to the receiving character](<https://github.com/yw0nam/YUI/issues/1595>)
   issue · 2026-10-26T05:45:46Z
   ## Work description A character that receives a user message better suited to another open character hands it over. The sender's backend decides to hand over. The client routes and labels. `address_character` (#1584) already routes a turn to the named character, but its contract…
29. [feat: address_character hands the user's message to another character](<https://github.com/yw0nam/YUI/pull/1597>)
   feature · 2026-10-26T05:45:45Z
   ## Summary `address_character` gains an optional `handoff: boolean`. With it, the receiving character's trigger carries the user's message of the sender's turn, verbatim, and she answers the user. ```diff sender window dispatcher admits user turn + turn.userText = userTextOf(env…
30. [\[bug\] Push mode hides the whole card section, so Import card… and the greeting fields are unreachable](<https://github.com/yw0nam/YUI/issues/1592>)
   issue · 2026-10-26T05:45:38Z
   ## Symptoms With a preset whose chat transport is push, the Card section is hidden in the Talk tab, in the pet window's quick controls and in the settings window (both build the panel with `createQuickControls`, `src/app/settings-window/wire-settings-window.ts:216`). The section…
