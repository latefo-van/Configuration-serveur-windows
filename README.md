  
  
  # 🖥️ Projet - Installation et préparation d’un serveur Windows

Ce projet a pour objectif de documenter l’installation d’un serveur Windows dans une machine virtuelle VirtualBox, en vue de ma préparation au BTS SIO SISR.

---

## 🔧 Étape 1 – Création de la machine virtuelle

- J’ai utilisé **VirtualBox** pour créer une nouvelle machine virtuelle.
- Nom de la machine : `SRV-AD1`
- Type : Microsoft Windows
- Version : Windows 2022 (64-bit)
- J’ai alloué :
  - 2048 Mo de RAM
  - 1 disque dur virtuel VDI de 50 Go

---

## 💿 Étape 2 – Installation de Windows Server

- J’ai téléchargé l’ISO de **Windows Server 2022**
- Je l’ai monté dans la machine via **Paramètres > Stockage > Lecteur optique**
- L’installation de Windows Server s’est déroulée sans problème
- J’ai défini un mot de passe administrateur et accédé au Bureau

---

## 🖥️ Étape 3 – Renommer la machine

- Je suis allé dans :
  `Panneau de configuration > Système > Paramètres système avancés > Nom de l’ordinateur`
- J’ai changé le nom en **SRV-AD1**
- J’ai redémarré la machine pour appliquer le changement

📸 Capture :  
![Nom du serveur](./images/nom-serveur.png)

---

## 📋 Étape 4 – Clonage de la machine

- Avant de continuer les configurations réseau ou serveur, j’ai préféré **cloner la machine**
- Dans VirtualBox, j’ai fait :
  `Clic droit > Cloner > Clonage complet`
- J’ai choisi :
  - Nom du clone : `SRV-AD1-Clone`
  - Reset MAC address : ✅ Oui
  - Preserve disk names :  Pas necessaire
  - Keep hardware UUIDs : ❌ Non
- Ce clone servira de sauvegarde de sécurité

📸 Capture :  
![Clonage VM](./images/clonage-vm.png)

---

## 📋 Étape 5 – Vérification de l'accès à Internet sur la VM


Après avoir clonée la machine en  `SRV-AD1-Clone`, j'ai vérifié l'accès à Internet en utilisant le ping


    Test avec la commande `ping`

J'ai ouvert l'invite de commande (`cmd`) et exécuté la commande suivante pour tester la connectivité avec un serveur DNS public (Google DNS) :

ping 8.8.8.8

📸 Capture :
 ![commande ping] (./images/ping-internet.png)
 
---


## ✅ Prochaine étape 6 – Configuration réseau



## Configuration de l'adresse IP

Après avoir cloné ma machine virtuelle, j'ai configuré les paramètres IP.

Pour vérifier la bonne configuration, j’ai ouvert l’invite de commandes (`cmd`) et j’ai utilisé la commande suivante :

ipconfig


📸 Capture à venir : `config-reseau1.png` ET `config-reseau2.png`

---

## Étape 7 : Installation du rôle Active Directory Domain Services (AD DS)

J’ai installé le rôle AD DS (Active Directory Domain Services) sur mon serveur afin d’en faire un contrôleur de domaine.

1. J’ai lancé le **Gestionnaire de serveur** puis cliqué sur **Ajouter des rôles et fonctionnalités**.
2. J’ai sélectionné le rôle **AD DS** dans la liste des rôles proposés.
3. J’ai poursuivi les étapes de l’assistant jusqu’à l’installation complète du rôle.

Les deux captures ci-dessous illustrent cette installation :

- `nom-de-domaine-ad.png` : Capture de l’ajout du nom AD DS dans le Gestionnaire de serveur.
- `installation-terminee.png` : Capture confirmant que le rôle a bien été installé.

> Ces étapes montrent que le rôle Active Directory Domain Services est bien actif sur le serveur, prêt à être configuré comme contrôleur de domaine.




























---

## 🧑‍🎓 Réalisé par LATEFO Vanessa

> Étudiant en BTS SIO SISR – Projet personnel de virtualisation système.
