# Multiplayer et autorité

L’hôte est l’unique autorité économique. Les clients envoient des intentions bornées contenant identité, version attendue et idempotency key. L’hôte recalcule permissions, prix, ownership et transition avant toute mutation.

## Synchronisation

- Identité persistante indépendante de l’adresse réseau.
- Snapshot initial pour late join.
- Commandes rejouables sans double effet.
- Checkpoint disque et récupération après crash.
- Refus de protocoles ou schemas incompatibles.
- UI client en lecture seule lorsque l’autorité ne peut pas être prouvée.

Le serveur dédié est prévu après les jalons principaux. La candidate actuelle fonctionne en solo ou avec un joueur hôte.

