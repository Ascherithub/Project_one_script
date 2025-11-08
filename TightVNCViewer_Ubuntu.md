# IV. Installation du Client Linux
###  1. Installation du serveur VNC

 Installation d'une application VNC, TightVNCViewer, sur un client Linux, dans le cas présent sur la version d'Ubuntu 24.04 LTS à jour pour le lier à une machine virtuelle serveur Windows et se connecter dessus. Le serveur en question est l'OS Windows Server 2022 GUI (interface graphique), préalablement installé et configuré de TightVNCServer (Voir partie I).   

---
 
- Mettre en route la machine Ubuntu qui se nomme ici "ubu01".

- Il vous faut ouvrir le Terminal d'Ubuntu. Cliquer sur le logo d'Ubuntu (Dock) en bas à gauche de l'écran ensuite cliquer sur l'icône sous laquelle est écrit Terminal s'il apparaît.

![Image01](https://github.com/WildCodeSchool/TSSR-1025-P1-G1/blob/main/Ressources/Screens_INSTALL/Client_Linux%20/TightVNC/01_TightVNC_Client_Linux.png)

---
- Sinon rechercher l'application Terminal directement dans la barre de recherche.

- Ouvrir donc le Terminal.

![Image02](https://github.com/WildCodeSchool/TSSR-1025-P1-G1/blob/main/Ressources/Screens_INSTALL/Client_Linux%20/TightVNC/02_TightVNC_Client_Linux.png)

---
- Entrer la ligne de commande `apt install xtightvncviewer` pour installer le logiciel TightVNCViewer.

- On constate qu'un message d'erreur apparaît concernant les droits utilisateurs.

![Image03](https://github.com/WildCodeSchool/TSSR-1025-P1-G1/blob/main/Ressources/Screens_INSTALL/Client_Linux%20/TightVNC/03_TightVNC_Client_Linux.png)

---
- On force l'installation en ajoutant la commande `sudo` à la précédente ligne de commande : `sudo apt install xtightvncviewer`

- Ne pas oublier d'ajouter le mot de passe permettant d'accéder aux droits administrateurs.

![Image04](https://github.com/WildCodeSchool/TSSR-1025-P1-G1/blob/main/Ressources/Screens_INSTALL/Client_Linux%20/TightVNC/04_TightVNC_Client_Linux.png)

---
- Tapez `O` et laissez l'installation s'opérer.

![Image05](https://github.com/WildCodeSchool/TSSR-1025-P1-G1/blob/main/Ressources/Screens_INSTALL/Client_Linux%20/TightVNC/05_TightVNC_Client_Linux.png)

---
- Une fois l'installation effectuée, mettre en route à côté la machine serveur Windows, ici nommée "srvwin01".

<img src="https://github.com/WildCodeSchool/TSSR-1025-P1-G1/blob/main/Ressources/Screens_INSTALL/Client_Linux%20/TightVNC/06_TightVNC_Client_Linux.png" width="500" height="400"/>

---
- Vérifier que le processus TightVNCServer est bien actif :   
  Deux manières de faire :
---
  
  a) Avec une invite de commandes ou plus communément appelé "Shell" :

* Rechercher dans la barre de recherche le logiciel "PowerShell".

* Ouvrir PowerShell en tant qu'Administrateur avec une action de clic droit dessus.
  
![Image07](https://github.com/WildCodeSchool/TSSR-1025-P1-G1/blob/main/Ressources/Screens_INSTALL/Client_Linux%20/TightVNC/07_TightVNC_Client_Linux.png)
   
---
     
* Taper la ligne de commande `Get-Process -Name tvnserver`.

* On constate que le processus "tvnserver" est bien en cours.

![Image08](https://github.com/WildCodeSchool/TSSR-1025-P1-G1/blob/main/Ressources/Screens_INSTALL/Client_Linux%20/TightVNC/08_TightVNC_Client_Linux.png)
   
---
     
* "tvnserver" étant le processus de TightVNCServer, on peut le vérifier avec la ligne de commande suivante :  
`Get-Process -Name tvnserver -FileVersionInfo | Format-List`

* On constate donc que "tvnserver" est en cours et qu'il s'agit bien du processus de TightVNCServer.

![Image09](https://github.com/WildCodeSchool/TSSR-1025-P1-G1/blob/main/Ressources/Screens_INSTALL/Client_Linux%20/TightVNC/09_TightVNC_Client_Linux.png)
      
---
  b) Directement sur l'interface graphique :
 
* Cliquer sur la flèche dans la barre des tâches.
* Cliquer sur l'icône V entouré d'un carré blanc.

* On constate bien que TightVNCServer est en cours.
    
![Image10](https://github.com/WildCodeSchool/TSSR-1025-P1-G1/blob/main/Ressources/Screens_INSTALL/Client_Linux%20/TightVNC/10_TightVNC_Client_Linux.png)
    
---
- Laisser de côté "srvwin01" et revenir sur "ubu01". Taper ensuite la ligne de commande `vncviewer srvwin01` pour ouvrir le logiciel TightVNCViewer.

- Taper le mot de passe choisi au préalable sur le serveur VNC sur la machine serveur Windows.

![Image11](https://github.com/WildCodeSchool/TSSR-1025-P1-G1/blob/main/Ressources/Screens_INSTALL/Client_Linux%20/TightVNC/11_TightVNC_Client_Linux.png)

---
- Une fenêtre se lance : "TightVNC : srvwin01".

- Regarder simultanément les écrans de "ubu01" et "srvwin01".

![Image12](https://github.com/WildCodeSchool/TSSR-1025-P1-G1/blob/main/Ressources/Screens_INSTALL/Client_Linux%20/TightVNC/12_TightVNC_Client_Linux.png)
  

### **Voilà, vous avez connecté le client Linux au serveur Windows !**


