# AGENTS.md — Crate — Community Bundles

This repo is part of the Control Room Creations workspace and is edited from multiple machines. The multi-device git protocol below applies to every session. Project-specific guidance can be added below it.

## Multi-device work protocol (Mac Mini + MacBook Neo)

This repo is edited from two machines. **GitHub is the single source of truth.**

### Start of every session (before any edit)
1. `git fetch --all --prune`
2. `git status` — if the working tree is dirty with work you don't recognise, **STOP** and surface it (it may be stranded work from the other device).
3. `git pull --rebase` on the branch you'll work on. If behind `main`, rebase onto it.
4. State which branch you are on and that it is up to date with origin.

### During the session
- Commit in small, logical steps. WIP commits are fine.
- Never leave substantial work uncommitted at a stopping point.
- Work that isn't ready goes on a pushed branch, not a dirty local tree.

### End of every session (before stopping)
1. Commit all intended changes.
2. `git push` the branch.
3. Confirm `git status` is clean and the branch is pushed to origin.
4. If anything is intentionally left uncommitted, say so explicitly.

### Hard rules
- **Never force-push.** Never push directly to `main`; open a PR.
- **Never commit secrets.** Real mechanism: gitignored `.env` files (VPS runtime), macOS keychain, `wrangler secret put`, GitHub Actions secrets. (The old age/sops line was aspirational — no such tooling exists; verified 2026-06-10.)
- If you cannot reconcile divergent state safely, **STOP and ask** — do not guess.

## Public repository scope

- Read `README.md` and `LICENCE.md`. This repository contains the community bundle catalogue consumed by Crate; it does not contain the macOS app or website implementation. Keep private operational notes, credentials, and unpublished submissions out of this public repository.
- `manifest.json` is the client-consumed catalogue. Preserve existing bundle IDs and verify each approved bundle's metadata, HTTPS download URL, file count, size, and SHA-256 against its intended archive. Do not fabricate licence clearance or checksums.
- The local `canary.json` is inert, as documented in `README.md`; editing it does not change Crate's live remote-control manifest.

## Validation and publication

- For a documentation change, check `git diff --check` and verify every referenced repository path. For manifest changes, run `python3 -m json.tool manifest.json >/dev/null` and the schema-validation Python block in `.github/workflows/validate-manifest.yml`.
- That workflow runs on PRs and pushes to `main`. Its PR-only download-URL step contacts the listed HTTPS endpoints; report it separately from offline JSON/schema validation.
- Catalogue changes reach installed clients through `main`. Use a reviewed PR, and obtain explicit owner approval before publishing, replacing, or deleting release archives or changing distribution. A passing schema check does not prove archive contents or permission to redistribute them.
