# BDVM.Operations

[Repository](https://github.com/Bunchyearth23/bdvm-operations) · Version 1.2.0 · Dépendances : Common, Companies, Fleet

Operations gère contrats fret et industriels, stocks, réservations, manifests, loading, unloading, livraisons partielles, backpressure et payouts. L’operator fournit toujours le matériel.

Le gate strict des jobs vanilla inventorie les jobs ouverts avant/après suspension des nouvelles générations et effectue un rollback si un adapter échoue ou si un job existant disparaît.

