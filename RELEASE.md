# Latest release — movable electromagnet — 2026-10-29

Live URL: https://potentell.com/electromagnets.html

- Deployment dpl_7RBFUy3bky1VteJMUG1LV9pZauD1 is production READY, potentell.com alias assigned with no error.
- Hosting commit db1350ec13fc289b8be764d29ed05d84380b3c99 on codex/electromagnet-drag, based on current production main22ef988974e22c51e73b3ca3ec775f1870c148f5. Preserves newer account-release changes.
- Public HTTP200 verified; served HTML exactly matches the reviewed source including moveMagnet and manual pickup controls.
- Production compilation, types, page generation and asset packaging passed. Existing build configuration skips lint.
- Node syntax and tracked behavior tests passed: pointer contact/lift/end, keyboard cycle, button cycle, no-contact/no-duplicate recording, and prior holder/model/storage regressions.
- Browser rendering/touch-device QA and actual CSV content download remain unverified.

Students can drag the electromagnet onto the tray and raise it above the line. Contact attaches modeled clips; lift records exactly once. Arrow keys and Lower/Lift buttons offer alternatives. Existing one-click pickup remains. Physics model, browser-only storage and holder taps remain unchanged.

Important continuity: an initial deployment from the historical lab branch was canceled before publication when a newer live main release was discovered. Do not deploy the older codex/electromagnet-lab branch over current production. Source is index.html here; hosting copy is public/electromagnets.html in potentellcoding-beep/potentell-website-SSO. Inspect current live source before any future release.

---

## Previous releases (historical)

# Latest production release — 2026-10-29

Live: https://potentell.com/electromagnets.html

## Paperclip pickup + tapped four-D-cell holder
- Deployment dpl_24LRfnaBN5AZ7goWHDTQDrTM5enD, production READY; potentell.com alias assigned, no alias error.
- Website commit e267c17aa3abb902ffb974d5372268e78c3e7c6c on codex/electromagnet-lab.
- Public URL returned HTTP200; returned HTML matched the reviewed source exactly, including the four-cell holder and fieldwork-paperclips-v2 notebook.
- Next.js compiled, checked types, generated pages and packaged assets successfully. Project build skips lint by existing configuration.
- Node syntax and tracked behavior checks pass: all8 setup counts; power-off release/baseline; averages; saved-data restore; invalid/blocked storage; CSV initiation; clearing;200-trial limit; all4 visible cells;1.5/6V lead positions.
- Browser rendering, keyboard interaction in a real browser and downloaded CSV content have not been manually verified.

Added paperclip force estimates, visual pickup, automatic trial log, averages, browser storage, CSV, and holder schematic based on the owner's photo and common/tap explanation. Counts are explicitly illustrative, not empirically calibrated. See docs/MODEL.md.

## History
Initial field-only deployment dpl_3iJkSnkEZzfgJvZZcutk1eWSZzAo at ffde4ba84dbaeccf4cbc7432d830bca4478d7fbc was verified READY/HTTP200 before this update. Intermediate paperclip deployment dpl_9Jw6R4Q3TL6R6K7N7afzBLt3NnYs was canceled to incorporate the holder reference before release.

## Future releases
Canonical source is index.html here; hosting copy is public/electromagnets.html in potentellcoding-beep/potentell-website-SSO. Preserve both and carry this asset into future production branches. Follow AGENTS.md and docs/DEPLOYMENT.md. Do not deploy this standalone repository over the entire PotentELL website.
