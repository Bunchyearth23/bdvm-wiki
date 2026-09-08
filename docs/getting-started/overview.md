# Présentation

BDVM remplace la progression centrée sur les licences vanilla par une progression économique. Les licences peuvent encore représenter assurance, certification, frais ou caution, mais ne doivent pas devenir un hard gate frustrant.

## Modèle de jeu

- Chaque joueur reçoit un wallet personnel persistant.
- Un joueur peut rester indépendant ou rejoindre une compagnie.
- Chaque compagnie possède un wallet, des membres, des permissions, du matériel et des contrats distincts.
- Une compagnie commence à zéro ; les membres la financent et la font vivre.
- Le matériel peut être personnel, appartenir à une compagnie, acheté ou loué.
- Les contrats utilisent exclusivement le matériel possédé ou loué par leur operator.
- Les stations produisent du cargo, jamais des wagons.

## Starter anti-deadlock

Chaque joueur obtient une seule fois le montant personnel par défaut, une DE2 et trois wagons. Ce grant est persistant et ne peut pas être récupéré par dissolution, recréation de compagnie ou reconnexion.

## Dissolution

Le chef ou un membre autorisé peut dissoudre une compagnie. Les contrats sont annulés, les véhicules vendus, puis dettes et pénalités sont déduites. Le reliquat positif est partagé également entre les membres. Si le résultat est nul ou négatif, aucune distribution n’a lieu et la dette résiduelle est annulée afin d’éviter un deadlock.

