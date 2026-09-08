# Optional-mod compatibility catalog

BDVM does not require every mod in this catalog. Optional mods extend signalling, the map, presentation, realism, diagnostics, or rolling stock. Add one family at a time after the minimal BDVM profile passes so failures remain attributable.

Status terms used here:

- **Supported dependency:** required by a BDVM integration or its runtime.
- **Compatible option:** useful and not known to own BDVM economic state.
- **Validation option:** retained, but still needs focused runtime evidence.
- **Quarantined:** keep out of the main test profile until its named conflict is resolved.
- **Removed:** intentionally excluded from the BDVM profile.

## Shared infrastructure

| Mod | Function | BDVM value | Status and requirements |
| --- | --- | --- | --- |
| **DVLangHelper** | Shared localization runtime. | Required transitively by PassengerJobs and used by several content frameworks. | **Supported dependency.** Keep the version required by the coordinated PassengerJobs package. |
| **DVSignals** | Functional signalling framework and signal packs. | High value for Dispatch route safety and signal-aspect views; it has no economic authority. | **Compatible option.** Load with DVLangHelper. Validate signals after the minimal profile and again with Multiplayer. |
| **DVCustomCarLoader (CCL)** | Loads custom locomotives, wagons, passenger cars, and definitions. | Enables a larger finite catalog and multi-component asset tests. | **Validation option.** Needed only when at least one CCL vehicle is installed. Every livery and bundle still needs runtime validation. |
| **DVCustomLicenses** | Registers licenses requested by custom vehicles or cargo. | Conflicts conceptually with BDVM's economic-license model when used as a vanilla hard gate. | **Quarantined.** Install only for content that cannot yet remove the requirement; BDVM must not duplicate the charge or hard gate. |
| **SkinManagerMod** | Applies skins and liveries; integrates with CCL, Multiplayer, and PassengerJobs. | Preserves visual customization of owned assets. | **Compatible option.** Set `allowPaintingUnowned` to false so ownership remains meaningful. Multiplayer may log a transient early integration error before its successful second pass. |

## Signalling, map, and operations

| Mod | Function | BDVM interaction | Status |
| --- | --- | --- | --- |
| **DoubleTrack** (sometimes called Dual Tracks) | Adds doubled track geometry and Multiplayer integration. | Remote Dispatch understands its geometry, but map changes may invalidate persisted track IDs used for delivery and contracts. | **Validation option.** Add only after depot/service-track placement works on the base map; repeat track-ID and save/reload tests. |
| **DV Level Crossings** | Animated barriers, lights, and bells. | Immersive safety feature with no known economic writes. | **Compatible option.** Add after the minimal profile. |
| **DVTrafficOverlay** | Local/VR view of tracks, consists, capacities, limits, and shunting. | Useful diagnostic fallback; overlaps visually with Dispatch but does not replace its authority. | **Compatible option during development.** Keep `JobFocus` disabled while isolating job lifecycle issues. |
| **WagonDestination** | Displays a job wagon's final station or track. | Useful with vanilla and PassengerJobs flows; may become redundant with Management contract views. | **Compatible option.** Re-evaluate after the full contract UI is validated. |

## World presentation and realism

| Mod | Function | BDVM interaction | Status |
| --- | --- | --- | --- |
| **DV People** | Animated crowds, boarding, conductor, and announcements. | Its passenger gameplay can overlap PassengerJobs and BDVM passenger lifecycle. | **Quarantined for passenger validation.** Reintroduce only after proving it creates no second lifecycle or payout. |
| **DV Seasons** | Seasonal textures, snow, weather, and winter adhesion. | Operational and immersive; M62 can consume ambient temperature. | **Compatible option.** Exclude from baseline performance and adhesion comparisons. |
| **Leak Down** | Simulates brake and boiler pressure loss over time and condition. | Relevant to manual maintenance and operating costs, but adds a variable to economy tests. | **Validation option.** Add after base refuel, repair, and condition charging are proven. |
| **Number Manager** | Displays and manages rolling-stock numbers through SkinManager. | Useful for company-visible custom names/numbers. Visible numbers must never replace `CarGUID`. | **Validation option.** BDVM Management remains the owner of company naming; use Number Manager only as the visual adapter. |

## Optional rolling stock

| Content mod | Type and purpose | Dependencies | Current BDVM position |
| --- | --- | --- | --- |
| **Passenger Cars / Blue** | Custom passenger cars for capacity and catalog testing. | CCL; works with PassengerJobs, optionally SkinManager. | **Recommended first passenger content.** Test capacity, ownership, consist reuse, and save/reload. |
| **FPD4** | ALCO FPD-4 diesel locomotive. | CCL. | **Recommended first simple CCL locomotive.** Good baseline before multi-component sets. |
| **EMC E-Series / DE4-740** | A/B multi-component diesel set. | CCL. | **Recommended bundle test.** Validate atomic purchase, placement, coupling, ownership, and reload. |
| **Big Boy X4015** | Heavy A/B/C multi-component steam set; beta content. | CCL and its declared content dependencies. | **Secondary stress test.** Keep out of the minimal profile; test tender/bundle lifecycle and performance separately. |
| **Class DCB / DE4-6-850** | Custom diesel with a custom-license registration. | CCL and currently DVCustomLicenses. | **Quarantined pending compatibility work.** Its manifest/licensing behavior must be corrected before first-class support. |
| **M62 Logic** | M62 locomotive with custom simulation, cold start, audio, signal, and seasonal-temperature integration. | CCL; optional DVSignals and DV Seasons adapters. | **Advanced validation option.** Its early version and broad integrations greatly expand the compatibility matrix. |
| **S464-730 Dreyfuss** | Multi-component steam locomotive and tender. | CCL and custom-license support. | **Validation option after update.** Test convex-mesh warnings, bundle identity, licensing, and save/reload before catalog support. |
| **Santa Fe 4-8-4 2901** | A/B steam locomotive and tender. | CCL and custom-license support. | **Preferred initial steam candidate** if one licensed steam set is selected. Validate the same bundle and license boundaries as Dreyfuss. |

## Intentionally removed or unsupported

| Mod | Reason |
| --- | --- |
| **PersistentJobsMod** | Competes with the strict job-generation, track-reservation, and reload hooks owned by BDVM Operations. |
| **MessageBox** | Was needed only by PersistentJobsMod in the observed profile. |
| **CommsRadioAPI** | No retained consumer requires it after AI Traffic removal from the core profile. |
| **Derail Valley Mod Toolbar** | BDVM has its own launcher/UI; the observed consumer was removed. |
| **ZSounds** | Purely optional audio pack and its toolbar dependency were removed from the BDVM profile. |
| **MultiplayerAPITest** | Manifest-less duplicate API folder ignored by UMM and harmful to provenance audits. |
| **DVCarChanger** | Had no useful active configuration and could bypass purchased definition, value, or ownership rules. |
| **Big Boy X4025** | Redundant with X4015 and produced control-reflection/license warnings in the observed build. |
| **A&WR H6F** | Repeatedly failed to resolve its main livery, and redistribution was not suitable for the supported pack. |

## Recommended activation order

1. Validate BDVM Full and its required forks only.
2. Add DVSignals and diagnostic overlays.
3. Add CCL with FPD4 and Passenger Cars.
4. Add EMC E-Series as the first multi-component bundle.
5. Add SkinManager and Number Manager.
6. Add map and realism mods: DoubleTrack, Level Crossings, Seasons, then Leak Down.
7. Add one steam set and advanced M62 integration.
8. Test DV People last, after PassengerJobs lifecycle and payout are proven.

For every addition, repeat startup, catalog resolution, purchase/placement, ownership, save/reload, cleanup, and host/client checks. A mod being listed here means its role is documented; it does not replace the runtime evidence required for stable support.
