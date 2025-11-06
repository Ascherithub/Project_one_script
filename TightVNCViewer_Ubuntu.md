#4. Installation du Client Linux#

Installation d'une application VNC, TightVNCViewer, sur un client Linux, dans le cas présent sur la version d'Ubuntu 24.04 LTS à jour pour le lier à une machine virtuelle serveur Windows et se connecter dessus. Le serveur en question est l'OS Windows Server 2022 GUI (interface graphique), préalablement installé et configuré de TightVNCServer (Voir partie 1).  


- Mettre en route la machine Ubuntu qui se nomme ici "ubu01".
- Ouvrir le Terminal.  
- Entrer la ligne de commande `apt install xtightvncviewer` pour installer le logiciel TightVNCViewer.  
- On constate qu'un message d'erreur apparaît concernant les droits utilisateurs.  
- On force l'installation en ajoutant la commande `sudo` à la précédente ligne de commande : `sudo apt install xtightvncviewer`
- Ne pas oublier d'ajouter le mot de passe permettant d'accéder aux droits administrateurs.
- Une fois l'installation effectuée, mettre en route à côté la machine serveur Windows, ici nommée "srvwin01".  
- Vérifier que le processus TightVNCServer est bien actif : 
  Deux manières de faire :
  * Avec une invite de commandes ou plus communément appelé "Shell" :
    - Rechercher dans la barre de recherche le logiciel "PowerShell".
    - Ouvrir PowerShell en tant qu'Administrateur avec une action de clic droit dessus.
    - Taper la ligne de commande `Get-Process -Name tvnserver`.
    - On constate que le processus "tvnserver" est bien en cours.
    - "tvnserver" étant le processus de TightVNCServer, on peut le vérifier avec la ligne de commande suivante : `Get-Process -Name tvnserver -FileVersionInfo | Format-List`
    - On constate donc que "tvnserver" est en cours et qu'il s'agit bien du processus de TightVNCServer.
  * Sur le GUI ("Graphical User Interface", l'interface graphique de l'utilisateur.) : 
    - Cliquer sur la flèche dans la barre des tâches.
    - Cliquer sur l'icône V entouré d'un carré blanc.
    - On constate bien que TightVNCServer est en cours.

- Laisser de côté "srvwin01" et revenir sur "ubu01". Taper ensuite la ligne de commande `vncviewer srvwin01` pour ouvrir le logiciel TightVNCViewer.
- Taper le mot de passe choisi au préalable sur le serveur VNC sur la machine serveur Windows.
- Une fenêtre se lance : "TightVNC : srvwin01".
- Regarder simuletanément les écrans de "ubu01" et "srvwin01".
- Voilà, vous avez connecté le client Linux au serveur Windows !
