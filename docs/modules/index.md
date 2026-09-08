# BDVM modules

Each module has its own public repository, manifest, license, provenance, and pipeline.

| Module | Version | Kind | BDVM dependencies | External runtime |
| --- | ---: | --- | --- | --- |
| Common | 1.0.0 | contracts | — | — |
| Core | 1.3.0 | core | Common | — |
| Companies | 1.3.0 | feature | Common | — |
| Fleet | 1.3.0 | feature | Common, Companies | — |
| Market | 1.2.0 | feature | Common, Companies, Fleet | — |
| Operations | 1.2.0 | feature | Common, Companies, Fleet | — |
| Passengers | 1.0.0 | feature | Common, Operations | — |
| Web | 1.2.0 | platform | Common, Core | — |
| Dispatch | 1.1.0 | web feature | Common | Web, RemoteDispatchLive |
| Management | 1.3.0 | web feature | Common | Web |
| MultiplayerBridge | 1.1.0 | bridge | Common | Multiplayer, MultiplayerAPI |
| SelfShuntBridge | 1.1.0 | bridge | Common, SelfShunt.API | SelfShunt, SelfShunt.API |
| PassengerJobsBridge | 1.1.0 | bridge | Common, Passengers | PassengerJobs, API, DVLangHelper |
| Full | 0.3.0 | bundle | All thirteen modules | Complete integration set |

Feature modules do not depend on third-party mods. Bridges are not standalone and fail closed without their compatible runtime and API. Full is a composition package, not a second business authority.

