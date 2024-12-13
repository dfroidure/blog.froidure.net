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

Mon choix s'est porté sur un **HP Prodesk mini G5** compact et économe en énergie. Il sera capable de gerer plusieurs VMs de tests avec sa configuration :
- Processeur i5-9500T (6 coeurs)
- 16 Go de RAM
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
1. Téléchargement de l'ISO sur [le site officiel](https://www.proxmox.com/en/downloads/proxmox-virtual-environment/iso)
[Téléchargement de Proxmox](/assets/images/posts/2025-01-proxmox/01-installation.png)
2. Création d'une clé USB bootable avec [BalenaEtcher](https://etcher.balena.io/#download-etcher)
[BalenaEtcher](/assets/images/posts/2025-01-proxmox/02-balena.png)
3. Installation en CLI en suivant l'assistant
[Proxmox CLI](/assets/images/posts/2025-01-proxmox/03-proxmox-cli.png)
4. Configuration réseau basique
[Proxmox réseau](/assets/images/posts/2025-01-proxmox/04-proxmox-network.png)

## Les premiers pas

Afin de m'assurer que tout fonctionne correctement, j'ai créé une machine virtuelle [Ubuntu Server 24.10](https://releases.ubuntu.com/oracular/) (j'avais l'ISO sous la main).

[Upload ubuntu server iso](/assets/images/posts/2025-01-proxmox/05-ubuntu-iso.png)

```bash
starting file import from: /var/tmp/pveupload-18c2633a13f395537db85a1bf16f0a9a
target node: pve
target file: /var/lib/vz/template/iso/ubuntu-24.10-live-server-amd64.iso
file size is: 2098460672
command: cp -- /var/tmp/pveupload-18c2633a13f395537db85a1bf16f0a9a /var/lib/vz/template/iso/ubuntu-24.10-live-server-amd64.iso
finished file import successfully
TASK OK
```

[Install Ubuntu](/assets/images/posts/2025-01-proxmox/06-ubuntu-install.png)

## La suite ?

Cet environnement servira de base pour tous les articles à venir. Il me permettra de :
- Tester des configurations système
- Me faire plaisir avec différentes technologies
- Documenter précisément mes manipulations
- Garantir la reproductibilité des tutoriels

Dans le prochain épisode, nous verrons... Je ne sais pas encore, tiens!
