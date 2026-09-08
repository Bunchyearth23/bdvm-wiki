# Configuration

`Mods/BDVM.Full/runtime-settings.json` controls the complete runtime. Any parse or validation error applies safe defaults: save and economy hooks remain disabled and no partial mutation is registered.

| Flag | Purpose |
| --- | --- |
| `enableSaveGameDataHook` | Persist BDVM state in the save |
| `enableWalletBridge` | Connect the authoritative vanilla wallet |
| `enableMultiplayerProtocol` | Enable host/client transport |
| `enableCompanyGovernance` | Membership and permission workflows |
| `enableFleetManagement` | Ownership, bundles, and service states |
| `enableFiniteMarket` | Catalog inventory and quotes |
| `enableIndustrialPilot` | BDVM industry runtime |
| `enablePassengerEconomy` | Passenger domain |
| `enableAssetLifecycle` | Targeted cleanup protection |
| `enableStrictWorldPopulation` | Govern rolling-stock spawn sources |
| `verboseLogging` | Detailed correlated diagnostics |

Strict population control also requires the save hook, an authoritative host, a new non-tutorial career, and at least one validated depot or service track. The current .NET serializer represents `worldPopulationPolicy.rules[].source` numerically: 0 purchased, 1 leased, 2 starter, 3 recovery, 4 external traffic, 5 natural locomotive, 6 contract-provided vehicle, 7 unsupported tutorial, and 8 unknown.

