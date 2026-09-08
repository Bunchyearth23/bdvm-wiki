# Installation

## Profil recommandé

Pour une première validation, utilisez **BDVM Full** avec les quatre forks BDVM correspondants. Ne mélangez pas une API de fork avec un binaire upstream portant la même version visible.

### Dépendances runtime du profil complet

| Composant | Rôle |
| --- | --- |
| Multiplayer + MultiplayerAPI | Transport réseau et identité de peer |
| SelfShunt + SelfShunt.API | Intégration industrielle et jobs externes |
| PassengerJobs + PassengerJobs.API | Lifecycle des services voyageurs |
| DVLangHelper | Dépendance transitive de PassengerJobs |
| RemoteDispatchLive | Host HTTP utilisé par Dispatch |

## Procédure

1. Fermez Derail Valley.
2. Sauvegardez les dossiers existants portant les mêmes IDs de mods.
3. Extrayez chaque archive sous `Derail Valley/Mods` en conservant son dossier racine.
4. Vérifiez qu’une seule copie de chaque assembly BDVM existe.
5. Conservez ensemble les binaires provenant de la même vague de release.
6. Lancez le jeu et contrôlez `Player.log` avant de charger une carrière.

!!! danger "Ne pas installer à chaud"
    Ne remplacez jamais une DLL, un manifest ou un fichier de configuration pendant que le jeu tourne.

## Profils

| Profil | Usage | Dépendances externes |
| --- | --- | --- |
| minimal | Domaine économique sans intégrations réseau/Web | Aucune |
| economic | Compagnies, flotte, marché, opérations | Aucune |
| dispatcher | Web et Dispatch | RemoteDispatchLive |
| complete | Tous les modules et bridges | Les cinq groupes listés ci-dessus |

