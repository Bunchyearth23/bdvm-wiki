# Installation

For initial testing, use **BDVM Full** with the matching BDVM builds of its four integration forks. Never mix a fork API with an upstream binary that merely displays the same version.

| Runtime component | Purpose |
| --- | --- |
| Multiplayer + MultiplayerAPI | Network transport and peer identity |
| SelfShunt + SelfShunt.API | External industrial job lifecycle |
| PassengerJobs + PassengerJobs.API | Passenger service lifecycle |
| DVLangHelper | PassengerJobs transitive dependency |
| RemoteDispatchLive | HTTP host used by Dispatch |

## Safe procedure

1. Close Derail Valley.
2. Back up every existing mod folder that will be replaced.
3. Extract archives under `Derail Valley/Mods`, preserving their root folders.
4. Ensure that only one copy of every BDVM assembly exists.
5. Keep all binaries from the same coordinated release set.
6. Launch the game and inspect `Player.log` before loading a career.

!!! danger "Never update live files"
    Do not replace a DLL, manifest, or configuration file while the game is running.

Profiles: **minimal** and **economic** have no external runtime dependency; **dispatcher** requires RemoteDispatchLive; **complete** requires all integrations listed above.

Optional signalling, map, presentation, realism, and rolling-stock mods are not bundled with BDVM. See the [optional-mod compatibility catalog](../mods/optional-mods.md) before adding them to a validation profile.
