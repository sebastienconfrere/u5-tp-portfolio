# Mettre en place la sauvegarde des dossiers partagés

[← Retour au portfolio](index.html)

*TPE de 12 salariés, bureau d'études — avril 2026 — option SISR*

## Contexte

L'entreprise stocke ses plans et ses devis sur un NAS de quatre disques, accessible depuis les postes. Il n'existait aucune sauvegarde : le NAS était à la fois l'espace de travail et le seul endroit où vivaient les fichiers.

## Problématique

Le gérant a pris conscience du risque après qu'un salarié a supprimé par erreur un dossier de plans. Le dossier a été retrouvé dans la corbeille du NAS, mais la question restait : que se passe-t-il en cas de panne des disques, de vol, d'incendie ou de rançongiciel ? Le volume à protéger était de 380 Go, avec environ 2 Go de nouveaux fichiers par semaine.

## Démarche

J'ai proposé trois pistes. Un disque externe branché en permanence sur le NAS : simple et peu coûteux, mais un rançongiciel chiffrerait aussi le disque, et un incendie détruirait les deux. Écarté pour cette raison. Une sauvegarde chez un hébergeur en ligne : protège de l'incendie, mais la première sauvegarde de 380 Go aurait pris plusieurs jours sur la ligne de l'entreprise, et le coût mensuel dépassait le budget annoncé.

J'ai retenu une solution mixte : une sauvegarde quotidienne automatique vers un disque externe, qui reste branché, et une copie hebdomadaire sur un second disque que le gérant emporte chez lui. Deux copies, dont une hors site, et un coût limité à l'achat de deux disques.

## Outils mobilisés

- NAS Synology DS220+ et son outil de sauvegarde intégré
- Deux disques durs externes de 1 To
- Un tableau de suivi des rotations, affiché près du NAS

## Précautions prises

J'ai chiffré les deux disques, puisque l'un d'eux sort de l'entreprise. J'ai programmé la sauvegarde à 20 h, hors des heures de travail. Surtout, j'ai fait un test de restauration : j'ai restauré un dossier de 500 Mo sur un poste, pour vérifier que la sauvegarde était réellement exploitable, et pas seulement « verte » dans l'interface.

## Résultats

La première sauvegarde complète a duré 4 h 10. Les sauvegardes quotidiennes suivantes durent entre 3 et 8 minutes. Le test de restauration a rendu le dossier en 6 minutes, fichiers intacts. Depuis la mise en place, aucune sauvegarde n'a échoué en six semaines.

## Bilan personnel

Je croyais qu'une sauvegarde configurée était une sauvegarde qui marche. Le test de restauration m'a appris le contraire : c'est le seul moment où on vérifie vraiment. Je le referai tous les trimestres, et je l'ai noté dans le tableau de suivi.

---

**Compétences mobilisées** : mettre à disposition un service informatique ; gérer le patrimoine informatique.
