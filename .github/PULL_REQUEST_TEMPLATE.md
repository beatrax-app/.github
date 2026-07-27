<!--
  Keep the description focused on what changed and why; the diff shows how.
  Contributor guide: https://github.com/beatrax-app/.github/blob/main/CONTRIBUTING.md
-->

## What & why

<!-- One or two sentences, plus the issue this resolves. -->

- Fixes #
- Refs #

## Test plan

- [ ] (a manual or automated step a reviewer can run to verify the change)
- [ ] (edge case covered)
- [ ] (regression check — nothing previously working is now broken)

## Checklist

- [ ] The repo's quality gate is green (for `beatrax`: Pint, Larastan level 10 strict, Pest)
- [ ] Conventional Commit subjects, signed commits, no merge commits
- [ ] `CHANGELOG.md` updated under `## [Unreleased]` if this is user-visible
- [ ] Documentation updated where behaviour changed
- [ ] No `.env`, secrets, or large binary fixtures committed by accident
- [ ] No new network call — or, if there is one, it is optional, off by default, and explained below

## Hippocratic License 3.0 — contribution acknowledgement

beatrax is released under the
[Hippocratic License 3.0](https://github.com/beatrax-app/beatrax/blob/main/LICENSE).
By opening this pull request you confirm that:

- [ ] Your contribution is yours to give (no code from incompatibly licensed
  sources, no employer-owned work without permission).
- [ ] You agree your contribution is licensed under Hippocratic-3.0 as part of
  beatrax.
- [ ] You will not use beatrax — or this contribution — in ways prohibited by
  Hippocratic-3.0 (the "do no harm" clauses; see `LICENSE` for the full list).

## Anything else

<!-- Notes for reviewers, screenshots of UI changes, performance numbers, follow-up work. -->
