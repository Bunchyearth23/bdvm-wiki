# Campagne de test

## Avant le lancement

1. Fermer le jeu et générer le preflight.
2. Exiger `safeToInstallNow=true`.
3. Installer avec backup vérifié.
4. Conserver hashes et commits de tous les composants.

## Passage principal

1. Charger une nouvelle carrière non tutorielle.
2. Vérifier UI, wallet, compagnie et starter grant.
3. Tester achat, placement autorisé/refusé, retry et revente.
4. Tester location entrante et sortante.
5. Exécuter contrats fret, industrie et voyageurs avec payout unique.
6. Sauvegarder, revenir au menu et recharger.
7. Rejouer une commande pour vérifier l’idempotence.
8. Tester dissolution et distribution nette.
9. Vérifier protection cleanup d’un actif exact et absence de protection d’un wagon marchand.
10. Activer le mode strict avec rails configurés : aucun nouveau consist gratuit, jobs existants annulables.
11. Tester SelfShunt : host-only, payout nul, retry sans duplication, reprise de production.
12. Refaire les points sensibles avec un client, deux reconnexions et comparaison host/client.

## Critère d’arrêt

À la première erreur d’ownership, double payout, véhicule dupliqué, débit sans livraison ou divergence host/client : arrêter les mutations, conserver la session et collecter les preuves avant reload.

