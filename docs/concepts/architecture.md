# Architecture

BDVM sépare le domaine, l’orchestration, les adapters Unity, les transports et les interfaces. `Common` définit les contrats. `Core` compose lifecycle, command bus, registry et checkpoint. Les modules fonctionnels portent les règles métier. Les bridges isolent les APIs tierces.

```text
Interfaces in-game / Web
          │ intentions et snapshots
     Core + Common
          │ ports versionnés
 Companies ─ Fleet ─ Market ─ Operations ─ Passengers
          │
 Bridges optionnels
 Multiplayer / SelfShunt / PassengerJobs / Remote Dispatch
```

## Invariants

- Graphe de dépendances acyclique.
- Aucun type Unity, UMM, Harmony ou mod tiers dans le domaine.
- Routes, protocoles, schemas et capabilities sont versionnés.
- Collision d’ID, cycle, capability absente ou version incompatible : refus explicite.
- Le state d’un module absent est conservé sans migration implicite.

