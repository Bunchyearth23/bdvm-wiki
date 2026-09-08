# Compatibilité

## Matrice de principe

- Même major de contracts et protocoles : upgrade/downgrade seulement si déclaré.
- Major différente : refus.
- Module absent : payload conservé, workflows suspendus.
- Module réinstallé compatible : state restauré.
- Doublon d’assembly, route ou module ID : refus.
- Ancien package DVCompany monolithique : aucune façade ni import automatique.

## Saves

La candidate stricte nécessite une nouvelle carrière non tutorielle ou une save portant déjà un checkpoint BDVM compatible. Les tests doivent utiliser des saves jetables jusqu’à publication d’une garantie de migration.

## Mods de contenu

BDVM identifie les véhicules par `CarGUID`, pas par leur livery. Les locomotives et wagons tiers nécessitent néanmoins une validation physique : spawn, couplage, réparation, coût, sauvegarde et Multiplayer.

