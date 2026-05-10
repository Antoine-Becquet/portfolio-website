---
title: "Migration et optimisation de l'infrastructure LAPS"
date: 2025-04-28
description: "Modernisation du système de projection laser pour la fabrication de pales d'éoliennes offshore chez GE Vernova."
image: "/images/projects/lap_prosoft6.png"
tags: ["Infrastructure", "Réseau OT", "Industrie 4.0", "Support IT"]
categories: ["Projets Professionnels"]
---

## Présentation de l’entreprise

**GE Vernova** est une multinationale disposant de plusieurs filiales dans le domaine de l’énergie. Le site de Cherbourg, où j’effectue mon alternance, fait partie de la filiale **Offshore Wind**. Nous y fabriquons des pales d’éoliennes en mer, bien plus grandes que celles que l’on retrouve sur terre.

![Vue aérienne du site de GE Vernova Cherbourg](/images/projects/GE%20VERNOVA%20vue%20aerienne.jpg)
*Figure 1 : vue aérienne du site de GE Vernova Cherbourg*

Ma mission sur site est d’assurer le support aux utilisateurs et de mettre en place des solutions pour optimiser les procédés de fabrication, apportant une plus-value en termes de précision et de gain de temps.

## Contexte du projet LAPS

Auparavant, les opérateurs devaient mesurer avec un mètre et découper chaque morceau de fibre manuellement. Le système **LAPS** (Laser Projection System) change la donne en projetant directement les instructions et les pochoirs sur le moule de la pale (environ 110m de long).

L'infrastructure repose sur un réseau de **20 projecteurs laser** disposés sur toute la longueur du moule. Mon projet consiste à améliorer cette infrastructure pour gagner encore en efficacité :

* **Affichage de davantage de couches** (layers) de fabrication.
* **Temps de rendu plus rapide**.
* **Contrôle via tablettes Wi-Fi** déportées pour piloter les projections n'importe où sur le moule.
* **Réduction du taux d’erreur** grâce à la précision millimétrée du laser.

## Contraintes et Défis

Le projet a dû faire face à des contraintes critiques :
* **Production 24/7** : Le système ne peut être arrêté que le dimanche.
* **Délai ultra-serré** : Moins de 3 semaines pour la mise en œuvre sous risque d'arrêt de production.
* **Logistique complexe** : Matériel réseau non commandé à temps via l'ERP.
* **Communication internationale** : Coordination avec les équipes réseau sur différents fuseaux horaires (nécessitant une vigilance accrue sur des détails comme le PoE qui aurait pu réinitialiser la passerelle).

![Infrastructure actuelle d'une baie](/images/projects/laps1.png)

## Objectifs et Développement

L'objectif principal était de migrer vers un système plus robuste fourni par la société *LAP GmbH*, intégré au réseau **OT (Production)**.

### Les étapes clés :
1.  **Évaluation et achat** : Rédaction du cahier des charges et sourcing chez des fournisseurs déjà enregistrés dans l'ERP.
2.  **Configuration PC/Serveur** : Installation d'un PC performant pour contrôler les passerelles et servir de serveur pour les tablettes.
3.  **Segmentation Réseau** : Création de **VLANs distincts** (Modèle Purdue) pour isoler les terminaux de contrôle (tablettes) de la passerelle technique.
4.  **Gestion logicielle** : Utilisation d'une image Windows LTSC ("Vanilla") pour contourner les restrictions de sécurité standard qui bloquaient les ports nécessaires au logiciel *MT PRO-SOFT*.

## Conclusion

Malgré les défis logistiques, la migration a été réalisée dans les délais. Les résultats sont concrets :
* **Satisfaction des utilisateurs** et des ingénieurs méthodes.
* **Mises à jour simplifiées** des plans de fabrication.
* **Infrastructure pérenne** prête pour les futures évolutions demandées par le groupe.

Ce projet illustre l'importance de la flexibilité informatique en milieu industriel : savoir adapter les solutions techniques (Windows LTSC, VLANs dédiés) pour répondre aux impératifs de la production.