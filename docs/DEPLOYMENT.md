# Deployment runbook

## Current hosting
Public URL: https://potentell.com/electromagnets.html

This repository's index.html is the standalone source. Production serves the same bytes as public/electromagnets.html in potentellcoding-beep/potentell-website-SSO. There is no GitHub Pages configuration and this repository does not itself deploy the PotentELL domain.

Vercel team: team_pGm1kuXXVridzxQP8QzJl0ss (potentell).
Vercel website project: prj_qp24g2Fbo9DtObzAzfJkNCO1n1sl (potentell-website).
Initial lab production deployment: dpl_3iJkSnkEZzfgJvZZcutk1eWSZzAo.
Hosting commit: ffde4ba84dbaeccf4cbc7432d830bca4478d7fbc.
Hosting branch: codex/electromagnet-lab.

IDs are recorded for continuity, not credentials. Verify the current account, project and live commit before use.

## Update process
1. Read both repositories' AGENTS.md and current task/handoff records.
2. Inspect the deployment currently serving potentell.com, its source commit, and current repository branches. The old production-version ref did not exist on 2026-10-29 even though the previous deployment referenced it.
3. Edit index.html here and run syntax and behavior checks. No dependencies or build step are needed for the lab itself.
4. Copy the exact reviewed HTML to public/electromagnets.html in the website checkout based on current production. Review the diff to preserve unrelated pages, auth, Firestore, Stripe and environment configuration.
5. Follow the website repository's required checks and current user-authorized release process. Deploy the complete website project; never deploy this small standalone repository over the root PotentELL project.
6. Wait for the deployment to become READY, verify potentell.com alias assignment, and fetch /electromagnets.html. Confirm HTTP 200, expected page title/content, and exact source bytes where possible. Perform browser checks when available.
7. Update RELEASE.md, CHANGELOG.md, MEMORY.md, TASKS.md and website handoff/task records. Keep pending checks explicit.

## Initial release evidence
The Vercel build compiled Next.js successfully, checked types, generated pages and packaged public assets. Production returned READY with potentell.com in aliases and no alias error. A connector HTTP fetch returned 200 and expected Electromagnet Lab HTML. Focused JS checks passed; browser rendering QA remains pending.

## Access and fallback
Initial release used authenticated GitHub and Vercel connectors because shell network requests could not reach the environment proxy. Use available connected tools before asking the user for secrets. Never store tokens in these files or repository settings. No Google Drive upload is part of this publishing workflow.

For rollback, identify and verify the previous healthy complete website deployment before changing aliases or promoting it. Do not change DNS or unrelated domain settings to repair a page issue.
