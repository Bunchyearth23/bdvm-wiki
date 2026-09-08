# Multiplayer authority

The host is the only economic authority. Clients send bounded intents containing identity, expected version, and an idempotency key. The host recalculates permissions, price, ownership, and transition before mutation.

The protocol provides persistent identity independent of network address, initial snapshots for late join, replay-safe commands, disk checkpoints, crash recovery, and explicit rejection of incompatible schemas. A client UI becomes read-only whenever authority cannot be proven.

A real dedicated server is planned after the main milestones. The current candidate supports solo play and player-hosted sessions.

