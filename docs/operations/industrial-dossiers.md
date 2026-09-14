# Industrial dossiers

!!! info "Development candidate — 14 September 2026"
    This workflow is implemented in `unity-candidate-20260914-industrial-contracts-r4`. Offline checks passed; it has not been installed or qualified in Unity. See the [candidate record](../development/candidate-2026-09-14.md).

## Manage deliveries together

Open **Management → Contracts** to create and organize industrial deliveries. Each delivery retains its own dossier, reservations, wagons and settlement. Grouping dossiers does not merge destinations or create a combined contract.

Filter and group by origin, destination, cargo or state. Select several dossiers for a summary. **Check selected deliveries** requests physical reconciliation separately and sequentially for each unfinished delivery. Partial results remain visible; an unknown response stops the batch. Retry retains the command identity.

Each dossier shows route, state, cargo quantities and payment. Expand details for exact wagon identities and tracks, or open its Dispatch link to locate the assigned wagons.

## Empty and preloaded wagons

1. Assign origin and cargo tags in Dispatch's Cars panel.
2. In Contracts, choose an allowed origin, destination, cargo and personal or company operator.
3. Search eligible wagons by name, stable identity or track. Select individually or select the displayed wagons together.
4. Enter the planned quantity, or use the quantity already aboard, then submit.

The host validates ownership, tags, physical cargo, capacity and assignments. Correctly tagged preloaded wagons can be assigned away from the loading track. Adopted cargo does not debit origin stock again. Compatible loading-track placement is still required when cargo actually needs loading.

A registered external SelfShunt job can finish loading when every identified wagon matches its allocated cargo and quantity. Mixed or incomplete groups retain the remaining loading work. Unloading and payment still require physical reconciliation.

Changing route or operator clears the wagon selection. Refresh retains the draft and removes newly ineligible wagons. An uncertain creation must be resolved with Retry before creating another dossier.

## Dispatch indicators

Dispatch provides railway context, wagon tags and links to Contracts. Industrial colors are available by default; existing color modes remain selectable.

| Appearance | Meaning |
| --- | --- |
| Blue | Tagged and empty |
| Amber | Partially loaded |
| Green | Full |
| Red | Physical cargo differs from the tag |
| Purple | Maintenance |
| Gray | Stored or untagged |

Text accompanies colors: empty, partial, full or unknown; fill percentage when capacity is known; and destination. Hover details and the Cars list show cargo, tag, dossier and operating state. Unknown capacity is not treated as empty.

Physical cargo follows targeted wagon events. Tag/dossier metadata refresh on opening, returning to the page, tag edits or explicit refresh. The read time identifies their age; refresh after a dossier change. A failed read clears previous metadata. These metadata are not continuous telemetry.
