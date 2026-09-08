# Interfaces en jeu et Web

## Interface en jeu

- `Alt` active le mouse mode.
- `F7` affiche ou masque BDVM uniquement dans ce mode.
- Le bouton persistant est placé en haut à droite.
- La fenêtre bloque clics, leviers, attelages et interactions avec le monde.

Cette interface reste un fallback compact pour diagnostics et opérations principales.

## Interface Web

Web charge deux modules :

- **Dispatch** pour topologie, trains, voies, aiguillages, signaux et occupations ;
- **Management** pour wallets, compagnies, flotte, marché, locations, contrats, voyageurs, industrie et triage.

Le browser n’est jamais une autorité. Chaque mutation est une intention authentifiée et validée sur le main thread de l’hôte. Les labels venant du jeu sont rendus comme texte inerte.

