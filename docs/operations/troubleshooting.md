# Troubleshooting

## BDVM loads in safe mode

Find `Runtime settings refused`. Fix the JSON while the game is closed, reinstall, and relaunch. Current population-policy enums must be numeric.

## A bridge is unavailable

Verify the original mod, its API, supported version, and load order. Installing a bridge does not install SelfShunt, PassengerJobs, Multiplayer, or RemoteDispatchLive.

## A client can view but not act

This is expected fail-closed behavior when identity, authority, or version cannot be proven. Compare host/client diagnostics.

## Money was removed but no train appeared

Do not click repeatedly. Record the operation ID and pending state, then reconcile. Retry and compensation paths must be idempotent.

## Abandoned consists or cabooses

Separate AI Traffic, vanilla jobs, and BDVM assets. Record `CarGUID`, owner, spawn source, and cleanup logs before attributing the obstruction.

