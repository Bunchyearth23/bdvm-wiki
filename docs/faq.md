# FAQ

## BDVM veut dire quoi ?

**Bunchy's Derail Valley Mods**.

## Full contient-il les mods tiers ?

Non. Full compose les modules BDVM. Multiplayer, SelfShunt, PassengerJobs, RemoteDispatchLive et leurs APIs/dépendances doivent provenir des packages de forks compatibles.

## PassengerJobs est-il requis pour BDVM.Passengers ?

Non. Passengers est un domaine indépendant. PassengerJobs est requis uniquement pour le bridge jouable actuel.

## Peut-on utiliser BDVM sur une save vanilla existante ?

Pas en mode strict. La candidate refuse volontairement le tutoriel et les saves sans checkpoint BDVM afin d’éviter une adoption incohérente du matériel existant.

## Pourquoi les contrats ne fournissent-ils pas les wagons ?

Parce que cela supprimerait l’intérêt économique d’acheter ou louer du matériel. Les contrats fournissent du cargo et une rémunération ; l’operator fournit la rame.

## Pourquoi l’interface Web ne peut-elle pas modifier directement un solde ?

Parce que seul l’hôte possède l’autorité. Le browser envoie une intention ; l’hôte vérifie acteur, permission, version, prix et transition.

## Le serveur dédié est-il disponible ?

Pas encore. L’architecture headless existe, mais le runtime dédié réel est différé.

## Où signaler un problème ?

Dans le repository du module concerné, avec `Player.log`, correlation ID, versions, hashes, rôle host/client et étapes exactes.

