# BDVM.Common

[Repository](https://github.com/Bunchyearth23/bdvm-common) · Version 1.0.0 · Apache-2.0

Common définit les IDs, DTO, résultats, erreurs, versions d’API et interfaces partagées. Il ne dépend ni de Unity, ni d’UMM, ni d’un autre module BDVM. Toute évolution incompatible d’un contrat exige une nouvelle version supportée explicitement.

Il ne contient aucune règle économique, aucun accès disque et aucun transport. Cette frontière permet aux modules et aux tests headless de partager les mêmes contrats sans charger le jeu.

