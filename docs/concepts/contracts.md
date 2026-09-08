# Contrats et industrie

Les stations disposent de stocks d’entrée, stocks de sortie, capacités et horloges autoritaires. La production s’arrête par backpressure lorsque la sortie est pleine et reprend après livraison.

## Règles d’un contrat

- Le cargo est réservé séparément de la capacité de destination.
- L’operator fournit une rame compatible possédée ou louée.
- Les quantités réellement chargées et déchargées déterminent la progression.
- Les livraisons partielles sont persistantes et idempotentes.
- Completion ou annulation libère la rame sans la détruire.
- Un payout unique est routé vers le joueur indépendant ou la compagnie operator.

## Jobs vanilla

Lorsque le mode strict devient autoritaire, les nouvelles générations vanilla sont suspendues. Les jobs déjà ouverts sont inventoriés et doivent rester annulables pendant la migration. L’activation effectue un rollback si un job existant disparaît.

## SelfShunt

Le bridge corrèle l’opération BDVM au job externe, impose une autorité host-only, un payout SelfShunt nul, une progression cumulative monotone et une reprise de production unique.

