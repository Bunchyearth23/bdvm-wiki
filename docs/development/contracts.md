# Contrats et sécurité

## Commandes

Une commande mutante contient au minimum acteur, operation ID, version attendue, payload borné et correlation ID. L’autorité recharge le state, valide permission et transition, puis produit un résultat idempotent.

## Atomicité

Unity, wallet, réseau et save ne partagent pas une transaction ACID. BDVM utilise intention persistée avant effet, transitions `pending`, opérations externes idempotentes, réconciliation et compensation. Un crash ne doit ni créer d’argent ni perdre silencieusement un actif.

## Bridges

Les bridges ne lisent pas les types internes par reflection lorsque l’API publique nécessaire existe. Toute API absente, version incompatible, exception, payout non nul inattendu ou progression régressive entraîne un refus corrélé.

