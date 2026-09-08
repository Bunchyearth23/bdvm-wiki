# BDVM.PassengerJobsBridge

[Repository](https://github.com/Bunchyearth23/bdvm-passengerjobs-bridge) · Version 1.1.0 · Runtime : fork PassengerJobs, PassengerJobs.API, DVLangHelper

Le bridge consomme l’API versionnée du fork BDVM et convertit les événements available, taken, completed et abandoned en transitions idempotentes. Le payout est lu et crédité une seule fois par l’autorité BDVM.

`BDVM.Passengers` reste indépendant ; ce bridge n’est pas autonome et ne copie aucun code PassengerJobs.

