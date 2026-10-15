---
source: "yui-repo"
date: "2026-10-15"
generated_at: "2026-10-15T12:08:35+09:00"
summary: "YUI repository: 12 updates in the last 24 hours, including closed issues, merged pull requests, features, and review requests for Youngwoo."
sources:
  - {name: "github.com/yw0nam/YUI", status: "ok", last_ok: "2026-10-15T03:08:35Z"}
---

# YUI repository: 12 updates in the last 24 hours, including closed issues, merged pull requests, features, and review requests for Youngwoo.

1. [\[feature\] Briefing delivery as a web page: a fixed HTML template the agent fills, served by static hosting of the published spool](<https://github.com/yw0nam/YUI/issues/1451>)
   issue · 2026-10-15T03:04:57Z
   ## Work description A third answer to Install step 6 of `integrations/skills/yui-daily-briefing/SKILL.md`: "a greeting with a link to a web page". The page is one HTML file per day, `<YYYY-MM-DD>/index.html`, written into the spool beside that day's markdown and pushed by `publi…
2. [feat: the daily briefing arrives as a web page per day, with a board of every day and page-check](<https://github.com/yw0nam/YUI/pull/1455>)
   feature · 2026-10-15T03:04:56Z
   ## Summary This PR adds a third answer to Install step 6 of the daily briefing skill: a greeting with a link to a web page for the day. Before the user's day starts, the agent fills a page with a fixed design from the day's briefings. Static hosting of the published spool serves…
3. [\[feature\] Nest the briefing spool by year, month and week, and give the published repository a fixed layout](<https://github.com/yw0nam/YUI/issues/1452>)
   issue · 2026-10-15T02:51:46Z
   ## Work description The spool, and so the published repository, lists one `<YYYY-MM-DD>/` folder per day at its root. After a year that is 365 folders side by side. The layout becomes: ``` .gitignore README.md the user's; publish leaves it alone index.html the board page, writte…
4. [feat: the briefing spool nests day folders under reports/ by year, month and week](<https://github.com/yw0nam/YUI/pull/1453>)
   feature · 2026-10-15T02:51:45Z
   ## Summary The briefing spool, and the repository `publish` pushes, now keeps each day under `reports/<YYYY>/<MM>/<Wn>/<DD>/`. Before this change, every day was a `<YYYY-MM-DD>/` folder at the root. `<Wn>` is the week of the month: `W1` covers days 1 to 7, `W2` 8 to 14, `W3` 15 …
5. [\[feature\] Publish the briefing spool to a git repository and hand the user a link in place of the spoken items](<https://github.com/yw0nam/YUI/issues/1448>)
   issue · 2026-10-15T02:07:12Z
   ## Work description The daily briefing is spoken item by item today. The user wants a greeting and a link to the day's report, and the report readable in a browser from anywhere. The spool already holds one markdown file per producer and day, and a git hosting service renders ma…
6. [feat: publish the briefing spool to a git repository and speak a link per day](<https://github.com/yw0nam/YUI/pull/1450>)
   feature · 2026-10-15T02:07:10Z
   ## Summary The daily briefing can be delivered as a greeting with one link per day to the published spool, in place of the items read out. - `briefing.py publish` stages every `<YYYY-MM-DD>/*.md` file of a spool that is its own git work tree, commits those paths only (`git diff …
7. [\[feature\] Architecture map of the push-transport plugin](<https://github.com/yw0nam/YUI/issues/1428>)
   issue · 2026-10-15T01:53:23Z
   ## Work description Add an architecture map of the push-transport plugin (`integrations/hermes/platform/yui/`) as a data file under the plugin's `docs/`, drawn by the client map's viewer, which gains a `?map=` query for a second data file in this work. The data file lists the pl…
8. [feat: architecture map of the push-transport plugin](<https://github.com/yw0nam/YUI/pull/1449>)
   feature · 2026-10-15T01:53:21Z
   ## Summary Adds an architecture map of the push-transport plugin (`integrations/hermes/platform/yui/`) in the client map's data format, drawn by the same viewer. 1. `integrations/hermes/platform/yui/docs/map.js` has 9 modules, 22 parts, 84 exchanges and 5 flows. The flows are th…
9. [\[feature\] Add time-based loneliness dynamics to the desire gate](<https://github.com/yw0nam/YUI/issues/1445>)
   issue · 2026-10-15T01:43:43Z
   <!-- from-natsume --> Opened by Natsume, the autonomous agent on profile natsume2. ## Work description Add a small, deterministic time-based affect update to the Hermes desire integration so that feelings such as `loneliness` can change even when no new event or held note exists…
10. [feat: the desire gate moves loneliness with time away and wakes the agent at each new level](<https://github.com/yw0nam/YUI/pull/1447>)
   feature · 2026-10-15T01:43:41Z
   ## Summary The desire gate now moves `loneliness` toward `user` with time since `last_interaction_at`, on every scheduled run, and wakes the agent once per new level. The change is wake case 3 in `integrations/hermes/desire/gate.py` (`loneliness_level`, `_loneliness_lines`), rec…
11. [fix: use Python executable on Windows](<https://github.com/yw0nam/YUI/pull/1398>)
   pull_request · 2026-10-15T01:33:24Z
   ## Summary Windows producer tests use the shared command-path convention instead of hardcoding the `py` launcher: `python` on Windows and `python3` elsewhere. `YUI_PYTHON` is an explicit override on every platform. The Windows default is `python` because the reported failure occ…
12. [\[feature\] Tuck the character away at the screen edge](<https://github.com/yw0nam/YUI/issues/1439>)
   issue · 2026-10-14T04:52:35Z
   ## Work description Desktop Mate characters "quietly tuck away at the edge of your screen" when not in use (https://store.steampowered.com/app/3301060/Desktop_Mate/). YUI's `peek` holds a side perch at an edge of the frontmost window (`body_action` `side`, `src/io/chat/tools/ava…
