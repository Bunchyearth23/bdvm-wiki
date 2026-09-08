# Diagnostics

## Fichiers à collecter

- `Player.log` complet ;
- dossier `Mods/BDVM.Full/diagnostics` ;
- checkpoint avant et après save/reload ;
- capture avant/après lorsque le problème est visuel ;
- preflight de la candidate installée.

## Identifiants indispensables

Notez l’étape, l’heure, le rôle host/client, le peer ID, le correlation ID, le job ID, l’event ID, les `CarGUID` et les wallets avant/après. Sans ces identifiants, deux événements similaires peuvent être confondus.

## Lire les logs

| Message | Sens |
| --- | --- |
| `composition-ready` | Web/Management enregistrés |
| `ui-ready` | Interface en jeu disponible |
| `population-control-disabled` | Mode strict volontairement inactif |
| `strict-population-control-active` | Tous les gates stricts activés |
| `activation-refused` | Précondition absente, aucune suppression partielle |
| `asset-cleanup-protected` | Actif économique exact protégé |
| `SaveGameData hook: enabled` | Persistance runtime active |

Ne concluez jamais à partir du seul numéro affiché par UMM : comparez commit, hash SHA-256 et source de l’archive.

