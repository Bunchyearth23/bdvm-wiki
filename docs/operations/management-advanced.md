# Management advanced options

The normal Management workflow uses guided buttons and named choices. Open **Advanced host setup** only when you want to design the economy of a server. These settings are host-authoritative, persistent, and can affect every player.

Identifiers remain visible for diagnostics and interoperability, but the interface shows the human-readable name first. Never change an identifier merely to rename something.

## Industry: recommended first setup

Use **Discover stations and configure a personal pilot chain** or its company equivalent whenever possible.

1. Select one or more available freight wagons.
2. Confirm the action.
3. BDVM finds cargo compatible with every selected wagon.
4. BDVM finds two loaded stations that can handle that cargo.
5. It creates finite source and destination stocks, a production recipe, and a shortage-driven policy.
6. It publishes the first transport need.

The action refuses safely when the wagons are unavailable, not controlled by the operator, incompatible with a common cargo, or no valid pair of loaded warehouses exists.

## Industrial stock

Industrial stock represents cargo at a station. It never represents wagons and never spawns rolling stock.

| Option | Meaning | Safe starting value |
| --- | --- | --- |
| Station | Facility that owns the stock. | Choose a named loaded station. |
| Cargo | Cargo stored at that station. | Choose a cargo supported by the intended chain. |
| Quantity currently available | Cargo immediately available before reservations. | `0` at a consumer; one or two trainloads at a producer. |
| Maximum storage capacity | Upper limit including reserved inbound cargo. | At least twice the intended trainload. |

`Quantity currently available` must not exceed capacity. Reducing capacity below already committed cargo may be refused.

## Production recipe

A recipe periodically consumes one stock and produces another at the same station.

| Option | Meaning |
| --- | --- |
| Internal recipe name | Stable technical key for this recipe. It is shown secondarily in diagnostics. |
| Producing station | Station at which input is consumed and output appears. |
| Cargo consumed / Quantity consumed | Input required for one production cycle. |
| Cargo produced / Quantity produced | Output added by one completed cycle. |
| Production interval | Authoritative economy ticks required per cycle. It is not real-world seconds. |
| Maximum stored production cycles | Backlog limit when several cycles become due. It prevents unlimited catch-up production. |

Both input and output stock records must exist. Production stops safely when input is insufficient or output storage is full.

## Shortage-driven transport policy

A policy compares destination stock with its target and publishes a finite transport need when cargo is missing.

| Option | Meaning |
| --- | --- |
| Internal policy name | Stable key used for persistence and diagnostics. |
| Cargo pickup station | Station whose available stock is reserved. |
| Cargo delivery station | Station whose free capacity and target create demand. |
| Cargo | Cargo transported by the policy. |
| Maximum cargo per offer | Upper bound for one generated job. Actual quantity may be lower. |
| Target stock at destination | Desired destination inventory. No need is created at or above this amount. |
| Base payment | Guaranteed quoted reward before scarcity adjustments. |
| Maximum shortage bonus | Maximum extra reward caused by low destination stock. |
| Time before an unaccepted offer expires | Lifetime of a published but unaccepted need, in economy ticks. |
| Time allowed to prepare wagons | Reservation window after acceptance. |
| Time allowed for delivery | Delivery deadline after activation. |
| Penalty if preparation expires | Bounded charge if the accepted reservation expires before activation. |
| Minimum number of wagons | Smallest consist accepted for the job. |
| Minimum cargo capacity | Required combined compatible capacity. |
| Allowed wagon models | Optional model allow-list. Selected vehicles are examples of their models, not permanently assigned wagons. |
| Publish offers from this policy | Enables future shortage-driven publication. Disabling it does not erase existing records. |

Creating a policy does not create wagons. The operator must own or lease compatible equipment.

## Manual transport contract

Use **Create one manual transport contract** only for testing or a deliberately curated operation. Unlike a policy, it creates one offer and does not establish recurring production.

The origin, destination, cargo, quantity, reward, deadline, wagon count, capacity, and allowed models have the same meaning as above. **Company operation** selects the company as beneficiary and operator; the authenticated player must have the required permission.

## Passenger routes

The guided action **Create a passenger route** generates the internal route identifier from the chosen stations.

| Option | Meaning |
| --- | --- |
| Departure station / Arrival station | Named endpoints of the service. They must differ. |
| Passengers waiting initially | Demand available immediately after route creation. |
| Maximum waiting passengers | Hard demand cap. |
| New passengers per demand cycle | Demand added during each refresh cycle. |
| Target service interval | Desired interval used when evaluating service frequency. |
| Fare per passenger | Maximum base revenue before capacity and punctuality adjustments. |
| Late penalty per time unit | Amount removed for each authoritative tick beyond the planned arrival. |

Creating a route does not create a Passenger Jobs service. Load or accept the service in the game, then use **Reserve passenger service**.

### Reserving a passenger service

Choose the named route, the loaded Passenger Jobs service, and passenger-capable rolling stock. **Available passenger seats** is the capacity BDVM may book; it must reflect the selected consist. **Planned journey duration** is measured in economy ticks. **Company operation** routes authorized revenue and costs through the company.

## Financing

Financing is optional and inactive until the host supplies a finite lender pool.

| Option | Meaning |
| --- | --- |
| Backed capital | Maximum real capital the pool can reserve across contracts. |
| Financing type | A loan provides its principal according to its contract; a credit line permits later draws up to its limit. |
| Principal limit | Maximum borrowed principal. |
| Interest, in basis points | `100` basis points equals 1%. For example, `500` equals 5%. |
| Minimum installment | Smallest scheduled repayment. |
| Payment interval | Economy ticks between installments. |
| Maturity | Final duration in economy ticks. |
| Guarantee | Amount held as security according to the disclosed terms. |
| Company financing | Makes the company, rather than the player, the debtor. |

The interface must disclose all terms before acceptance. A pool cannot promise more capital than it has available.

## Maintenance

BDVM records and settles manual maintenance; it does not repair or refuel a vehicle automatically.

| Option | Meaning |
| --- | --- |
| Action | Observation category: inspection, service, repair, or refuel. |
| Maximum authorized cost | Spending ceiling. Costs above it require refusal or explicit handling. |
| Company pays | Uses the authorized company account instead of the personal wallet. |
| Optional trip ID | Associates the cost with an operation for profitability reporting. Leave it blank when not applicable. |

Start the session, perform the work in the game, then complete it. Cancel an unused session so reserved funds are released.

## Yard plans

Yard plans are planning-only checklists. They do not move trains, operate switches, or control SelfShunt.

Choose an active assignment and enter track IDs in the intended working order. The plan ID is its persistent technical key. Cancel obsolete plans rather than reusing their IDs for unrelated work.

## Troubleshooting an advanced action

If an action is refused, keep the displayed request identifier and exact reason. Refresh first: another action may have changed the authoritative version. Retrying preserves the idempotency key, so a successful operation cannot normally be charged or created twice.

Common safe refusals include insufficient permissions, stale state, incompatible wagons, missing loaded stations, unsupported cargo, insufficient stock or capacity, and invalid economic bounds.
