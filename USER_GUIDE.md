<div align="center"><h1>Documentation Utilisateur</h1></div>

## Se connecter à l'interface de Sécurity Onion 

Une fois Security Onion installé :
  
Ouvrez un navigateur web et entrer l'adresse IP du server security Onion :

![image](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTOS_USER/saisie_adresse_IP_OK.png)
  
Connectez vous à l'interface Security Onion en entrant vos identifiants :
  
![image](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTOS_USER/login_user.png)

_________________________________________

## Présentation de l'interface utilisateur

Bienvenue dans l'interface avec les différents panels, analyse de gestions des alertes et seuil d'alerte.
Depuis la barre de navigation sur la gauche de l'interface, vous pouvez accéder aux principaux panneaux d'information et de surveillance suivant :

### OVERVIEW :
Ecran d'atterissage à la connexion au serveur. Cette écran permet d'accéder à l'aide du logiciel (en anglais), d'afficher la version du logiciel, ses nouveautés, son développement en cours.

![image](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTOS_USER/overview_panel02.png)

### ALERTS :
Centralise les différentes alertes configurés dans Security Onion.

![image](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTOS_USER/alert_pannel_overview.png)

### DASHBOARDS ( tableau de bord ) :
Permet de visualiser les activités sur le server et de cibler certains événements avec précision :

![image](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTOS_USER/dashboard_pannel.png)

### HUNT :
Permet d'ennquêter, de manière flexible et rapide, sur les alertes remontées.

![image](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTOS_USER/hunt_pannel.png)

### GRID :
Affiche le status du server et des nodes connectés sur la grille de Security Onion.

![image](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTOS_USER/grid_pannel.png)

________________________________________________________________________________

===============================================
# A SUPPRIMER
> ADMINISTRATION :
* users : liste et gestion des utilisateurs avec leurs identifiants.
* configuration : configurer les aspects du logiciel avec toutes les options, dans l’onglet _Global_ 
===============================================


## Utilisation de base : Comment utiliser certaine fonctionnalités clés de Security Onion

### Filtrer des événements
Cliquer sur la flêche permet de dérouler le menu des filtres d'événements prés-configurer dans Security Onion

![image](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTOS_USER/dashboard_filtrer-event.png)

Ici nous sélectionnons le filtre "connec failur" afin d'afficher les erreurs de connexion à un équipement
 déscendre pour consulter le journal
 exemple d'evennement (connexion failur) 

 - Clic droit sur une alerte pour en connaître les détails, toutes les informations concernant la menace. 
  
- Passer à Hunt, interface qui cible plus précisemmment les requêtes en regroupant plusieurs champs du Tableau de bord, etudiez et étendre votre recherche, les journaux supplémentaires relatifs aux adresses IP source et de destination.
  
- Si l'une de ces alertes, vous semble intéressantes passer PCAP ( packet capture ) interface de programmation permettant de capturer un trafic réseau pour examiner.

- En fonction de vos recherches, envoyez a CyberChef pour une analyse et un décodage plus approfondie.

- Transférez les alertes et les journaux vers les dossiers. Passez à la rubrique _Hunt_ pour élargir votre champ d'action.

- Si vous avez déployé ElasticAgent, rechercher des journaux d'hôte supplémentaires ou exécuter des requêtes à l'aide d'osquery.
  
- Enfin, revenez aux dossiers et documentez l’intégralité de l’enquête et fermez le dossier.

## Utilisation avancée : comment utiliser au mieux les options

Sécurity Onion, permet la sauvegarde quotidienne de certains fichiers afin de pouvoir récupérer ces derniers en cas de panne. 


Une sauvegarde quotidienne est disponible _/nsm/backup/_ 

![](https://docs.securityonion.net/en/2.4/_images/config-item-backup.png)

ainsi une duplication de sauvegarde est possible vers un emplacement extérieur. Cependant les données ElasticSearch ne sont pas sauvegardeés automatiquement.


## FAQ : solutions aux problèmes connus et communs liés à l'utilisation
"comment puis je utiliser tel outil ?"
"comment puis je surveiller cet objet ?"
"reformuler sous forme de question la doc déjà présente"
