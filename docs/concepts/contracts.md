# Contracts and industry

Industrial deliveries are organized together in **Management → Contracts**, with one independent dossier per delivery. Dispatch shows wagon tags, cargo/fill state and dossier links. The [industrial dossier guide](../operations/industrial-dossiers.md) covers selection, preloaded wagons and physical loading requirements in the prepared development candidate.

Stations have input stock, output stock, capacity, and an authoritative clock. Production pauses under output backpressure and resumes after delivery.

A contract reserves cargo and destination capacity separately. Its operator assigns compatible owned or leased equipment. Actual loaded and unloaded quantities drive progress; partial deliveries are persistent and idempotent. Completion and cancellation release the consist without destroying it, and exactly one payout reaches the independent operator or company.

When strict authority activates, new vanilla job generation is suspended. Existing jobs are inventoried and remain available for cancellation; activation rolls back if an adapter fails or a job disappears.

The SelfShunt bridge correlates BDVM operations with external jobs, enforces host-only authority, zero SelfShunt payout, monotonic cumulative delivery, and exactly-once production resumption.
