<p align="center">
  <img alt="beatrax" src="../.github/logo.png" height="96">
</p>

<h1 align="center">Your money, in one picture &mdash; on your own machine</h1>

<p align="center">
  A local-first personal finance dashboard that pulls your banks, cards, PayPal
  and subscriptions into a single calm view. No telemetry, no cloud sync,
  no remote account.
</p>

<p align="center">
  <img alt="Licence" src="https://img.shields.io/badge/licence-Hippocratic%203.0-3E4C59">
  <img alt="Status" src="https://img.shields.io/badge/status-v1.3%20shipped%20%C2%B7%20v2.0%20in%20development-E9A93B?labelColor=3E4C59">
  <img alt="Platforms" src="https://img.shields.io/badge/macOS%20%C2%B7%20Windows%20%C2%B7%20Linux-8A9BA8?labelColor=3E4C59">
  <img alt="Stack" src="https://img.shields.io/badge/Laravel%2013%20%C2%B7%20PHP%208.5%20%C2%B7%20SQLite-777bb4?labelColor=3E4C59">
  <a href="https://discord.gg/FYuV9CbTHR"><img alt="Discord" src="https://img.shields.io/badge/chat-Discord-5865F2?labelColor=3E4C59"></a>
</p>

---

## The problem it kills

Money that lives in one bank is easy. Money that lives across two banks, a
credit card, PayPal and a fistful of app-store subscriptions is not — and the
only tool most people have for it is a spreadsheet rebuilt every month.

The usual fix is to hand a third party read access to every account you own.
beatrax takes the other route: it reads the statement files your bank already
exports, on your machine, and never phones home.

```console
$ # everything beatrax knows lives here, and only here
$ ls ~/Library/Application\ Support/beatrax/
database.sqlite
```

## What it actually does

- **Reads the formats European banks already export** — CAMT.053 (ISO 20022),
  MT940 and CSV — so it is not tied to one institution. Plus ICS credit-card
  PDF statements and PayPal CSV.
- **Optional email-receipt scanning** via Gmail or Microsoft Graph, so an
  app-store charge on your card gets matched to the receipt that explains it.
- **Optional open banking**, off by default, through the Enable Banking
  aggregator on your own key. Your machine talks to the aggregator directly —
  there is no beatrax server in the path, because there is no beatrax server.
- **Resolves the routing chains between your accounts** — PayPal → bank,
  card → bank via bulk SEPA settlement — so a charge points at whatever
  really paid for it.
- **Sees what is coming** — recurring series, drift alerts when a subscription
  quietly goes up, and a 30/60/90-day cash-flow forecast across every account.
- **Budgets in envelopes** — assign every euro, roll balances over, move money
  between categories, and import your history from YNAB, nYNAB or Actual.

## The privacy stance, stated plainly

beatrax runs entirely on your own machine. The SQLite database, the OAuth
tokens, the cached email receipts — all on your disk, and none of it leaves
unless you export it yourself. There is no telemetry, no analytics, no cloud
account, and nothing to sign up for.

Sync between *your own* devices is peer-to-peer and end-to-end encrypted:
devices pair by QR or word-code with a human-verifiable safety number, talk
directly over the LAN when both are awake, and fall back to a store-and-forward
relay that only ever holds ciphertext. At rest, the database is encrypted with
a passphrase-derived key gated behind the app lock.

## Who it's for

One person, or a two-person household, whose spending is spread across several
banks, cards and payment processors, and who has given up reconciling it by
hand. It assumes you can install a desktop application and grant an OAuth
permission if you want receipt scanning.

If you bank with one institution that already gives you a good app, you
probably don't need beatrax.

## Status

**v1.3 shipped. The current development line is v2.0** — a large release, which
is why it is v2.0 and not a point bump:

- Local-first end-to-end-encrypted peer-to-peer device sync
- A notification inbox with proactive, locally-generated reminders
- The optional open-banking connector
- Envelope (zero-based) budgeting, with split transactions
- A general-purpose rules engine that does more than assign categories
- Migration importers for YNAB, nYNAB and Actual Budget

Still in flight for v2.0: the mobile client as a fully synced peer, and
app-store distribution.

## The repos

| | |
|---|---|
| **[beatrax](https://github.com/beatrax-app/beatrax)** | The application — Laravel 13, Livewire, NativePHP desktop and mobile |
| **[spec](https://github.com/beatrax-app/spec)** | Specification and design documents |
| **[website](https://github.com/beatrax-app/website)** | The public site |
| **[.github](https://github.com/beatrax-app/.github)** | Org-wide community health files (this page lives here) |

## Licence

beatrax is licensed under the **[Hippocratic License 3.0](https://github.com/beatrax-app/beatrax/blob/main/LICENSE)**.
It is *source-available*, not OSI-approved open source: read it, run it, modify
it — but not as an instrument for human-rights abuse. Software that ingests a
person's entire financial history should be auditable, and should say out loud
what it won't be used for. The reasoning is written up in
[NOTICE.md](https://github.com/beatrax-app/beatrax/blob/main/NOTICE.md).

If you need an OSI-approved licence for procurement or downstream
relicensing, beatrax is not the right project for you.

## Want to help?

You don't need to write code:

- **Try it and tell us what broke.** Clear bug reports are worth more than
  most patches.
- **Improve the docs.** Something unclear is a bug; a docs PR is a real
  contribution.
- **Translate.** The interface and README already ship in English and Dutch;
  more are welcome.
- **Design & accessibility feedback** on any surface in the app.

Prefer to write code? The most useful things are new ingestion adapters
(especially Dutch-market sources we haven't covered), categorization rules and
merchant heuristics, and email-receipt parsers. Start with
[CONTRIBUTING.md](https://github.com/beatrax-app/beatrax/blob/main/CONTRIBUTING.md)
— it covers the module boundary and the quality gate every PR has to pass.

Not sure where something belongs? File it anywhere; routing is our job — or
just [ask on Discord](https://discord.gg/FYuV9CbTHR).

---

<p align="center">
  <a href="https://nightworks.io">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="../.github/nightworks-white.png">
      <img alt="NightWorks.io" src="../.github/nightworks-dark.png" height="20">
    </picture>
  </a>
</p>
