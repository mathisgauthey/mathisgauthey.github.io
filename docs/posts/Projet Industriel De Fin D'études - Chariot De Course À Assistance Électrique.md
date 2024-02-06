---
title: Projet Industriel De Fin D'études - Chariot De Course À Assistance Électrique
aliases: 
description: Je décris ici mon projet industriel de fin d'études réalisé à Polytech Lyon, la conception d'un chariot de course à assistance électrique.
authors:
  - Mathis Gauthey
categories:
  - projects
tags:
  - CAD
  - Adams
  - CatiaV5
date:
  created: 2022-02-10T16:11:22+01:00
  updated: 2024-02-06T10:41:35+01:00
share: true
comments: true
---

# Projet Industriel De Fin D'études - Chariot De Course À Assistance Électrique

Je décris ici mon projet industriel de fin d'études réalisé à Polytech Lyon, la conception d'un chariot de course à assistance électrique.

<!-- more -->

*Ce document contient des extraits de notre soutenance finale.*

## Introduction

> Équiper un chariot de courses d’un système d'assistance électrique pour aider au déplacement sur le plat et au franchissement de trottoirs et d'escaliers.

Lors de notre dernier semestre d'études d'ingénieur en mécanique, nous avons réalisé ce projet en autonomie à 3. Ce projet s'est déroulé selon les étapes suivantes :

![2023-10-10_16-15-48_etapes_projet_industriel.png](../images/2023-10-10_16-15-48_etapes_projet_industriel.png)

Pour suivre l'avancement des différentes phases du projet, nous avons utilisé le logiciel Jira et son affichage Gantt.

![2023-10-10_16-18-26_jira_gantt.png](../images/2023-10-10_16-18-26_jira_gantt.png)

## Etablissement Du Cahier Des Charges Fonctionnel

Nos objectifs ont été les suivants :

- ✅ Assistance sur le plat
- ✅ Assistance franchissement trottoir
- ✅ Assistance franchissement escalier
- ❌ Assistance franchissement escalier en colimaçon

## Recherche De Solutions Existantes

Nous avons envisagé plusieurs solutions techniques lors de nos recherches documentaires.

### Système À Piston

Une première piste que nous avons envisagé fut d'utiliser un système de vérin poussoir soulevant le chariot à deux roues (éventuellement motorisées) au-dessus de la marche.

![2023-10-10_16-21-56_schema_piston.png](../images/2023-10-10_16-21-56_schema_piston.png)

### Système À Crochet

Une seconde piste que nous avons envisagé fut d'utiliser un système de crochet tracteur soulevant le chariot à deux roues (éventuellement motorisées) au-dessus de la marche.

![2023-10-10_16-22-53_systeme_crochet.png](../images/2023-10-10_16-22-53_systeme_crochet.png)

### Système À Trois Roues

Une dernière piste que nous avons envisagé fut d'utiliser un système à 6 roues, avec des roues individuellement motorisées ou par transmission, et un couple appliqué sur l’axe entre les roues pour faire tourner le support des roues.

![2023-10-10_16-23-19_systeme_trois_roues.png](../images/2023-10-10_16-23-19_systeme_trois_roues.png)

## Pré-études Des Solutions Sur Adams

![2023-10-10_16-26-56_difficulte.png](../images/2023-10-10_16-26-56_difficulte.png)

Après plusieurs pré-études, les résultats les plus prometteurs en terme d'aide à la réduction des efforts pour l'utilisateur sont associées au modèle à 6 roues.

En effet, l'accompagnement est beaucoup plus souple et sans à-coups, et le système permet un franchissement répété d'obstacle (comme un escalier) beaucoup plus rapide.

## Préciser Les Caractéristiques Techniques À L'aide D'études Sur Adams

Nous avons donc par la suite utilisé les scripts d'optimisation d'Adams pour trouver les meilleures dimensions et masses afin de réduire les efforts de l'utilisateur. Nous avons ainsi joué notamment sur les dimensions des roues, du système 3 roues, la hauteur du chariot et son chargement afin de contrôler l'assistance quel que soit le niveau de charge.

![2023-10-10_16-31-53_pre-etudes_adams.png](../images/2023-10-10_16-31-53_pre-etudes_adams.png)

Ces études nous ont mené a définir notre cahier des charges techniques :

- Charge max admissible : 30kg
- Contenance maximale : 50L
- Poids à vide : 5 à 10kg max
- Diamètre roues : 14cm
- Entraxe système 3 roues : 17cm
- Hauteur du chariot : 1.1m
- Largeur du chariot : 40cm
- Profondeur du chariot : 35cm

En terme de composants utilisés :

- Moteur : Transtecno CM 026 F30 D, série CM-CMP
   	- Couple en sortie de 10 Nm (entre 1 et 17)
   	- Puissance 0.06 kW à 0.12 kW
   	- Vitesse entre 25 et 300 RPM
- Transmission : Réducteur intégré puis réduction par engrenage de 0.5.
- Embrayage : Embrayage électromagnétique WARNER M.0113.2411
- Batterie : Batterie Lithium Iron Phosphate LIFEPO4 → 12.8V, 7.5Ah, 96Wh
- Système de commande : Bouton poussoir (franchissement) et molette A/R pour l’assistance sur le plat

## Modélisation De La Solution Retenue

![2023-10-10_16-32-23_modelisation_3D.png](../images/2023-10-10_16-32-23_modelisation_3D.png)

### Schema Cinematique

![2023-10-10_16-38-23_schema_cinematique.png](../images/2023-10-10_16-38-23_schema_cinematique.png)

### Motorisation

![2023-10-10_16-38-49_motorisation.png](../images/2023-10-10_16-38-49_motorisation.png)

### Chaine De Transmission Et Embrayage

![2023-10-10_16-39-05_transmission_embrayage.png](../images/2023-10-10_16-39-05_transmission_embrayage.png)

### Batterie Et Passage De Cables En Rotation

![2023-10-10_16-39-24_batterie_cables.png](../images/2023-10-10_16-39-24_batterie_cables.png)

### Commande Assistance

![2023-10-10_16-39-41_commande_assistance.png](../images/2023-10-10_16-39-41_commande_assistance.png)

## Test De Validation Sur Adams Avec Le Modèle CAO Puis Prototypage

Enfin, nous avons utilisé les caractéristiques techniques finales du modèle pour valider nos modélisation et analyser les efforts subit par l'utilisation avec ou sans les diverses assistances activées ou non.

![2023-10-10_16-29-51_adams_rotation_roues_seules.png](../images/2023-10-10_16-29-51_adams_rotation_roues_seules.png)

![2023-10-10_16-30-21_adams_assistance_rotation_seule.png](../images/2023-10-10_16-30-21_adams_assistance_rotation_seule.png)

![2023-10-10_16-31-26_adams_assistance_complete.png](../images/2023-10-10_16-31-26_adams_assistance_complete.png)
