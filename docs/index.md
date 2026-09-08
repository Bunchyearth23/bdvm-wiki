# BDVM Wiki

BDVM signifie **Bunchy's Derail Valley Mods**. Cette suite transforme Derail Valley en environnement économique modulaire : chaque joueur conserve son portefeuille, les compagnies possèdent leur compte et leur matériel, et l’hôte reste l’unique autorité sur les transactions, contrats et actifs.

<div class="bdvm-status">
  <div><strong>14</strong>modules indépendants</div>
  <div><strong>4</strong>forks d’intégration</div>
  <div><strong>0.3.0</strong>candidate beta actuelle</div>
  <div><strong>1.0.0</strong>première stable prévue</div>
</div>

!!! warning "État beta"
    Les builds actuels sont destinés aux tests sur des saves jetables. Une release beta ne garantit ni migration descendante ni compatibilité avec une save vanilla, un tutoriel ou une ancienne version de DVCompany.

## Choisir son point de départ

- **Joueur** : commencez par [Installation](getting-started/installation.md), puis [Première partie](getting-started/first-run.md).
- **Administrateur de session** : consultez [Configuration](operations/configuration.md), [Multiplayer et autorité](concepts/multiplayer.md) et [Diagnostics](operations/diagnostics.md).
- **Développeur de module** : lisez [Architecture](concepts/architecture.md), [Contrats et sécurité](development/contracts.md), puis [Build et repositories](development/build.md).
- **Testeur** : utilisez la [Campagne de test](operations/testing.md) et joignez les preuves décrites dans [Diagnostics](operations/diagnostics.md).

## Principes non négociables

1. L’hôte valide toute mutation économique.
2. Une transaction indique explicitement le wallet débité et crédité.
3. Le matériel est identifié par `CarGUID`, jamais par proximité ou numéro visible.
4. Les UI en jeu et Web affichent le state et envoient des intentions ; elles ne calculent aucune autorité.
5. Un module absent ou incompatible échoue fermé sans supprimer son payload persistant.
6. Aucun contrat ne crée gratuitement les wagons nécessaires à son exécution.
7. Aucun conducteur IA n’est recrutable ; l’automatisation reste limitée aux aides de triage autorisées.

## Repositories essentiels

- [BDVM Full](https://github.com/Bunchyearth23/bdvm-full) — bundle complet.
- [Organisation des modules](modules/index.md) — rôle et dépendances de chaque package.
- [Forks BDVM](forks/index.md) — provenance, licences et compatibilité.
- [Toutes les releases GitHub](https://github.com/orgs/Bunchyearth23/repositories?q=bdvm) — sources et archives publiques.

