# BDVM.Core

The current development implementation includes a worker-owned persistent journal, a retained periodic economic projection and checkpoints tied to successful saves/autosaves. Read the [method and recovery boundaries](../development/unity-persistence.md); some commands and save staging remain synchronous.

[Repository](https://github.com/Bunchyearth23/bdvm-core) · 1.3.0 · Requires Common

Provides module registry, lifecycle, authoritative command bus, modular checkpoints, migrations, correlated logging, and runtime composition. It rejects duplicate IDs, dependency cycles, route collisions, missing capabilities, and incompatible versions. Missing-module payloads remain opaque and preserved.
