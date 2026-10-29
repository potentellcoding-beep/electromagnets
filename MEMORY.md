# Project memory

Last updated: 2026-10-29. This is project continuity documentation, not model-private memory.

## User intent and source
The owner requested an interactive website from https://docs.google.com/presentation/d/1ysgsVUpS5n3CJMXJHc24kjUiYnKyYZFLofS8Lb2qO_w/edit, titled Making an Electromagnet PS 22-23. The presentation is a student activity template with blank answers and data tables, not a completed experimental dataset.

Deck concepts: define an electromagnet; connect series cells for 1.5/3/4.5/6 V; compare 25/50 wire turns; collect two trials and averages; identify independent/dependent variables and constants; explain voltage and turns effects; discuss home applications, permanent magnetism, and a creative magnetic-touch prompt.

The user created potentellcoding-beep/electromagnets and then explicitly requested deployment on potentell.com with a unique URL. Later they requested Markdown for agents, memory, tasks and history so other AI agents can continue work.

## Implemented experience
A standalone green/cream Fieldwork-branded interactive workbench with programmatic SVG core, copper coil, series cells, field lines and moving current. Voltage and turn buttons, power toggle, field-line checkbox, live current/relative-field metrics, contextual explanations, eight notebook rows with two trials each, averages, localStorage, CSV export, clear confirmation, quiz feedback, and expandable everyday-science explanations. The source deck is linked in the footer. No imagery from the deck was copied; its readable text grounded the lesson.

## Decisions
Use fixed resistance and geometry to isolate voltage/turn-count effects. Model values are deterministic, not real measurements; repeated identical setups have identical results. Extra turns in real coils also increase resistance. A real iron core may retain magnetism. Heating and core saturation are discussed but not simulated.

Keep the lab anonymous and independent of teacher sign-in. Store no identity. Device-only trial persistence is explicitly stated. Use a single HTML file so downloads work without a server and hosting needs only one static asset.

## Release and repository relationship
Live: https://potentell.com/electromagnets.html. Main source: index.html here. Hosting copy: public/electromagnets.html in potentellcoding-beep/potentell-website-SSO, branch codex/electromagnet-lab. Current verified release details are in RELEASE.md.

Production was based on live website commit b9286d9a55db6d8903c543daac444d7953f3bcd4. The historical production-version branch no longer resolved remotely, so the agent created the hosting branch from that verified commit and added only the lab and task/handoff documentation. Do not assume website main contains the release; inspect before integrating. A later main-based website release could omit the lab unless it is carried forward.

## Earlier attempts and limitations
A private Sites registration was created (project appgprj_6ae33af55af48191aee9d0a63bcdd491) but no version was deployed because the execution environment's proxy was unreachable. Do not present that Site as live or create duplicates to fix it.

A Google Drive upload was rejected by automatic approval review for destination authorization. No generated HTML was uploaded to Drive. The user then selected GitHub and potentell.com instead.

The execution environment could use connectors but shell Git/HTTP calls failed to connect to proxy:8080. GitHub connector writes and Vercel connector deployment succeeded. No credentials were committed. Browser rendering QA was unavailable; focused JavaScript behavior checks and production HTTP verification passed.

## Paperclip experiment update — 2026-10-29
The user requested visible paperclip lifting as voltage and wraps increase, realistic counts, and an automatically recorded data table saved in the browser without accounts. This explicitly supersedes the fixed-10-ohm, field-only model. New R=2+0.02N accounts for extra wire. Lift uses an effective-gap magnetic-force estimate; constants and lack of experimental calibration appear on the page. 30 clips of 0.5 g each, 20 mm² nail tip, 0.8 mm effective gap, 65% transfer factor, B capped at 1.2 T. Deterministic counts at 1.5/3/4.5/6 V: 25 wraps 0/2/5/9; 50 wraps 1/6/14/26. Zero at the weakest setup models a lifting threshold.

Each pickup, including powered-off baselines, automatically appends voltage, wraps, current, clip count, mass and timestamp. Notebook shows individual trials and per-setup powered averages. Most recent 200 rows persist under fieldwork-paperclips-v2. Old field-only trial data is left separate because field values cannot be converted into observed clip counts. Configuration changes reset the visual pickup; opening the circuit drops clips but preserves historical trials. Invalid persisted rows are rejected; storage failures tell the student to export CSV. Tests are tracked in tests/paperclips.test.cjs. Browser QA remains pending.

## Four D-cell holder reference
The owner supplied a photo of a four-D-cell holder and explained that one electromagnet wire remains on a common connector while the other moves across 1.5/3.0/4.5/6.0V taps. The UI now keeps all four cells visible, dims cells outside the selected circuit, moves the red clip in the SVG, keeps the black common fixed, and exposes labeled tap buttons. It is a teaching schematic, not a photo-accurate wiring diagram or instruction for an unverified physical holder. Tap choices reset the pickup view and synchronize the voltage controls and next trial. Tests verify all four cells and red-lead positions at 1.5/6V.

## Movable electromagnet
Owner asked to move the electromagnet to pick up clips. The lower workbench now has a draggable vertical nail/coil assembly, tray contact zone and lift line. Pointer capture supports mouse/touch; arrows and Lower/Lift buttons are alternatives. Contact snapshots modeled clip capacity, lifting to the threshold records once, and renewed contact permits another trial. Raising without contact does not record. Settings/power reset attached state while preserving history. Existing pickup button runs a full automatic cycle. New tests cover pointer movement/end, keyboard and button cycles and duplicate prevention. Browser QA still pending.

A newer production release at22ef988974e22c51e73b3ca3ec775f1870c148f5 was discovered before publication. The older-branch deployment was canceled; codex/electromagnet-drag starts from that current main release to preserve account changes. Do not publish the outdated codex/electromagnet-lab branch over newer production.

## Paperclip bunch appearance — 2026-10-29
Owner requested picked-up clips bunch into a pile like a real pickup. Lifted clips now use deterministic overlapping positions and varied rotations under the nail tip; cluster grows with clip count and moves with the draggable magnet. Exactly one decorative clip is drawn per modeled lifted clip. Tray layout, physics/counts, recording, CSV and storage unchanged. JS syntax and existing interaction checks pass; browser rendering QA pending. Latest deployment evidence in RELEASE.md.
