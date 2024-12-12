---
title: "Preparation de l'environnement"
date: 2025-01-01 09:00:00 +0100
categories:
  - Infrastructure
tags:
  - Proxmox
  - Virtualisation
  - Homelab
excerpt: "Utilisation d'un MiniPC qui traine pour installer Proxmox"
header:
  overlay_image: /assets/images/headers/2025-01-01-proxmox-banner.png
  overlay_filter: 0.5
toc: true
toc_sticky: true
---

Tout blog technique qui se respecte nécessite un environnement de test fiable. C'est dans cette optique que j'ai décidé de ressusciter un vieux MiniPC qui prenait la poussière pour en faire un lab pour ce blog.

## Le matériel :

Mon choix s'est porté sur un **HP Prodesk mini** compact et économe en énergie. Il sera capable de gerer plusieurs VMs de tests avec sa configuration :
- Processeur 
-  Go de RAM
- SSD de 256 Go
- Consommation électrique réduite

## Qu'est-ce que Proxmox ?

**Proxmox VE** est une plateforme de virtualisation open source basée sur Debian. Elle combine deux technologies de virtualisation majeures :
- La virtualisation KVM pour des machines virtuelles complètes
- Les conteneurs Linux (LXC) pour une virtualisation légère

Son interface web intégrée permet de gérer facilement :
- La création et la gestion des VMs et conteneurs
- Les ressources système (stockage, réseau, mémoire)
- Les sauvegardes et snapshots
- Les mises à jour du système

## Les alternatives envisagées

- **VMware ESXi**
  - Solution mature et entreprise
  - Interface web complète
  - Version gratuite limitée
  - Ressources nécessaires trop importantes

- **XCP-ng**
  - Fork open source de Citrix XenServer
  - Interface Xen Orchestra puissante
  - Communauté active
  - Courbe d'apprentissage plus raide

- **OpenShift**
  - Plateforme complète d'orchestration Kubernetes
  - Excellent pour le déploiement d'applications cloud-native
  - Fonctionnalités DevOps avancées
  - Trop complexe et gourmand pour un simple homelab
  - Nécessite plus de ressources qu'un hyperviseur classique

- **Virtualbox**
  - Simple à prendre en main
  - Parfait pour le poste de travail
  - Moins adapté à un usage serveur
  - Pas d'interface web native

## Pourquoi avoir choisi Proxmox ?

Proxmox s'est imposé pour plusieurs raisons :
- Solution 100% open source
- Interface web intuitive et complète
- Support natif des conteneurs LXC
- Gestion simple des snapshots
- Base Debian familière
- Communauté active et documentation riche

## Installation et configuration de base

L'installation de Proxmox a été remarquablement simple :
1. Téléchargement de l'ISO sur le site officiel
Ajouter image
2. Création d'une clé USB bootable
Ajouter image
3. Installation en suivant l'assistant
Ajouter image
4. Configuration réseau basique
Ajouter image

## Les premiers pas

Afin de m'assurer que tout fonctionne correctement, j'ai créé une machine virtuelle Ubuntu Server 24.10 (j'avais l'ISO sous la main).
Ajouter image

## La suite ?

Cet environnement servira de base pour tous les articles à venir. Il me permettra de :
- Tester des configurations système
- Me faire plaisir avec différentes technologies
- Documenter précisément mes manipulations
- Garantir la reproductibilité des tutoriels

Dans le prochain épisode, nous verrons... Je ne sais pas encore, tiens!
