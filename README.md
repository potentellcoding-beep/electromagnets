# Electromagnet Lab

Live: https://potentell.com/electromagnets.html

Open index.html in a modern browser for a standalone copy. No build step, server or account is needed.

Based on the supplied Building an Electromagnet presentation. Students vary voltage (1.5–6 V) and wire wraps (25/50), pick up paperclips, observe the field, and compare automatically recorded trials. The notebook saves the newest 200 trials in this browser, computes averages, and exports CSV. No identity or trial data is sent to a server.

Counts use a simplified magnetic-force model with wrap-dependent wire resistance. These are illustrative estimates under explicit assumptions, not experimentally calibrated predictions for a real nail. Read the in-page model notes and MEMORY.md.

## For contributors and AI agents
Start with AGENTS.md, then MEMORY.md, TASKS.md, CHANGELOG.md, docs/DEPLOYMENT.md and RELEASE.md. These explain history, user intent, model assumptions, hosting, evidence and pending work.

## Verification
Run `node tests/paperclips.test.cjs index.html`. This checks the inline application with DOM stubs; browser rendering QA remains a separate task.

## Hosting
The production copy is public/electromagnets.html in potentellcoding-beep/potentell-website-SSO. Keep both copies identical. Do not deploy this small repository over the entire PotentELL website. Follow docs/DEPLOYMENT.md.
