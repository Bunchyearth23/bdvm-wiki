# Contracts and safety

A mutating command contains actor, operation ID, expected state version, bounded payload, and correlation ID. The authority reloads state, validates permission and transition, then records an idempotent result.

Unity objects, wallets, network state, and saves do not share an ACID transaction. BDVM uses intent-before-effect persistence, pending transitions, idempotent external effects, reconciliation, and compensation.

Bridges use supported public APIs instead of reflecting over internal types. Missing APIs, incompatible versions, exceptions, unexpected non-zero payouts, or regressive progress fail closed with correlated logs.

