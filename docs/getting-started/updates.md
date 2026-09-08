# Mise à jour et rollback

## Politique de version

- Les prereleases `beta` servent aux campagnes de validation.
- La première stable est réservée à `1.0.0`.
- Les modules et forks d’une même vague forment un ensemble testé.
- Un downgrade ou un changement de major non déclaré doit être refusé.

## Mise à jour sûre

1. Fermez le jeu.
2. Sauvegardez les dossiers remplacés et le checkpoint BDVM.
3. Vérifiez le SHA-256 des archives.
4. Installez la vague complète ou un profil dont les dépendances sont fermées.
5. Conservez le backup jusqu’à validation du save/reload.

## Rollback

Fermez le jeu, restaurez tous les fichiers du même backup et ne mélangez pas assemblies nouvelles et anciennes. Un payload de module absent doit rester conservé de manière opaque ; sa suppression manuelle peut rendre le rollback impossible.

