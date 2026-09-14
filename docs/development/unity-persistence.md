# Unity work and persistent projections

Apply this method before extending periodic work in BDVM, RemoteDispatch, Multiplayer or their bridges. It is the priority methodology recorded in the workspace `AGENTS.md`.

## Ownership and processing

Unity objects and physical effects stay on the Unity owner thread. Capture only required values into owned data, compute and serialize on workers, then validate versions before applying changes on Unity. Detached containers must not retain mutable live references.

The periodic economy captures its inputs at initialization or after an external mutation. A retained `PeriodicEconomicProjection` calculates due production and reservation expiry away from Unity. `PeriodicEconomicDelta` carries expected revisions and changed rows; Unity checks every row before applying it. Only due production creates automatic commands. Do not restore whole-career copying, global validation or full serialization on every economic tick.

Other persisted systems use a journal of **already confirmed host mutations**, with documents per record. All 35 persisted business roots have explicit migration assignments. Accounting transactions alone cannot reconstruct initial balances, permissions or physical phases: import the complete initial state first.

`PersistentStateOwner` processes immutable confirmations in a worker-owned FIFO bounded by count, bytes and age. `PersistentJournal` checks sequences, hashes and duplicate receipts. Segmented storage flushes writes before acknowledging persistence. This acknowledgment does not authorize physical effects.

Some UI/Web commands, staging and actual saves still perform complete validations or serialization synchronously. This is not a complete asynchronous command processor. Positions and live physics do not belong in the business journal.

## Save, autosave and recovery

Staging `UpdateInternalData` does not prove save success. The `DoSaveIO` prefix embeds a unique `BDVM.PersistentJournalSave` ticket; a non-null save result queues a worker checkpoint of the exact immutable payload actually saved. Workers never read `SaveGameData`, and Unity does not wait for their disk writes.

Game saves retain a complete legacy payload for portability and recovery if the sidecar checkpoint has not finished. Loading an older save uses its own ticket and starts a new branch, without replaying future events or native effects. Saving an older staged image must not rewind the live journal.

Reset providers, queues, captures and projections for every world generation, including the same career reloaded. Old workers cannot publish into the replacement world. An incomplete terminal append is recoverable; corruption inside committed history is an explicit failure. Stop uncertain journal tracking while retaining embedded game-state recovery.

## Method: one migration at a time

1. Consult Graft and the index, then trace callers. Identify frequency, scans, allocations, waits, authority and Unity boundaries.
2. Inventory persisted roots and invariants: initial values, permissions, ordering, pending effects and reconciliation.
3. Capture minimal owned input and retain the worker projection. Exclude completed histories and unrelated systems from periodic capture.
4. Prepare changes off Unity. Validate revisions and all affected rows before applying; publish copies the worker cannot mutate.
5. Journal immutable confirmations with bounded queues, duplicate receipts, ordered segments and explicit write failures.
6. Hook successful saves/autosaves using the actual saved payload. Separate staging from durability and preserve the portable fallback.
7. Test world replacement, old saves, conflicts, duplicates, interrupted writes, corruption and failed saves. Compare business results against the previous implementation.
8. Measure Unity frames separately. A soft capture budget or passing offline checks does not prove a frame-time ceiling.

RemoteDispatch applies the same boundary to tracks, infrastructure, jobs and wagons. Cache and serialize owned data on workers; invalidate affected cargo through events. Do not add periodic economic polling for visual indicators. Multiplayer queues remain bounded and respect lifecycle cancellation.
