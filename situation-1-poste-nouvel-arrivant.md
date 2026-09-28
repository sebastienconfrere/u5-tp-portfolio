# Préparer le poste d'un nouvel arrivant

[← Retour au portfolio](index.html)

*PME de 45 postes, service informatique — mars 2026 — option SISR*

## Contexte

L'entreprise recrute une assistante commerciale qui arrive le lundi suivant. Le service informatique, où je suis en alternance, doit lui fournir un poste prêt à l'emploi : ordinateur, compte, accès aux dossiers partagés, imprimante, messagerie. Nous avions un portable de retour d'un départ, rendu trois semaines plus tôt.

## Problématique

Le poste rendu contenait encore la session de l'ancien salarié, ses fichiers et ses comptes enregistrés dans le navigateur. Il fallait le remettre à zéro et le reconfigurer, sans perdre les documents professionnels qu'il pouvait contenir, et être prêt avant le lundi 9 h.

## Démarche

J'ai commencé par vérifier avec le responsable si des fichiers devaient être récupérés : il en restait 1,2 Go dans le dossier Documents, que j'ai copiés sur le serveur de fichiers, dans le dossier du service commercial.

J'ai ensuite envisagé deux solutions. Supprimer simplement le compte de l'ancien salarié : rapide, mais il restait des logiciels installés par lui et des paramètres inconnus. J'ai écarté cette option : le poste devait repartir sur une base saine, et le critère qui a tranché, c'est la traçabilité — je ne pouvais pas garantir ce qui restait sur la machine.

J'ai donc réinstallé Windows 11 depuis une clé USB préparée avec l'outil de création de support de Microsoft, puis installé les logiciels de la liste standard de l'entreprise, joint le poste au domaine, et créé le compte de l'arrivante avec les droits du groupe « Commerce ».

## Outils mobilisés

- Windows 11 24H2, clé USB d'installation créée avec Media Creation Tool
- Active Directory pour la création du compte et l'ajout au groupe Commerce
- GLPI 10.0 pour la mise à jour de l'inventaire
- Imprimante réseau partagée depuis le serveur d'impression

## Précautions prises

J'ai sauvegardé les fichiers avant d'effacer quoi que ce soit, et j'ai fait valider cette sauvegarde par le responsable avant la réinstallation. J'ai noté le numéro de série du poste et son nouveau nom dans GLPI. Le mot de passe initial du compte a été transmis à l'arrivante en main propre, avec obligation de le changer à la première connexion.

## Résultats

Le poste était prêt le vendredi à 16 h, soit un jour d'avance. L'arrivante a ouvert sa session le lundi à 9 h 05 sans incident. Aucun ticket n'a été ouvert par elle la première semaine. Le parc GLPI est à jour : le poste est passé du statut « en stock » à « affecté ».

## Bilan personnel

J'avais oublié de vérifier la licence Office avant de réinstaller : j'ai perdu 40 minutes à la retrouver dans le portail d'administration. La prochaine fois, je relèverai les licences et les clés avant de lancer la réinstallation, et j'en ferai une ligne de ma fiche de préparation.

---

**Compétences mobilisées** : gérer le patrimoine informatique ; répondre aux incidents et aux demandes d'assistance.
