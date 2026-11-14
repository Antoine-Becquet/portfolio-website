---
title: "Mon installation Home Assistant"
date: 2024-11-22
description: "Centralisation et automatisation de mon écosystème domotique multi-protocoles avec Home Assistant."
image: "/images/projects/02/homeassistant.png"
tags: ["Home Assistant", "Domotique", "Automatisation", "Réseau", "HomeLab"]
categories: ["Projets Personnels"]
---

## Préambule

J'ai récemment décidé de renouveler mon système domotique chez moi en voulant un contrôle absolu sur mes appareils. L'objectif est d'exploiter le plein potentiel de chacun et de faciliter l'interconnexion entre tous, car j'utilise de nombreux équipements basés sur différents protocoles qui ne communiquent pas nativement entre eux.

Auparavant, j'utilisais uniquement l'écosystème Google Home avec un **Google Nest Hub (2e gén.)**, permettant l'affichage d'informations ainsi que le contrôle des éclairages de différentes marques et du téléviseur sous Android TV. 

Grâce à **Home Assistant** — hébergé directement sous forme de machine virtuelle sur ma Freebox Delta — j'accède désormais à bien plus d'équipements :
* Mon serveur **HomeLab**
* Mon robot aspirateur
* Ma console de jeux
* La **Freebox** elle-même (suivi du débit, nombre d'appareils connectés, création de capteurs réseau)

## Intégrations et centralisation

Une fois la machine virtuelle installée et configurée, Home Assistant permet de regrouper un grand nombre d'intégrations pour différentes marques d'appareils connectés au sein d'une interface unique.

![Intégrations Home Assistant](/images/projects/02/ha-integrations.png)

Sur mon tableau de bord principal, j'ai organisé les contrôles par zones fonctionnelles :
* **À gauche :** l'ensemble de mes ampoules connectées.
* **Au centre :** mes applications média, pour diffuser du contenu sur les appareils compatibles et piloter la lecture.
* **À droite :** les commandes de mon robot aspirateur (renommé pour l'occasion au lieu de laisser le simple nom générique *Roomba* !), ainsi que les statistiques de la Freebox et les commandes de redémarrage.

![Tableau de bord Home Assistant](/images/projects/02/ha-dashboard.png)

## Protocoles avancés et automatisations

Home Assistant supporte également des protocoles réseau standards comme le **SNMP**, ce qui permet de superviser des machines (comme un Windows Server) ou d'exploiter des données météorologiques locales pour déclencher des scénarios précis.

![Protocoles et capteurs](/images/projects/02/ha-automations.png)

Voici un exemple de logique d'automatisation mise en place pour la gestion de l'éclairage et des ouvrants :

```text
SI : Coucher_du_soleil < Heure < Lever_du_soleil
    allumer.lumières_salon
SINON :
    ouvrir.volets_salon
    eteindre.lumières_salon