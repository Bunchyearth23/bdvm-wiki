# BDVM.Core

[Repository](https://github.com/Bunchyearth23/bdvm-core) · Version 1.3.0 · Dépendance : Common

Core fournit le registry de modules, le lifecycle, le command bus autoritaire, les checkpoints modulaires, les migrations, la corrélation des logs et la composition runtime. Il détecte doublons d’ID, cycles, routes concurrentes, capabilities manquantes et versions incompatibles.

Le checkpoint conserve comme payload opaque le state d’un module absent. Core n’invente pas de migration, ne vend pas ses actifs et ne supprime pas ses workflows.

