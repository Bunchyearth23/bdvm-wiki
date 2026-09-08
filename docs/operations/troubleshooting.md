# Dépannage

## BDVM charge mais reste en mode sûr

Cherchez `Runtime settings refused`. Une configuration invalide désactive volontairement les hooks. Corrigez le JSON hors jeu, réinstallez puis relancez. Pour la policy de population actuelle, `source` doit être un enum numérique.

## Un bridge est indisponible

Vérifiez le mod d’origine, son API, la version attendue et l’ordre de chargement. Installer uniquement `BDVM.SelfShuntBridge` ou `BDVM.PassengerJobsBridge` ne fournit pas SelfShunt ou PassengerJobs.

## Un client peut voir mais pas agir

C’est le comportement fail-closed lorsque l’identité, l’autorité ou la version attendue n’est pas prouvée. Comparez les rapports host/client et les versions de protocole.

## Un train a été débité mais n’apparaît pas

Ne recliquez pas en boucle. Relevez l’operation ID et le state `pending`, puis utilisez la réconciliation. Une compensation ou un retry idempotent doit terminer l’opération.

## Convois ou cabooses abandonnés

Séparez AI Traffic, jobs vanilla et actifs BDVM. Un signal vert n’implique pas que BDVM a créé ou gouverné l’obstacle. Relevez son `CarGUID`, son owner et les logs de sa source/cleanup avant toute conclusion.

