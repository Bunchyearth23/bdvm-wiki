# BDVM Wiki

BDVM stands for **Bunchy's Derail Valley Mods**. It is a modular economy and operations suite for Derail Valley: every player keeps a personal wallet, companies own separate accounts and rolling stock, and the host remains authoritative for transactions, contracts, and assets.

<div class="bdvm-status"><div><strong>14</strong>independent modules</div><div><strong>4</strong>integration forks</div><div><strong>0.3.0</strong>current beta line</div><div><strong>1.0.0</strong>first planned stable</div></div>

!!! warning "Beta status"
    Current builds are intended for disposable test saves. A beta does not guarantee downgrade support or compatibility with tutorial and pre-BDVM careers.

## Start here

- **Players:** [Installation](getting-started/installation.md), then [First session](getting-started/first-run.md).
- **Session hosts:** [Configuration](operations/configuration.md), [Multiplayer authority](concepts/multiplayer.md), and [Diagnostics](operations/diagnostics.md).
- **Module developers:** [Architecture](concepts/architecture.md), [Contracts and safety](development/contracts.md), and [Build and repositories](development/build.md).
- **Testers:** [Test campaign](operations/testing.md) and [Diagnostics](operations/diagnostics.md).

## Core rules

1. The host validates every economic mutation.
2. Every transaction names its source and destination account.
3. Rolling stock is identified by `CarGUID`, never proximity or visible number.
4. In-game and Web interfaces display state and send intents; they do not calculate authority.
5. Missing or incompatible modules fail closed while their persistent payload remains preserved.
6. Contracts never create free rolling stock.
7. No AI driver can be hired; automation is limited to authorized planning assistance.

Main repository: [BDVM Full](https://github.com/Bunchyearth23/bdvm-full).

