---
title: Journal Février
date: 2024-02-16T07:07:07+01:00
tags: [news,life,blog,work,jeux]
---

## Février 2024
Négligeance de ma part, aucune nouvelle depuis le nouvel an.

### L'actuel

Dûs a des rénovations au travail je n'ai pu terminer MarioRPG remake en totalité.<p>
Construction d'un nouvel ordinateur gamer pour faire différent j'ai décider d'essayer un <b>AMD 7950X3D</b> au lieu du i9 14ieme génération.

### Serveur
Liste rapide des tâches effectués depuis.

* Une migration complète de mon serveur maison fût effectuer en mi-janvier.
* Remplacement du vieux serveur Xeon par mon ancienne machine de gaming i9-9900k.
* Changer le i9 de boitier pour un Fratal Design ( meilleur qualité et plus d'espace disque ) 
* Ajout de 4 x disque de 20TB pour migrer le contenu du serveur debian.
* Achat de licensse Unraid pour le nouveau serveur.
* Plex utilise maintenant une 1080ti pour video transcoding.
* Apprentissage des fonctionnalitées Unraid.
* Installation des docker et migration de config.

### Unraid
Pourquoi unraid?

J'avais plusieurs disques de différents size et TrueNAS scale me pénalisais énormément en espace avec ces parité Raid. sous Unraid une clé usb pour le os, les anciens disques NVME devienne des cache temporaire qui sont vider sur le array au heures et le array est capable de se reconstruire avec 1 seul disque de 20TB ( bien évidemment je vais en rajouter d'avantage par la suite ) </p>
 
#### Les services que je n'utilise plus
 * Nginx Proxy Manager ( remplacé par CaddyV2 )
 * Scrutiny
 * Uptime Kuma
 * AMP control panel ( pour l'instant vu sa limitation sous docker donc par conséquent unraid )
 * Wireguard ( Remplacé par tailscale )
 * Guacamole ( Unraid ne nécessite pas de ssh bien que disponible )
 * Paperless NGX ( Était très peu utilisé )
 * IdleRPG ( Bot inutile irc )

 