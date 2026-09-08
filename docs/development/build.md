# Build et repositories

Les modules ciblent .NET Framework 4.8 (`net48`). Les builds d’intégration nécessitent les assemblies de Derail Valley, Unity Mod Manager et les APIs tierces correspondant aux forks.

## Règles de repository

- Un repository public par module.
- Licence Apache-2.0 pour le code BDVM.
- README, `module.json`, `COMPATIBILITY.md`, `LICENSE` et `NOTICE` dans chaque package.
- Provenance et licence upstream visibles pour tout code réutilisé.
- Aucune DLL téléchargée ou assembly de jeu commitée.

## Validation minimale

Le build de la solution, les tests domaine/modularité, les tests du module, l’audit de dépendances, la matrice de packages et `diff --check` doivent réussir avant publication.

