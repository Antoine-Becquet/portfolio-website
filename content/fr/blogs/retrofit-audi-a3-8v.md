---
title: "Retrofit OEM : Virtual Cockpit et MIB2 High sur Audi A3 8V"
date: 2026-11-14
description: "Installation complète d'un combiné Virtual Cockpit et d'une unité MHI2 Harman (crossflash Q2 vers A3) sur Audi A3 8V : bus optique MOST, recodage ABS sous VCDS et déport Waze."
image: "/images/projects/04/rendu_waze.jpg"
tags: ["Automobile", "Retrofit", "Audi"]
categories: ["Projets Personnels"]
---

## Objectif du projet

L'objectif était de moderniser l'électronique embarquée de mon **Audi A3 8V (2014)** — initialement dotée d'un combiné d'instruments analogique et d'un système multimédia d'entrée de gamme (MIB1 Standard) — en intégrant des équipements constructeur d'origine (OEM) de génération supérieure :
* Un combiné numérique **Virtual Cockpit (FPK1)** (référence : 8V0920790C).
* Une unité d'infodivertissement **MIB2 High (MHI2 Harman)** (réference : 81A035036 car elle provient d'un Q2, adaptée comme une 8V0035036 d'origine A3 8V2).

![Configuration d'origine avant modification](/images/projects/04/original.jpg)

## Préparation matérielle et Cross-Flash du MIB2

Le passage sur une plateforme MIB2 High a nécessité le démontage de la planche de bord et de la boîte à gants pour adapter le faisceau Quadlock, raccorder les lignes de communication **CAN** au Gateway et tirer la boucle en **fibre optique (Bus MOST)** entre l'unité principale et le combiné.

L'unité MHI2 provenant d'un modèle différent (Audi Q2), j'ai dû réaliser un **cross-flash** complet du firmware et des datasets (via M.I.B. et accès Telnet/SSH) afin de reconfigurer le profil logiciel pour l'Audi A3 8V (gestion de l'écran rétractable 7 pouces (remplacé également car l'ecran 5.8 d'origine ne supporte pas le MIB2), cartographie, activation des licences FEC/SWaP pour CarPlay/Android Auto et adaptation de la protection des composants).

![Démontage et installation de l'unité MIB2](/images/projects/04/demontage.jpg)

## Installation du Virtual Cockpit et recodage du bloc ABS

La pose du combiné numérique s'est accompagnée de contraintes électroniques critiques. Lors du remplacement du combiné d'origine, le calculateur **ABS (`03 - Brakes`)** a perdu son codage long (remise à zéro), déclenchant une cascade de voyants et de codes défauts (DTC) sur l'ensemble du réseau CAN (ESP, direction assistée, frein de parking, contrôle de pression des pneus).

![Codes défauts suite au remplacement du combiné](/images/projects/04/defauts.jpg)

J'ai procédé à la reconstruction et au **recodage complet du module ABS via VCDS**, suivi de la calibration des capteurs (angle de braquage G85, accélération latérale) et de l'adaptation du module `17 - Instruments` (jauge à carburant, paramètres moteur TDI, affichage déporté), effaçant l'intégralité des défauts.

![Premier démarrage du Virtual Cockpit](/images/projects/04/compteur.jpg)

## Rendu final : Android Auto et déport Waze

Une fois la protection des composants levée et l'ensemble codé correctement, l'intégration est totalement transparente comme si l'on avait la version Facelift (A3 8V2 sortie en fin 2016):
* **Connectivité moderne :** Affichage d'Android Auto sur l'écran central rétractable avec gestion native des commandes au volant et de la molette MMI.

![Rendu avec Android Auto sur l'écran central](/images/projects/04/rendu_AA.jpg)

* **Navigation déportée dans le Virtual Cockpit :** Grâce au  bus optique MOST qui permet de base, d'afficher la cartographie integrée et obsolète, l'affichage des applis de cartes d'Android Auto et CarPlay est directement projeté au centre du Virtual Cockpit entre les compteurs, indépendament de l'affichage central.

![Affichage de la navigation Waze directement dans le Virtual Cockpit](/images/projects/04/rendu_waze.jpg)

Le total des pièces constructeurs (d'occasion) ayant couté environ :
- Compteur et câbles divers : 650€ avec adaptation antidémarrage officiel
- Ecran central 7" : 50€
- Unité MHI2 Q2 : 150€
- Volant et airbag : 250€

Soit un total d'environ 1 100€ pour une modernisation et une amélioration du confort de conduite qui augmente la valeur du véhicule, comparé a des pièces "aftermarket" type Aliexpress, affichant souvent quelque chose de moderne pour moins cher, mais qui dénature totalement l'interieur original du véhicule. 