# Décisions et limites

## Décisions établies

- Plusieurs compagnies peuvent coexister dans une partie.
- Un joueur possède un wallet personnel et peut être indépendant.
- Une compagnie démarre à zéro et sa création est gratuite.
- Invitation/candidature par défaut, configurable.
- Le chef délègue les permissions sensibles.
- Vente à 50 % en parfait état, dégressive linéairement jusqu’à 15 %.
- La dissolution annule contrats, vend actifs, déduit dettes/pénalités puis distribue le positif également.
- Placement initial uniquement en dépôt ou rail de service.
- Achat locomotive + matériel remorqué possible comme bundle atomique.
- Pas de conducteur IA recrutable.
- Serveur dédié différé après les jalons principaux.
- Licences transformées en coûts économiques plutôt qu’en hard gates.

## Risques encore ouverts

- Atomicité réelle entre wallet, objets Unity, réseau et save lors d’un crash.
- Exploits économiques par dissolution, recréation ou transferts circulaires.
- Compatibilité de modules indépendants absents ou de versions différentes.
- Lifecycle et payout PassengerJobs à confirmer dans Unity et en host/client.

## Preuves encore nécessaires

Les builds et tests headless ne remplacent pas les tests physiques : save/reload, spawn, placement, cleanup, signaux, refuel/repair, navigateur, PassengerJobs, SelfShunt, reconnexion et rollback.

