#4. Installation du Client Linux#

Installation de l'application OpenSSH, sur un client Linux, dans le cas présent sur la version d'Ubuntu 24.04 LTS à jour pour le lier à une machine vituelle serveur Linux et se connecter dessus. Le serveur en question est l'OS Debian 13.1.0 CLI (interface d'invite de commandes).  

- Mettre en route la machine Ubuntu qui se nomme ici "ubu01".
- Ouvrir le Terminal.  
- Entrer la ligne de commande `apt install openssh-client` pour installer le client OpenSSH.  
- On constate qu'un message d'erreur apparaît concernant les droits utilisateurs.  
- On force l'installation en ajoutant la commande `sudo` à la précédente ligne de commande : `sudo apt install openssh-client`
- Ne pas oublier d'ajouter le mot de passe permettant d'accéder aux droits administrateurs.
- Une fois l'installation effectuée, mettre en route à côté la machine serveur Linux, ici nommée "srvlx01".
- Se connecter en tant qu'administrateur et entrer son mot de passe.
- Vérifier si l'OS est à jour avec la ligne de commande `apt install update && apt upgrade` (Ce dernier est à jour dans le cas présent.)
- Installer le serveur OpenSSH avec la commande `apt install openssh-server` 
- Vérifier le statut d'OpenSSH avec la commande `systemctl status ssh`.
- S'il n'est pas actif comme indiqué dans les lignes "Loaded" (2x "enabled" en vert) et "Active" ("active (running)" en vert), entrer les commandes à la suite les commandes `systemctl start ssh` et `systemctl enabled ssh` pour activer le service ssh.
- Laisser de côté "srvlx01" et revenir sur "ubu01". Taper ensuite la ligne de commande `ssh nom_utilisateur@adresse_ip_ou_nom_du_serveur` (ici le nom d'utilisateur est "wilder" et le nom du serveur est "srvlx01", comme celui de la machine, avec comme adresse ip 172.16.10.6 auparavant indiqué dans les prérequis) pour créer une clé SSH avec la machine "srvlx01".
- Taper `yes`.
- Taper le mot de passe de la machine "srvlx01".
- On constate bien un changement nom de machine à côté du @.
- Voilà, vous avez connecté le client Linux au serveur Linux !
 
