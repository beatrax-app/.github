# Security policy

beatrax holds a person's complete banking history on their own machine. That
class of data has real consequences if something goes wrong, so reports are
taken seriously and routed privately so a fix can ship before the issue is
public.

## Reporting a vulnerability

**Please do not report security vulnerabilities through public issues.**

Use GitHub's private vulnerability reporting on the affected repository — the
**Security** tab → **Report a vulnerability**. For the application itself that
is
[beatrax-app/beatrax/security/advisories/new](https://github.com/beatrax-app/beatrax/security/advisories/new).

Include, where you can:

- The repository and version affected
- A description of the vulnerability and its impact
- Steps to reproduce
- Any suggested remediation

The report stays private between you and the maintainers until a fix ships and
a coordinated disclosure is published. If private reporting is disabled or
inaccessible to you, do not open a public issue with the details — reach out
privately first and we'll re-enable the flow.

## The ones that matter most

Two classes outrank everything else:

- **Local data at rest.** The SQLite database, the passphrase-derived at-rest
  key gated behind the app lock, and the encryption of stored OAuth tokens.
- **The sync path.** Device pairing and identity (Ed25519 / X25519), the
  encrypted transport, and the store-and-forward relay. The relay is
  zero-knowledge by design: any way to make it hold, infer or leak plaintext is
  a high-severity finding, as is any way to get a device confirmed into a sync
  group without the safety-number check.

## Scope

**In scope:** the application code in these repositories; the bundled PHP
dependencies where the vulnerability is reachable through beatrax's own usage;
the Electron/NativePHP shell in the released installers; the auto-update path
(Ed25519 manifest signing plus SHA-512 binary verification); the local
data-at-rest assumptions; and the sync and pairing stack.

**Out of scope:** vulnerabilities in third-party services beatrax talks to
(Gmail API, Microsoft Graph, an open-banking aggregator, your OS) unless
triggered exclusively by a flaw in beatrax's handling; operating-system-level
security on the user's machine, which beatrax assumes is uncompromised; social
engineering of the maintainers or of GitHub; issues requiring a user to grant
beatrax destructive permissions on their own machine deliberately; and
theoretical risks with no demonstrable reproduction.

## Safe harbour

Good-faith security research is welcome. If you report through the private
channel, don't exploit beyond what's needed to demonstrate the issue, don't
access data that isn't yours, and don't disclose before the coordinated date,
the maintainers will not pursue legal action.

## Response timeline

| Stage | Target |
| ------- | -------- |
| Acknowledgment of report | within 7 days |
| Triage decision (in scope, severity, planned fix window) | within 14 days |
| Patch ships or detailed status update | within 60 days |
| Public disclosure (coordinated with reporter) | 90 days from acknowledgment, unless extended |

These are targets, not guarantees — beatrax is maintained by a small team in
their spare time. If something slips, we'll tell you why. If you need to
disclose sooner because of an exploit in the wild, say so and we'll work out an
accelerated timeline together.

## Credit

Reporters who follow this policy and want public credit will be named in the
release notes for the patched version, or in the advisory. Reporters who prefer
anonymity will be respected.
