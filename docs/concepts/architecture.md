# Architecture

BDVM separates domain rules, orchestration, Unity adapters, transports, and interfaces. Common defines contracts; Core provides lifecycle, registry, command bus, checkpoints, and migrations; feature modules own business rules; bridges isolate third-party APIs.

```text
In-game UI / Web UI
       │ intents and snapshots
   Core + Common
       │ versioned ports
Companies ─ Fleet ─ Market ─ Operations ─ Passengers
       │
Optional bridges: Multiplayer / SelfShunt / PassengerJobs / Remote Dispatch
```

The dependency graph is acyclic. Domain code contains no Unity, UMM, Harmony, or third-party mod type. Route IDs, schemas, protocols, and capabilities are versioned. Duplicate IDs, cycles, missing capabilities, and incompatible versions are explicit failures. Missing-module state is retained without invented migration.

