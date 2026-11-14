---
title: "Raccordement réseau de bâtiments"
date: 2025-02-13
description: "Extension de l'infrastructure réseau sur deux bâtiments annexes chez GE Vernova : fibre optique, câblage RJ45/PoE et étude de couverture Wi-Fi (HeatMap)."
image: "/images/projects/01/GEVERNOVA_vue_aerienne.jpg"
tags: ["Réseau", "Infrastructure", "WiFi", "PoE", "Fibre Optique", "GE Vernova"]
categories: ["Projets Professionnels"]
---

## Introduction

Pour ce premier projet réalisé chez GE Vernova, j'ai eu pour mission de raccorder deux bâtiments annexes au réseau de l'infrastructure principale, afin de pouvoir ensuite y déployer des équipements tels que des bornes Wi-Fi.

Le matériel réseau de l'usine n'étant pas administré localement mais intégré à l'infrastructure mondiale de l'entreprise, les équipements sont supervisés par les équipes réseau globales qui en gèrent également les configurations et le déploiement.

## Développement du projet

### Bâtiment annexe 1 : Fibre optique, brassage et norme PoE

Nous avons d'abord ouvert un projet auprès de l'équipe réseau globale. Une fois la liaison fibre optique tirée entre le bâtiment principal et le premier bâtiment annexe, puis les deux switches raccordés entre eux, l'équipe réseau a poussé à distance la configuration sur un ordinateur connecté au port console des switches concernés.

Une fois les équipements configurés et raccordés, il a fallu brasser les prises RJ45 depuis la baie du premier bâtiment jusqu'aux emplacements prévus pour les bornes Wi-Fi. Le tirage des câbles RJ45 à paires torsadées a été réalisé par les techniciens de maintenance, ne disposant pas de l'habilitation pour le travail en hauteur.

Lors du raccordement final, une des bornes ne recevait pas d'alimentation **PoE (Power over Ethernet)**. En inspectant le câblage, j'ai constaté que la première extrémité avait été sertie en **T568B** par le technicien et la seconde en **T568A**, empêchant l'alignement des paires nécessaires à l'alimentation électrique. J'ai donc recâblé l'extrémité pour harmoniser la norme et vérifié la continuité des paires à l'aide d'un testeur de câbles dédié.

![Normes de câblage T568A et T568B](/images/projects/01/normes-T568.webp)

### Bâtiment annexe 2 : Étude de couverture Wi-Fi (HeatMap)

Pour le second bâtiment (un entrepôt), face à des contraintes de matériel, de budget et d'urgence opérationnelle, nous avons opté pour le déploiement d'une borne unique capable de couvrir la zone utile.

L'enjeu principal était double :
* Éviter l'effet **cage de Faraday** provoqué par les nombreux racks métalliques de stockage.
* Positionner la borne à l'abri des passages de chariots élévateurs tout en maximisant sa portée.

J'ai donc réalisé plusieurs relevés de signal (**HeatMaps**) avec l'application **WifiMan** afin de comparer différents emplacements.

## Plan de l'installation

![Plan de l'installation réseau](/images/projects/01/plan-reseau.png)

## Les HeatMaps générées par l'application

---

| Scan 2 (Emplacement initial) | Scan 3 (Emplacement retenu) |
| :---: | :---: |
| ![HeatMap Scan 2](/images/projects/01/heatmap-scan2.png) | ![HeatMap Scan 3](/images/projects/01/heatmap-scan3.png) |

En comparant les relevés par rapport à la disposition des racks métalliques dans l'atelier, on constate que le signal du **Scan 2** est très irrégulier, alors que le **Scan 3** offre une couverture quasi homogène sans zone d'ombre critique.

Après validation de l'accès aux applications métier et réalisation d'un test de débit concluant, l'installation a été mise en production.