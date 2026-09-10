# In-game and Web interfaces

In-game, `Alt` enters mouse mode and `F7` toggles BDVM. The persistent button sits at the top right. While the window is open, clicks, levers, coupling, and other world interactions must be blocked.

Web loads **Dispatch** for railway topology and **Management** for companies, wallets, fleet, market, leases, contracts, passengers, industry, and planning. The browser is never authoritative: it renders snapshots and sends authenticated intents for host validation on Unity's main thread. Untrusted game labels are rendered as inert text.

Management shows human-readable names first and keeps stable IDs as secondary diagnostic information. Normal play uses guided buttons and named choices; the [advanced-options reference](management-advanced.md) explains every host configuration field.
