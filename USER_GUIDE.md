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
Depuis le panneau Dashboard, cliquer sur la flêche permet de dérouler le menu des filtres d'événements prés-configurer dans Security Onion

![image](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTOS_USER/dashboard_filtrer-event.png)

Ici nous sélectionnons le filtre __SOC Login event Failures__ afin d'afficher les erreurs de login à un équipement enregistrées par Security Onion.

![image](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTOS_USER/dashboard_filtres_login_faileur.png)

Déscendre vers le bas de la page pour consulter le journal d'évenement

![image](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTOS_USER/dashboard_pannel_scrolldown.png)

Le journal d'événement s'est mis à jour avec le filtre d'évenement séléctionné

![image](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTOS_USER/dashbord_event_filtrer_update.png)

### Activer/Désactiver des stratégies et méthodes de sécurité
Security Onion intègre de nombreuses stratégies de surveillance prédéfinit qu'il est possible d'activer (ou désactiver) via le panneau __Detections__

![image](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTOS_USER/detection_pannel_scroll_down.png)

En bas du panneau __Detections__, séléctionnez la stratégie de surveillance que vous voulez ajouter à Security Onion.
Ici nous séléctionnons les tentatives des connexion, via le protocole HTTP, à la node IDH de notre server.

![image](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTOS_USER/detection_event_selection_pannel.png)

Une fois la stratégie séléctionnée, remontez la page __Detections__. 
La champs des filtres s'est automatiquement complété.
Cliquez sur l'icone symbolisant une cible pour lancer la stratégie et être automatiquement redirigé sur le panneau __Alertes__ afin de visualiser ses résultats.

![image](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTOS_USER/detection_pannel_majfiltre_lancer-alert.png)

## FAQ : solutions aux problèmes connus et communs liés à l'utilisation

Comment accéder à l'interface de mon server Security Onion ?
Puis-je rechercher spécifiquement certains événements de l'activité de mon réseaux grâce au logiciel Security Onion ?
Comment afficher les echecs de connexion aux équipements de mon réseau ?
Est-il possible de vérifier l'état d'une node de mon réseau avec Security Onion ?
Est-il possible d'installer une node IDH avec Security Onion ?
