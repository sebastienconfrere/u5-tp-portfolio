# L'imprimante du service comptabilité n'imprime plus

[← Retour au portfolio](index.html)

*PME de 45 postes, service comptabilité — février 2026 — option SISR*

## Contexte

Le service comptabilité utilise une imprimante réseau partagée par quatre personnes. Elle sert notamment à l'édition des bulletins de paie et des relances clients, deux tâches qui ne peuvent pas attendre.

## Problématique

Un lundi matin, les quatre postes affichaient les travaux en file d'attente, sans qu'aucune page ne sorte. La panne durait depuis le vendredi après-midi, et une vingtaine de documents étaient bloqués. La paie devait partir le mercredi.

## Démarche

J'ai d'abord vérifié l'imprimante elle-même : écran allumé, pas de message d'erreur, pas de bourrage, du papier et du toner. J'ai imprimé une page de test depuis le panneau de l'imprimante : elle est sortie. Le problème ne venait donc pas de la mécanique.

J'ai ensuite testé le réseau : un ping vers l'adresse IP de l'imprimante depuis mon poste ne répondait pas. J'ai regardé l'adresse affichée sur l'écran de l'imprimante : 192.168.1.47, alors que les postes imprimaient vers 192.168.1.42. L'imprimante avait changé d'adresse pendant le week-end, après une coupure électrique.

J'ai envisagé de reconfigurer les quatre postes avec la nouvelle adresse : c'était le plus rapide, mais le problème se reproduirait à la prochaine coupure. Je l'ai écarté pour cette raison. J'ai préféré fixer l'adresse de l'imprimante, via une réservation DHCP sur le serveur, pour qu'elle retrouve toujours la même.

## Outils mobilisés

- Console DHCP du serveur Windows Server 2022
- Panneau de configuration de l'imprimante (Ricoh, écran tactile)
- Invite de commandes : ping et arp -a pour retrouver l'adresse MAC

## Précautions prises

Avant de créer la réservation, j'ai vérifié que l'adresse 192.168.1.42 n'était plus utilisée par un autre appareil. J'ai prévenu la comptable que les documents en attente devraient être relancés, et j'ai purgé les files d'attente après son accord, pour éviter que vingt documents sortent d'un coup.

## Résultats

L'impression a repris en 25 minutes. La paie est partie le mardi, avec un jour d'avance sur l'échéance. L'imprimante a conservé la même adresse lors de la coupure suivante, en mars. Le ticket GLPI a été clos le jour même, avec la cause et le correctif notés.

## Bilan personnel

J'ai failli reconfigurer les postes un par un, ce qui aurait marché le jour même et cassé de nouveau à la première coupure. Ce que je retiens : traiter la cause plutôt que le symptôme coûte dix minutes de plus et évite de refaire l'intervention.

---

**Compétences mobilisées** : répondre aux incidents et aux demandes d'assistance ; gérer le patrimoine informatique.
