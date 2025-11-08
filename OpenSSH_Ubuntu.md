# IV. Installation du Client Linux#

### 2. Mise en place du serveur SSH

Installation de la suite logicielle OpenSSH sur un client Linux, dans le cas présent sur la version d'Ubuntu 24.04 LTS à jour pour le lier à une machine vituelle serveur Linux et se connecter dessus. Le serveur en question est l'OS Debian 13.1.0 CLI (interface d'invite de commandes).  

---

- Mettre en route la machine Ubuntu qui se nomme ici "ubu01".

- Ouvrir le Terminal. (Se référer au 1. pour le localiser.)

![Image01](https://github.com/WildCodeSchool/TSSR-1025-P1-G1/blob/main/Ressources/Screens_INSTALL/Client_Linux%20/OpenSSH/01_OpenSSH_Client_Linux.png)

---

- Entrer la ligne de commande `apt install openssh-client` pour installer le client OpenSSH.
- On constate qu'un message d'erreur apparaît concernant les droits utilisateurs.

- On force l'installation en ajoutant la commande `sudo` à la précédente ligne de commande : `sudo apt install openssh-client`.

![Image02](https://github.com/WildCodeSchool/TSSR-1025-P1-G1/blob/main/Ressources/Screens_INSTALL/Client_Linux%20/OpenSSH/02_OpenSSH_Client_Linux.png)

---


- Ne pas oublier d'ajouter le mot de passe permettant d'accéder aux droits administrateurs.

- Laisser l'installation s'opérer.

![Image03](https://github.com/WildCodeSchool/TSSR-1025-P1-G1/blob/main/Ressources/Screens_INSTALL/Client_Linux%20/OpenSSH/03_OpenSSH_Client_Linux.png)

---

- Une fois l'installation effectuée, mettre en route à côté la machine serveur Linux (Debian), ici nommée "srvlx01".

- Se connecter en tant qu'administrateur et entrer son mot de passe.

![Image04](https://github.com/WildCodeSchool/TSSR-1025-P1-G1/blob/main/Ressources/Screens_INSTALL/Client_Linux%20/OpenSSH/04_OpenSSH_Client_Linux.png)

---

- Vérifier si l'OS est à jour avec la ligne de commande `apt install update && apt upgrade`. (Ce dernier est à jour dans le cas présent.)

![Image05](https://github.com/WildCodeSchool/TSSR-1025-P1-G1/blob/main/Ressources/Screens_INSTALL/Client_Linux%20/OpenSSH/05_OpenSSH_Client_Linux.png)

---

- Installer le serveur OpenSSH avec la commande `apt install openssh-server`.

![Image06](https://github.com/WildCodeSchool/TSSR-1025-P1-G1/blob/main/Ressources/Screens_INSTALL/Client_Linux%20/OpenSSH/06_OpenSSH_Client_Linux.png)

---

- Vérifier le statut d'OpenSSH avec la commande `systemctl status ssh`.

- S'il n'est pas actif comme indiqué dans les lignes "Loaded" (2x "enabled" en vert) et "Active" ("active (running)" en vert), entrer les commandes à la suite les commandes `systemctl start ssh` et `systemctl enabled ssh` pour activer le service SSH.

![Image07](https://github.com/WildCodeSchool/TSSR-1025-P1-G1/blob/main/Ressources/Screens_INSTALL/Client_Linux%20/OpenSSH/07_OpenSSH_Client_Linux.png)

---
- Laisser de côté "srvlx01" et revenir sur "ubu01". Taper ensuite la ligne de commande `ssh nom_utilisateur@adresse_ip_ou_nom_du_serveur`.
Ici le nom d'utilisateur est "wilder" et le nom du serveur est "srvlx01", comme celui de la machine, avec comme adresse ip 172.16.10.6 auparavant indiqué dans les prérequis) pour créer une clé SSH avec la machine "srvlx01".
 
- Taper `yes` et taper ensuite le mot de passe de la machine "srvlx01" (préalablement choisi dans la partie II).

![Image08](https://github.com/WildCodeSchool/TSSR-1025-P1-G1/blob/main/Ressources/Screens_INSTALL/Client_Linux%20/OpenSSH/08_OpenSSH_Client_Linux.png)

---
- On constate bien un changement nom de machine à côté du `@` .

![Image09](https://github.com/WildCodeSchool/TSSR-1025-P1-G1/blob/main/Ressources/Screens_INSTALL/Client_Linux%20/OpenSSH/09_OpenSSH_Client_Linux.png)

### **Voilà, vous avez connecté le client Linux au serveur Linux !**
 
