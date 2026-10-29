# Agent guide

Read README.md, MEMORY.md, TASKS.md, CHANGELOG.md, docs/DEPLOYMENT.md, and RELEASE.md before changing this project.

## Purpose
Interactive classroom lesson adapted from the owner's Google Slides presentation. Teach current-driven magnetism, series battery voltage, coil turns, fair tests, and evidence-based conclusions. The user explicitly requested this repository and publication at a unique potentell.com URL.

## Files and source of truth
- index.html is the complete standalone application, including CSS and JavaScript. No build system or server is required.
- This repository owns the lab source. The hosting copy is public/electromagnets.html in potentellcoding-beep/potentell-website-SSO.
- Live URL: https://potentell.com/electromagnets.html.
- Do not deploy this standalone file as a replacement for the whole PotentELL website. Follow docs/DEPLOYMENT.md.

## Product and science constraints
Students remain anonymous. No accounts, names, rosters, remote progress storage, or tracking. Trial values stay in localStorage; CSV export is browser-local. Label storage truthfully.

Use 1.5, 3.0, 4.5, 6.0 V and 25/50 turns, matching the deck. The simplified model holds resistance at 10 ohms and core/coil geometry constant: I=V/R and relative field=(V/1.5)*(turns/25) when powered, zero when open. Clearly retain assumptions: real wire adds resistance; heating and saturation are omitted. Never describe modeled outputs as measured experimental data or predict paperclip counts from this model.

Keep keyboard support, visible focus, reduced-motion support, responsive layout, model caveats, source attribution, trial averages, CSV export, and quiz feedback.

## Working practice
Read the current hosting repository AGENTS.md before editing it. Inspect current live deployment and remote branches; do not assume a historical branch still exists. Base hosting changes on verified current production, preserve unrelated work, and review differences before release. User publication authorization in this session covered the initial lab; follow the current user's scope for future releases. Never store credentials in code, Markdown, commits, logs, or command arguments.

After a change, run proportionate syntax and behavior checks, then verify the real public URL after deployment. Report browser QA limitations honestly. Update MEMORY.md, TASKS.md, CHANGELOG.md, RELEASE.md and deployment notes when relevant. Record pending work explicitly; do not claim checks ran when they did not.
