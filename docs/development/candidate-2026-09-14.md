# Candidate record — 14 September 2026

## Prepared candidate

`unity-candidate-20260914-industrial-contracts-r4` combines Unity workload and persistence corrections with the [industrial Contracts workflow](../operations/industrial-dossiers.md). It is prepared, **not installed**. Source/wiki publication does not activate its binaries.

Official preparation and verification passed 25 validation groups with 96 candidate files. Comparison excluding configuration reports eight changed runtime DLLs: Full, Management, SelfShuntBridge, Web, RemoteDispatchLive, SelfShunt.API, SelfShunt and SelfShunt.MP. Proposed configuration remains separate and was not applied.

| Offline evidence | Result |
| --- | --- |
| BDVM domain | 148 passed |
| Industrial | 60 passed |
| Web / Management / modular Dispatch frontend | 30 passed |
| RemoteDispatch frontend | 38 passed |
| Web runtime | 34 passed |
| Management presentation and snapshot checks | 21 passed |
| SelfShunt API and cargo plan | 21 passed |
| Multiplayer protocol | 148 passed |
| Full build | No warnings or errors |

RemoteDispatch and SelfShunt retain existing package/nullable warnings. Browser checks used simulated data: 30 wagons and four dossiers. Grouping, filtering, selection, retained drafts, retry identity and desktop/mobile layouts passed. The actual Dispatch frontend with fixture data showed partial fill, destination and dossier navigation. This is not live physical or multiplayer proof.

## Earlier installed persistence candidate

`unity-candidate-20260914-persistent-systems-r2` was activated with the game closed and a recoverable backup. Official comparison showed 95 unchanged files after activation, excluding configuration. The user subsequently reported apparently stable performance; no quantified Unity frame-time qualification is claimed.

The preceding regression investigation observed expensive economic captures and a Windows-reserved port range containing 7245. The installed environment moved to 18080. Use the configured port for `/dispatch` and `/management`; 18080 is an environment setting, not a universal default. Development proxies must forward map/data routes instead of returning the SPA HTML fallback with HTTP 200.

Passenger economy and dedicated authority remain paused in the development profile. This candidate does not qualify them.

## Unity qualification remaining

1. Create a dossier with tagged preloaded wagons on SM-B40 without returning to a loader; conserve cargo and source stock.
2. Manage several independent deliveries and prevent duplicate wagon assignment.
3. Finish mixed/partial loads, unload and pay exactly once.
4. Observe stationary wagon cargo indicators during loading/unloading.
5. Save/autosave and reload loaded/mixed jobs; verify old-save isolation and retries.
6. Repeat sensitive cases with a client, two players and reconnects.
7. Measure real-save Unity frames and economic progression.

## Workspace evidence

Candidate files remain under `dv-company/artifacts/unity-candidates/`, logs under `dv-company/artifacts/industrial-contracts-20260914/`, and browser fixtures/screenshots under `dv-company/artifacts/dossier-ui-checks/`.

`dv-company` is an aggregate folder, not a Git repository. Its operational `docs/INDEX.md`, reports, aggregate tests/tools and generated Graft graph remain workspace files; the 14 module repositories live separately under `src/`. Methods and candidate status are published here for readers without the local aggregate. Game assemblies, saves and generated candidate binaries are not committed to this wiki.
