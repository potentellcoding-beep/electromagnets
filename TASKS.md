# Task ledger

Updated 2026-10-29.

## Completed
- Read the supplied Google Slides deck through the connected Google Drive tool.
- Build a standalone interactive electromagnet lab matching voltage and turns activities.
- Add current and relative-field visualization, circuit power, deterministic repeated trials, averages, local notebook storage, CSV export, and quiz feedback.
- Save source in this user-selected repository.
- Add hosting asset on codex/electromagnet-lab from verified prior production commit in potentell-website-SSO.
- Complete Vercel production build and publish at https://potentell.com/electromagnets.html.
- Verify production READY, domain alias assignment and HTTP 200 containing expected lab HTML.
- Add agent, memory, task, change and deployment documentation.

## Verification completed
JavaScript syntax check (node --check) passed. A Node VM harness with DOM stubs checked initial 3 V/0.30 A state, increasing to 6 V/0.60 A, changing to 50 turns/8x relative field, two saved trials and average, open-circuit zero current/hidden field, rejecting powered trial recording while open, and correct quiz feedback. Production Next.js compilation, type checking and static generation completed successfully. The harness was a workspace verification aid; it is not a browser test and is not tracked here.

## Pending / next tasks
- Browser QA at desktop and narrow mobile widths: layout, keyboard traversal, reduced motion, SVG animation, no console errors.
- Browser QA of persistence after reload, both trial slots for all eight configurations, CSV download content, and clear confirmation.
- Integrate the website hosting branch into the owner's chosen long-term production branch before future releases, after comparing current branches and avoiding unrelated changes. Initial production is already live; this is repository maintenance, not a deployment blocker.
- Optional future work only when requested: physical-resistance model, reverse polarity, additional experiments, or branding changes.

## Acceptance for future edits
Preserve correct scientific assumptions, anonymous browser-only storage, source attribution, all supported settings, and the live URL. Verify source and hosting copy match. Record exact checks and any limits in RELEASE.md and CHANGELOG.md.

## Paperclip pickup enhancement — implemented 2026-10-29
- Visible 30-clip tray and nail-tip pickup bundle; changing voltage/wraps changes modeled lifting capacity.
- Power off releases clips and permits zero-current baseline recording.
- Every pickup automatically records a row; summary averages by voltage and wraps; CSV export; browser-only persistence of newest 200 trials.
- Added wire resistance and explicit effective-gap force model. Counts plausible under stated assumptions, not experimentally calibrated.
- `node tests/paperclips.test.cjs index.html` passes all eight setup counts, monotonic effects, release/baseline, averages, reload, invalid saved data, blocked storage, CSV initiation, quiz, clear and retention cap. Inline JS syntax checked.
- Production release verification: see RELEASE.md. Full browser visual and download-content QA remains pending.

## Movable electromagnet — 2026-10-29
Implemented pointer/touch/arrow movement and Lower/Lift buttons. Only contact followed by lifting records a trial; repeat lift alone does not. Power off releases clips. Regression tests pass pointer cycle/end, keyboard cycle, button cycle and all existing model/storage checks. Browser visual QA remains pending. Hosting branch is now codex/electromagnet-drag, based on current main production22ef9889; latest release evidence in RELEASE.md.
