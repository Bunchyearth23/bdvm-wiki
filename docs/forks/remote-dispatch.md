# Remote Dispatch Live fork

The prepared industrial candidate replaces the dossier creation panel with links to Management → Contracts and adds cargo/tag colors and text to wagons. Cargo invalidation is event-driven; metadata refresh is explicit or tied to page/tag actions. See the [workflow](../operations/industrial-dossiers.md).

[Bunchyearth23/dv-remote-dispatch](https://github.com/Bunchyearth23/dv-remote-dispatch) derives from [mspielberg/dv-remote-dispatch](https://github.com/mspielberg/dv-remote-dispatch), base `0e032da48550e09e405b4b164f31136f2e925ebf`, under MIT.

It provides the HTTP host, frontend, and adapters used by Dispatch. Its upstream functions remain usable without BDVM; economic views require the Web, Dispatch, and Management modules.
