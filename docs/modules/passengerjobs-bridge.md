# BDVM.PassengerJobsBridge

[Repository](https://github.com/Bunchyearth23/bdvm-passengerjobs-bridge) · 1.1.0 · Runtime: BDVM PassengerJobs fork, PassengerJobs.API, and DVLangHelper

Consumes the fork's versioned API and maps available, taken, completed, and abandoned events to idempotent domain transitions. The host reads and credits each payout exactly once. No PassengerJobs source is copied into this bridge.

