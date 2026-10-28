---
source: "yui-repo"
date: "2026-10-29"
generated_at: "2026-10-29T08:00:12+09:00"
summary: "YUI repository: 56 updates in the last 24 hours, including closed issues, merged pull requests, features, and review requests for Youngwoo."
sources:
  - {name: "github.com/yw0nam/YUI", status: "ok", last_ok: "2026-10-28T23:00:12Z"}
---

# YUI repository: 56 updates in the last 24 hours, including closed issues, merged pull requests, features, and review requests for Youngwoo.

1. [Bridge tools and the plugin tools line](<https://github.com/yw0nam/YUI/issues/1666>)
   issue · 2026-10-28T15:21:45Z
   Part of #1657 ## Question Build the client side to the bridge contract fixed in "Bridge contract details" (#1664, resolution comment): `plugin_describe`, `plugin_call`, and `plugin_skill` as `ClientTool`s over the host, declared on every transport; the per-turn `plugin tools:` a…
2. [feat: bridge tools reach plugin tools and skills, and every turn lists them](<https://github.com/yw0nam/YUI/pull/1703>)
   feature · 2026-10-28T15:21:44Z
   ## Summary The backend model can now find, describe and call the tools of an enabled YUI-hosted plugin, and read its skills. This works on every transport, through three bridge tools. Every turn also lists what is on offer. ``` pet window (Tauri only) createPetWindowTools ─┬─ … …
3. [Install, update, and remove from the catalog](<https://github.com/yw0nam/YUI/issues/1667>)
   issue · 2026-10-28T13:54:25Z
   Part of #1657 ## Question Start from the quarantine measurement in "Quarantine on files the unsigned app writes and spawns" (#1688). Build catalog fetch, install, update, and remove in the host to "catalog.json schema and the release pipeline": download the platform asset, check…
4. [feat: install, update, and remove plugins from the catalog](<https://github.com/yw0nam/YUI/pull/1702>)
   feature · 2026-10-28T13:54:23Z
   ## Summary The MCP host installs, updates, and removes plugins from the Catalog (`plugins/catalog.json` on main). Before this PR it listed only plugins added from a folder; nothing downloaded or removed a plugin. ``` src-tauri/src/mcp_host/ catalog.rs new: fetch the Catalog (sch…
5. [\[feature\] Reasoning effort Default: send no effort and let the model decide](<https://github.com/yw0nam/YUI/issues/1699>)
   issue · 2026-10-28T07:46:26Z
   ## Work description The client always sends a reasoning effort: `reasoning_effort` on Chat Completions and `reasoning.effort` on Responses (`src/dispatcher/backend/backend-caller.ts:293`, `src/io/chat/stream/chat-completions-stream.ts:108`, `src/io/chat/stream/responses-stream.t…
6. [feat!: reasoning effort Default sends no effort and is the new default](<https://github.com/yw0nam/YUI/pull/1700>)
   pull_request · 2026-10-28T07:46:24Z
   ## Summary The reasoning-effort setting gains `Default`, its new starting value and first segment. With `Default` the client sends no `reasoning_effort` (Chat Completions) and no `reasoning` (Responses), so the backend applies the model's own default. `none`, `minimal`, `low`, `…
7. [\[bug\] Signal details sheet is cut off in a short window, and opening it in the expanded list scrolls the page](<https://github.com/yw0nam/YUI/issues/1678>)
   issue · 2026-10-28T07:34:36Z
   ## Symptoms Found while measuring #1634 (rung 1: the real pet page in headless Chromium, the real `createSignalChips` and `createDelegationChip` mounted into the app's chip column, 3 signal chips plus the delegation chip). 1. **The details sheet is cut at the bottom in a short w…
8. [fix: signal details sheet stays inside the window and opening it never scrolls](<https://github.com/yw0nam/YUI/pull/1697>)
   pull_request · 2026-10-28T07:34:35Z
   ## Summary The signal details sheet stays inside the pet window at any size, and opening it never scrolls the page. ```diff chip.open click openId = id; render() renderDetails() # sheet absolute under the whole chip column setVisible(true) + fitSheet(details.el) # lift so the bo…
9. [\[bug\] Unsigned macOS release is refused as damaged, and the release notes point to Open Anyway](<https://github.com/yw0nam/YUI/issues/1691>)
   issue · 2026-10-28T07:30:11Z
   ## Symptoms The macOS app released without Apple secrets is refused as "damaged" when it carries `com.apple.quarantine` (a Safari download), and the dialog offers no way to open it. The release notes and the build guide tell users to allow it under **System Settings → Privacy & …
10. [fix: sign the macOS bundle ad hoc when no Developer ID certificate is set](<https://github.com/yw0nam/YUI/pull/1696>)
   pull_request · 2026-10-28T07:30:10Z
   ## Summary The release workflow signs the macOS bundle ad hoc when no Developer ID certificate is registered. Today the shipped `YUI.app` is only linker-signed (`Sealed Resources=none`), so a downloaded copy is refused as "damaged" with no Open Anyway. With a sealed ad hoc signa…
11. [Build the Rust MCP host](<https://github.com/yw0nam/YUI/issues/1665>)
   issue · 2026-10-28T07:25:40Z
   Part of #1657 ## Question Build `src-tauri/src/mcp_host/` to the decisions in #1648 and the P0 measurements: plugin → servers from `.mcp.json`; spawn with `${CLAUDE_PLUGIN_ROOT}` / `${CLAUDE_PLUGIN_DATA}` expansion and argv without a shell; startup deadline; bounded stderr tail;…
12. [feat: Rust MCP host for local plugins](<https://github.com/yw0nam/YUI/pull/1693>)
   feature · 2026-10-28T07:25:38Z
   ## Summary YUI now runs local plugins' MCP servers itself. A new Rust part, `src-tauri/src/mcp_host/`, starts each enabled plugin's servers, keeps enablement and consent on disk, publishes a revisioned snapshot to every window, and answers tool calls and skill reads. No TypeScri…
13. [\[feature\] address_character description: hand off only when the user asks, and name handoff in the first sentence](<https://github.com/yw0nam/YUI/issues/1692>)
   issue · 2026-10-28T07:24:11Z
   ## Work description `address_character`'s description decides when a backend model hands the user's message to another character. Today it says "Use handoff when the user's message is better answered by that character", gives the sender no instruction for its own reply, and its …
14. [feat: address_character hands off only when the user asks](<https://github.com/yw0nam/YUI/pull/1695>)
   feature · 2026-10-28T07:24:09Z
   ## Summary `address_character`'s description now: - names both uses in its first sentence (`Talk to or hand off to another character: name who this reply is for.`), so a backend that lists deferred tools by their first sentence (Hermes `tool_search`) still shows that a handoff e…
15. [chore: catalog browser v0.1.0](<https://github.com/yw0nam/YUI/pull/1694>)
   pull_request · 2026-10-28T06:56:48Z
   ## Summary The checks do not start on a PR opened by GITHUB_TOKEN; before merging, run `gh pr close <n> && gh pr reopen <n>` once. Lists browser 0.1.0 in the plugin catalog, from the release https://github.com/yw0nam/YUI/releases/tag/plugin-browser-v0.1.0. ## Related issues N/A …
16. [Quarantine on files the unsigned app writes and spawns](<https://github.com/yw0nam/YUI/issues/1688>)
   issue · 2026-10-28T06:46:18Z
   Part of #1657 ## Question Measure on macOS, with the app as shipped (unsigned, un-notarized): when the app itself downloads a zip over HTTPS, unpacks it into its app data folder, and spawns the unpacked binary, does any written file carry `com.apple.quarantine`, and does the spa…
17. [Browser MCP server crate in plugins/browser](<https://github.com/yw0nam/YUI/issues/1687>)
   issue · 2026-10-28T06:43:21Z
   Part of #1657 ## Question Build the browser MCP server as the official plugin crate `plugins/browser/`, standalone from the host. Port the relay core from `src-tauri/src/browser/` (`relay.rs`, `script.rs`, `locate.rs`, `shots.rs`; only `mod.rs`'s two Tauri commands and `tauri::a…
18. [feat: browser MCP server plugin crate in plugins/browser](<https://github.com/yw0nam/YUI/pull/1690>)
   feature · 2026-10-28T06:43:19Z
   ## Summary A standalone MCP server crate for the ego lite browser, released as the official plugin `browser`. The app's own browser path is untouched; #1670 switches to this plugin and deletes it. ```text plugins/browser/ ├── Cargo.toml, Cargo.lock # package and bin `browser` 0.…
19. [chore: generic example in the reading dictionary placeholder](<https://github.com/yw0nam/YUI/pull/1689>)
   pull_request · 2026-10-28T06:35:29Z
   ## Summary The reading dictionary textarea placeholder showed two real game character names (`秧秧=ヤンヤン`, `穂穂=スイスイ`). It now shows generic examples of the same scripts: `小明=シャオミン` (a Chinese name read in katakana) and `東雲=しののめ` (a kanji word read in hiragana). `src/ui/quick-contro…
20. [\[feature\] Fixed schema for address_character and rate_relation: open characters go in the client context](<https://github.com/yw0nam/YUI/issues/1684>)
   issue · 2026-10-28T06:05:49Z
   ## Work description `address_character`'s `to` and `rate_relation`'s `toward` carry an `enum` of the other open presets' names. The enum is read when the schema is built. On the push transport the schema goes out once, in `hello.tools` (`src/io/chat/push/push-socket.ts:402-410`)…
21. [feat!: open characters go in the client context instead of the tool enum](<https://github.com/yw0nam/YUI/pull/1686>)
   pull_request · 2026-10-28T06:05:48Z
   ## Summary `address_character.to` and `rate_relation.toward` no longer carry an `enum` of the other open presets. Each turn's client context lists them instead, on a new `open characters:` line. ``` before: open presets ──(read when the schema is built)──▶ tools[].to/toward enum…
22. [\[feature\] yui-notify: warn at session start when YUI is unreachable](<https://github.com/yw0nam/YUI/issues/1683>)
   issue · 2026-10-28T05:55:41Z
   ## Work description A yui-notify hook that cannot reach YUI fails silently: it records `last-error.json` and the user hears nothing. Two gaps make this common for an agent on a remote host: 1. The setup's remote branch (`skills/setup/references/remote.md`) uses a per-connection …
23. [feat: yui-notify warns at session start when YUI is unreachable](<https://github.com/yw0nam/YUI/pull/1685>)
   feature · 2026-10-28T05:55:40Z
   ## Summary A yui-notify hook that cannot reach YUI failed silently. Two gaps made this common for an agent on a remote host: the remote setup used a per-connection `RemoteForward`, which an agent in tmux/screen outlives, and the setup probe ran through that same connection's tun…
24. [Bridge contract details](<https://github.com/yw0nam/YUI/issues/1664>)
   issue · 2026-10-28T05:22:58Z
   Part of #1657 ## Question Fix the bridge contract from the prototypes' measurements: final tool names (they must not collide with Hermes's `tool_search` / `tool_describe` / `tool_call`), the `plugin tools:` line format in `docs/reference/client-context.md`, what `plugin_describe…
25. [Official catalog and plugin release assets in CI](<https://github.com/yw0nam/YUI/issues/1669>)
   issue · 2026-10-28T05:20:29Z
   Part of #1657 ## Question Create `plugins/catalog.json` and the CI that builds each official plugin's binary per platform, attaches the assets to a release, and writes their urls and sha256 into the catalog, to the schema decided in "catalog.json schema and the release pipeline"…
26. [ci: release official plugins and list them in the catalog](<https://github.com/yw0nam/YUI/pull/1677>)
   pull_request · 2026-10-28T05:20:28Z
   ## Summary A tag `plugin-<id>-v<version>` now releases one official plugin and lists it in the catalog the app reads. ``` .github/workflows/plugin-release.yml meta tag -> id, version; must match plugins/<id>/Cargo.toml and .claude-plugin/plugin.json build darwin-arm64 (macos-lat…
27. [\[feature\] project-structure.md file tree matches the source again](<https://github.com/yw0nam/YUI/issues/1642>)
   issue · 2026-10-28T05:16:22Z
   ## Work description The file tree in `docs/agent-guide/project-structure.md` no longer matches the source at `f871dd4f`. Bring it up to date. Found by the v0.5.0 docs drift audit; deferred past the release because only contributors and agents read this page. Measured on `f871dd4…
28. [docs: project-structure tree matches the source](<https://github.com/yw0nam/YUI/pull/1681>)
   pull_request · 2026-10-28T05:16:21Z
   ## Summary The Directory Map in `docs/agent-guide/project-structure.md` matches the source again at `f35166ce`. A checker parses the tree block into paths and compares them with `git ls-files src src-tauri/src scripts` (test files and `*test-helpers.ts` excluded): | | before | a…
29. [ci: add the plugin catalog](<https://github.com/yw0nam/YUI/pull/1680>)
   pull_request · 2026-10-28T05:11:22Z
   ## Summary Adds the empty plugin catalog on its own, ahead of #1677, so the plugin release workflow's catalog-PR step can run for real: that step branches from `main` and upserts `plugins/catalog.json`, and the probe run on #1677 failed there because the file did not exist on `m…
30. [\[bug\] Signal chips are cut off when the pet window is small](<https://github.com/yw0nam/YUI/issues/1634>)
   issue · 2026-10-28T05:11:18Z
   ## Symptoms When the pet window is small, the Signal chips beside the character are cut off (reported by the owner on 2026-10-27, `pnpm tauri dev` on main `338a62f6`). ## Steps to reproduce 1. Turn on External signals and restart YUI. 2. Post two or three Signals (for example `y…
