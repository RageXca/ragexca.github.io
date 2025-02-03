---
title: Idée Projet Mini-PC
date: 2024-10-21T07:07:07+01:00
tags: [github,projet,computer,Nas,serveur]
---
# Project de Mini-PC
En liens avec un [MINI-ITX board BD790i](https://store.minisforum.com/products/minisforum-bd790i)

Une charte PCI-Express lane speed selon les générations.
![Vitesse approximative des lanes pci-express](https://l.ragex.ca/mg)

**RTX 2080 PCI-E 3.0 x16** ( Connecteur 16x prennant 16 lanes 3.0 ( Supposément 8 lanes change rien au performance mais bon ) 

*8x Lanes 3.0* = 8GB/s 16x Lanes 3.0 = 16GB/s

**LSI SAS 9201-16e PCI Express to 6Gb/s SAS HBA** ( Connecteur 16x prenant 8 lanes 2.0 ) 

*8x Lanes 2.0* = 4GB/s bandwith 

Le hic je ne trouve pas d’adapteur de bifurcation dans le PCI-E 5.0 ceux disponible sont dédié a des NVME.

Les adapteur powered que je trouve sont Connecteur 16x 4.0 divisé en 2 connecteur 16x avec 8lanes 4.0 donc 16GB/s par prise.
De plus ceux ci on très peu d’espace entre chaque connecteur donc requiert un riser 16x dans une des deux prises pour installer un GPU de transcoding.

Comme celui-ci ![Adapteur de Bifurcation PCI-Express 4.0](https://l.ragex.ca/mh)
La carte mère du itx board avec le dernier update supporte x8/x4/x4 ou 4x4x4x4 reste a vérifier si le x8/x8 est aussi bien supporté sans aucun erreur.

Le site affiche 64GB de ram mais les utilisateurs disent que avec le dernier bios update il est possible d'avoir 96GB DDR5 sodimm.

## Raison de ce build

La carte LSI a pour but de relier les 16 disques dur mecanique dans des hotswap cages
La carte vidéo a pour but d'améliorer le video transcoding et autres tâche relié au images et vidéo.

Un NAS surpuissant avec une capacité de rouler des VM et autres serveurs vue ces nombreux coeurs.
Le tout a faible cout énergétique ( quand la carte vidéo est sur le idle )

## Étapes
1. Installation
    1. Installer la ram
    2. Installer les disques dur nvme.
    3. Installer une fan noctua sur le heatsink présent.
    4. Connecter au boitier choisi les connecteurs présent.
    5. Installer un Bifurcateur 5.0 ( Celui ci doit possèder un alimentation externe additionnel ).
    6. ***(Optionnel)*** Connecter un PCI-Express extender 5.0 pour le GPU ( dépendant du modèle de bifurcateur trouvé ).
    7. Installer le GPU.
    8. Installer la carte LSI.
    9. Installer le cablage SFF to SATA relié au cage hotswap existante.
2. Mettre a jour le bios ( pour 96 gb de ram )
    1. Activer dans le bios le mode birfucation pci-e 8x/8x
    2. Changer le boot order a usb pour unraid
## Quand?
Ce n'est pas pour l'immédiat vu que je ne trouve pas des bifurcateurs 5.0 et qu'une prochaine version de carte mère avec processeur de laptop pourrait bientot faire surface.

Le coût estimer du project 700 CAD pour la carte mère en spécial , 600 CAD pour la ram, 150 CAD pour le boitié. Je possède déjà le GPU/Power Supply/Carte LSI.
:\