# Configuration

Le fichier `Mods/BDVM.Full/runtime-settings.json` active les capabilities de la composition complète. Toute erreur de parsing applique les safe defaults : hooks économiques et save désactivés, aucune mutation partielle.

## Flags principaux

| Flag | Effet |
| --- | --- |
| `enableSaveGameDataHook` | Persistance BDVM dans la save |
| `enableWalletBridge` | Raccord au wallet vanilla autoritaire |
| `enableMultiplayerProtocol` | Transport host/client |
| `enableCompanyGovernance` | Invitations, candidatures et permissions |
| `enableFleetManagement` | Ownership, bundles et états |
| `enableFiniteMarket` | Catalogue, disponibilité et quotes |
| `enableIndustrialPilot` | Industrie BDVM |
| `enablePassengerEconomy` | Domaine voyageurs |
| `enableAssetLifecycle` | Protection et cleanup ciblé |
| `enableStrictWorldPopulation` | Contrôle des sources de spawn |
| `verboseLogging` | Logs de diagnostic détaillés |

## Mode strict

Ne l’activez que si `enableSaveGameDataHook` est vrai, que l’instance est autoritaire, qu’une nouvelle carrière non tutorielle est chargée et qu’au moins un dépôt ou rail de service réel est configuré. Les enums de `worldPopulationPolicy.rules[].source` sont sérialisés numériquement par le serializer .NET Framework utilisé actuellement.

| Valeur | Source |
| ---: | --- |
| 0 | PurchasedDelivery |
| 1 | LeasedDelivery |
| 2 | StarterDelivery |
| 3 | RecoveryRequired |
| 4 | ExternalTraffic |
| 5 | NaturalLocomotive |
| 6 | ContractProvidedVehicle |
| 7 | UnsupportedTutorial |
| 8 | Unknown |

Une source inconnue ou une policy incomplète échoue fermé.

