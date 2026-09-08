# Fork PassengerJobs

Le fork [Bunchyearth23/DVPassengerJobs](https://github.com/Bunchyearth23/DVPassengerJobs) dérive de [katycat5e/DVPassengerJobs](https://github.com/katycat5e/DVPassengerJobs), révision auditée `9bb668cbc2f3d270d282b2b3297667f01bec3e18`, sous licence MIT.

Il ajoute `PassengerJobs.API` et les protections nécessaires aux événements idempotents, au rôle host/client, à la lecture fiable du payout et à l’interdiction de recréer gratuitement un consist entre deux legs. Son feed de mise à jour ne suit pas l’upstream, car un package upstream peut légitimement ne pas contenir cette API.

