# Contributing to beatrax

Thank you for wanting to contribute. This is the org-wide guide; the
[beatrax repository](https://github.com/beatrax-app/beatrax) has its own
[CONTRIBUTING.md](https://github.com/beatrax-app/beatrax/blob/main/CONTRIBUTING.md)
with the setup steps, the module boundary rules and the quality gate. Read that
one before writing application code — this one covers what applies everywhere.

## You don't have to write code

The most valuable contributions often aren't code:

- **Try it and report what broke** — a clear bug report saves everyone time.
- **Fix or improve docs** — spot something unclear and fix it; a docs PR counts.
- **Translate** — the interface and README ship in English and Dutch; more are
  welcome.
- **Design & accessibility feedback** on any surface in the app.

If you're unsure whether an idea fits, open a
[Discussion](https://github.com/beatrax-app/beatrax/discussions) before sinking
effort into a pull request. We'd rather agree on shape early than ask you to
rework a finished branch.

## The constraint that doesn't move

**beatrax is local-first. Nothing may phone home.**

No telemetry, no analytics, no cloud account, no server that sees a user's
data. Sync between a user's own devices is peer-to-peer and end-to-end
encrypted; the optional relay only ever holds ciphertext. Any contribution that
adds a network call has to justify itself against that, and it has to be
optional and off by default — that's how the open-banking connector landed.

If a change would weaken this, it isn't a pull request, it's a conversation.

## Ground rules across every repo

- **Conventional Commits.** `<type>(<scope>): <subject>`, where `<type>` is
  `feat`, `fix`, `chore`, `docs`, `refactor`, `test` or `perf`.
- **Branch names** follow `<type>/<short-slug>`, e.g.
  `feat/counterparty-profile-tabs`.
- **Signed commits** are required on `main`. Set `git config commit.gpgsign true`
  with a key registered on your GitHub account before you push.
- **Linear history** on `main` — no merge commits. PRs are squashed or rebased.
- **Changelog entries** for user-visible changes. `CHANGELOG.md` is the single
  source of truth for release notes; an omitted entry simply will not appear in
  the release.
- **No secrets, no `.env`, no large binary fixtures** in a commit.

## Before you open a PR

- Tests pass and the repo's own quality gate is green. For `beatrax` that is
  Pint, Larastan level 10 strict and Pest — see its CONTRIBUTING.
- Documentation is updated where behaviour changed.
- The PR template is filled in, including the licence acknowledgement.

## Licence and conduct

Contributions are licensed under the
[Hippocratic License 3.0](https://github.com/beatrax-app/beatrax/blob/main/LICENSE)
as part of beatrax — a source-available licence with ethical-use clauses. The
reasoning is in
[NOTICE.md](https://github.com/beatrax-app/beatrax/blob/main/NOTICE.md).
By participating you also agree to the [Code of Conduct](CODE_OF_CONDUCT.md).

## Questions

Ask in [Discord](https://discord.gg/FYuV9CbTHR) for anything conversational, open a
[Discussion](https://github.com/beatrax-app/beatrax/discussions) for something
worth keeping, or file an issue. If you're not sure which repo an issue belongs
in, file it anywhere — routing is our job, not yours.
