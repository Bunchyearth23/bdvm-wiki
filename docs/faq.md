# FAQ

## What does BDVM mean?

**Bunchy's Derail Valley Mods**.

## Does Full contain third-party mods?

No. Full composes BDVM modules. Compatible Multiplayer, SelfShunt, PassengerJobs, RemoteDispatchLive, APIs, and transitive dependencies are installed separately.

## Does BDVM.Passengers require PassengerJobs?

No. Passengers is independent. PassengerJobs is required only by the current playable bridge.

## Can strict mode use an existing vanilla career?

No. It intentionally refuses unsupported careers to avoid silently adopting naturally generated rolling stock.

## Why do contracts not provide wagons?

Free contract consists would remove the economic purpose of buying or leasing equipment. Contracts provide cargo and rewards; operators provide rolling stock.

## Why can the Web UI not set a balance directly?

Only the host is authoritative. The browser sends an intent; the host verifies actor, permission, version, price, and transition.

## Is a dedicated server available?

Not yet. Headless architecture exists, but the real dedicated runtime is deferred.

