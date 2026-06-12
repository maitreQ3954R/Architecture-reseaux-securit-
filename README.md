# 🌐 Architecture Réseau Sécurisée - Cisco Packet Tracer

## 📝 Description du projet
Ce projet présente la conception et la sécurisation d'une infrastructure réseau d'entreprise entre pluiseurs villes sur Cisco Packet Tracer. L'objectif principal est de segmenter le réseau et de restreindre les accès administratifs pour garantir une sécurité optimale.

## 🖼️ Topologie Réseau
![Topologie du réseau](./d94045a5-2d38-4484-96ee-b8d2602f686c.jpg)

## 🛠️ Technologies et Protocoles Configurés
* **Sécurisation SSH (v2) :** Activation du protocole SSH sur les lignes VTY des switchs et routeurs avec authentification locale (`login local`).
* **Contrôle d'accès (ACL) :** Mise en place d'une **Access Control List Standard** (via la commande `access-class in`) appliquée sur les lignes VTY pour autoriser **uniquement** l'adresse IP du `PC-ADMIN` à se connecter en SSH. Tous les autres équipements du LAN sont bloqués.
* **Adressage et Passerelles :** Configuration des interfaces virtuelles (SVI) sur le VLAN 1 des switchs (`interface vlan 1`) avec attribution d'IPs dédiées et configuration du `ip default-gateway`.
* serurisation des ports : activation du violations restrict ou shutdown sur chaque por pc


## 🚀 Comment tester et valider le projet ?
1. Télécharge le fichier zip dans le projet
2. Extraire le zip puis ovrir le fichier pkt
3. fais des ping entres les pc de differents routers pour testé la connectivité ( le premier fais souvent fail) sa fera succecful
4. Depuis le **PC-ADMIN**, ouvre l'invite de commande  pour tous les routers 'ssh -l levy [ip_du_lan] et ils ont tous le meme mots de passe qui cisco ex pour le lan 2 faites 'ssh -l levy 172.16.20.1" mot de passe 'cisco' et l'enable secret est cisco
5. Depuis n'importe quel autre PC (ex: `PC-LBV`ou 'PC-FRAN'), tente la même commande -> La connexion est instantanément refusée par l'ACL.
6. toucher un switch le mot passe et l'enable mot de passe est 'cisco' puis faites show porsecurity pour voir la secuté appliqué sur les port de chaque pc (rectrict et shutdown)
