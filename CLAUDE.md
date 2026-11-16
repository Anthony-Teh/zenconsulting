# Zen Consulting website (zenconsulting.co.nz)

Hugo site. GitHub repo: AZJTZC/zenconsulting.
Pushing to `main` deploys the live site via GitHub Actions (.github/workflows/main.yml).

## How Rowan works
- Rowan edits site files in VS Code on the `test` branch and previews them at http://localhost:1313/ (`npm run test`).
- Rowan doesn't use GitHub directly. Claude handles all git and GitHub work: committing, pushing, pull requests, merging and checking deploys.
- Don't edit site files unless Rowan asks.

## Releasing test to main ("push to live", "push test to main")
1. Make sure the `test` branch is checked out.
2. If there are uncommitted changes, list them in plain words and commit them on `test` with a short descriptive message. Skip Office temp files (`~$*`) and ask about anything that looks accidental.
3. Push `test` to GitHub (`git push origin test`).
4. Summarise what will go live: the commits and changed files in `main..test`, in plain language.
5. Wait for Rowan's OK, then open a pull request from `test` into `main` and merge it (`gh pr create` / `gh pr merge`).
6. Watch the "Deploy Hugo site to Pages" run (`gh run watch`) and report whether it succeeded; if it failed, explain why in plain words.
7. Bring local `main` up to date, merge `main` back into `test` so they match, push `test`, and leave `test` checked out.

## Rules
- Never commit directly to `main` or force-push.
- Never merge into `main` without Rowan's explicit OK.
- Explain git/GitHub outcomes in plain language; Rowan isn't a GitHub user.
