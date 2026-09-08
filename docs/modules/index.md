# Modules BDVM

Chaque module possède son repository, son manifest, sa licence, son historique et son pipeline. Les versions ci-dessous décrivent la candidate actuelle ; elles ne constituent pas une garantie de stabilité.

| Module | Version | Type | Dépendances BDVM | Dépendances runtime externes |
| --- | ---: | --- | --- | --- |
| Common | 1.0.0 | contracts | — | — |
| Core | 1.3.0 | core | Common | — |
| Companies | 1.3.0 | feature | Common | — |
| Fleet | 1.3.0 | feature | Common, Companies | — |
| Market | 1.2.0 | feature | Common, Companies, Fleet | — |
| Operations | 1.2.0 | feature | Common, Companies, Fleet | — |
| Passengers | 1.0.0 | feature | Common, Operations | — |
| Web | 1.2.0 | platform | Common, Core | — |
| Dispatch | 1.1.0 | web-feature | Common | Web, RemoteDispatchLive |
| Management | 1.3.0 | web-feature | Common | Web |
| MultiplayerBridge | 1.1.0 | bridge | Common | Multiplayer, MultiplayerAPI |
| SelfShuntBridge | 1.1.0 | bridge | Common, SelfShunt.API | SelfShunt, SelfShunt.API |
| PassengerJobsBridge | 1.1.0 | bridge | Common, Passengers | PassengerJobs, PassengerJobs.API, DVLangHelper transitif |
| Full | 0.3.0 | bundle | Les treize autres modules | Les quatre intégrations complètes |

## Autonomie

`Common`, `Core` et les modules fonctionnels sont indépendants des mods tiers. Les bridges ne sont pas autonomes : ils refusent toute activation si leur runtime ou API compatible manque. `Dispatch` nécessite Web et le transport RemoteDispatchLive. `Full` est une composition pratique, pas une nouvelle autorité métier.

