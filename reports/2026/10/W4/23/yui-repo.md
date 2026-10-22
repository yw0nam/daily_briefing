---
source: "yui-repo"
date: "2026-10-23"
generated_at: "2026-10-23T08:00:12+09:00"
summary: "YUI repository: 12 updates in the last 24 hours, including closed issues, merged pull requests, features, and review requests for Youngwoo."
sources:
  - {name: "github.com/yw0nam/YUI", status: "ok", last_ok: "2026-10-22T23:00:12Z"}
---

# YUI repository: 12 updates in the last 24 hours, including closed issues, merged pull requests, features, and review requests for Youngwoo.

1. [\[spike\] Conversation between backend agents behind different presets: what is the client's share](<https://github.com/yw0nam/YUI/issues/1509>)
   issue · 2026-10-22T11:55:37Z
   ## Uncertainty / question Should backend agents behind different presets be able to **talk to each other** (one character reacting to what another said, relationships such as rivalry or cooperation), and what is the client's share of it? Facts from the current tree: - No wire fr…
2. [\[feature\] A pet window holds its turns while another window's turn is in flight](<https://github.com/yw0nam/YUI/issues/1537>)
   issue · 2026-10-22T11:55:36Z
   ## Work description A pet window holds its turns while another pet window's turn is in flight. The gate is an exclusive Web Lock `yui.turn` (the same mechanism as the `yui.speaking` voice lock from #1528): a window takes it just before its backend call and releases it once the c…
3. [\[feature\] A character's turn carries the other open presets' user↔character lines as an overheard block](<https://github.com/yw0nam/YUI/issues/1536>)
   issue · 2026-10-22T11:55:35Z
   ## Work description Before a character's turn, the window reads the other open presets' user↔character lines and renders them into `client_context` as an `overheard:` block. Each pair (this preset → other preset) keeps a watermark, the timestamp of the last transcript entry alre…
4. [feat: a turn carries the other open presets' lines, and a pet window takes the turn lock before its backend call](<https://github.com/yw0nam/YUI/pull/1542>)
   feature · 2026-10-22T11:55:34Z
   ## Summary A pet window's turn carries the lines the other open characters exchanged with the user since this character last heard them, and a pet window waits for another window's turn to end (call and playback) before it calls its own backend. ``` io/chat/conversation/overhear…
5. [\[feature\] The settings window edits any preset: an edit target in the strip, and main's character switched from the manage popover](<https://github.com/yw0nam/YUI/issues/1533>)
   issue · 2026-10-22T03:32:28Z
   ## Work description Today the preset `<select>` at the top of the settings window is the switch for main's character. A preset whose own pet window is open is disabled in it, so its connection, voice, history and VRM can only be changed from that window's own settings window. Th…
6. [feat: the settings window edits any preset, and main's preset is switched from the manage popover](<https://github.com/yw0nam/YUI/pull/1535>)
   feature · 2026-10-22T03:32:27Z
   ## Summary The settings window picks the preset it edits, independent of the preset main shows. Switching main's preset moves to a "Use in main" button in the manage popover. The quick-controls popover inside pet windows keeps today's behaviour (its select switches main). ``` se…
7. [chore: three TTS synths in flight per window](<https://github.com/yw0nam/YUI/pull/1534>)
   pull_request · 2026-10-22T03:32:21Z
   ## Summary `configs/endpoints.json` `tts_max_inflight`: 1 → 3. One pet window now keeps up to three sentence synths in flight instead of one. ``` configs/endpoints.json tts_max_inflight 1 → 3 src/io/voice/tts/tts-synth.ts the 30 s comment no longer calls the server serial ``` Wh…
8. [docs: the client routes and directs, the backend writes the words](<https://github.com/yw0nam/YUI/pull/1532>)
   pull_request · 2026-10-22T02:28:29Z
   ## Summary The core principle sentence in `AGENTS.md` and the matching anti-pattern bullet in `CONTRIBUTING.md` said the client "never invents a speak/don't-speak gate". Agents read that as a ban on any client-side choice about who speaks, which blocked ordinary routing designs …
9. [\[feature\] Multi-preset fixes: camera per preset, window geometry per window, 30 s TTS deadline, preset name on the message plate](<https://github.com/yw0nam/YUI/issues/1527>)
   issue · 2026-10-22T00:52:53Z
   ## Work description Four defects the owner hit with several presets open at once: 1. The camera zoom and orbit (`yui.camera`) are device-wide, so changing the model size in one pet window changes it in every window. Make the camera a preset's own key, copied when a preset is cre…
10. [feat: camera per preset, window geometry per window, a 30 s TTS deadline, and the preset name on the message plate](<https://github.com/yw0nam/YUI/pull/1529>)
   feature · 2026-10-22T00:52:52Z
   ## Summary Four defects the owner hit with several presets open at once, each fixed where it lives. ``` settings/preset/preset-keys.ts PRESET_COPIED_KEYS += "yui.camera" (1) camera is the preset's own io/voice/tts/tts-synth.ts TTS_SYNTH_TIMEOUT_MS 10_000 → 30_000 (2) serial TTS …
11. [\[feature\] One voice at a time across pet windows](<https://github.com/yw0nam/YUI/issues/1526>)
   issue · 2026-10-22T00:52:35Z
   ## Work description With several bound pet windows open, each window runs its own TTS pipeline, so two characters can speak at the same time once the TTS server answers requests in parallel. Overlapping voices are unintelligible. Add a device-wide switch "One voice at a time" (d…
12. [feat: one voice at a time across pet windows](<https://github.com/yw0nam/YUI/pull/1528>)
   feature · 2026-10-22T00:52:34Z
   ## Summary With several bound pet windows open, each window plays its own TTS, so two characters could speak at once. This PR adds a device-wide switch "One voice at a time" (default on) and a cross-window gate on playback. ``` settings-stores.ts oneVoiceSettings (yui.one-voice,…
