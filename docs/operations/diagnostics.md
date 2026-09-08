# Diagnostics

Collect the complete `Player.log`, `Mods/BDVM.Full/diagnostics`, preflight, checkpoint before/after reload, and relevant screenshots. Record the exact step, UTC time, host/client role, peer ID, correlation ID, job ID, event ID, affected `CarGUID` values, and wallet values before and after a payout.

| Log event | Meaning |
| --- | --- |
| `composition-ready` | Web and Management registration succeeded |
| `ui-ready` | In-game interface is available |
| `population-control-disabled` | Strict mode is intentionally off |
| `strict-population-control-active` | All strict gates activated |
| `activation-refused` | A precondition failed with no partial suppression |
| `asset-cleanup-protected` | The exact economic asset was protected |
| `SaveGameData hook: enabled` | Runtime persistence is active |

Never rely on UMM's displayed version alone. Match source commit, archive provenance, and SHA-256.

