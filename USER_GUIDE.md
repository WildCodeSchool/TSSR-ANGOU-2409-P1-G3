<div align="center"><h1>Documentation Utilisateur</h1></div>

## Se connecter à l'interface de Sécurity Onion 

- Une fois Security Onion installé :
  
- Ouvrez un navigateur web (IMAGE)
  
- Connectez vous à l'interface Security Onion :
identifiant et mot de passe (IMAGE)

=======================================================
# Présentation de l'interface utilisateur

 - Bienvenue dans l'interface avec les différents panels et analyse de gestions des alertes et seuil d'alerte.

> OVERVIEW : IMAGE
Ecran de présentation, description, version du logiciel, les nouveautés de la version

> ALERTS IMAGE
Centre des différentes alertes générées, afficher par type, count,  HIDS, NIDS, permet l’examen des alertes reçues. clic droit >  _DrillDown_ pour avoir des informations 

fleche d’une alerte : toutes les caractéristiques d’une alerte avec le type de journal 

> DASHBOARDS ( tableau de bord ) : IMAGE
Visualisation simple, graphique et diagramme des anomalies détéctées
plusieurs tableaux de bords sont disponibles 

> HUNT IMAGE
Enquête, flexible et rapide des alertes remontées, filtres point d'analyses récupération de données pour détecter les intrusions ou les menaces

> CASES :
outil de gestion des cas, documentation, partie intégrer au flux du travail


> GRID :


===============================================
# A SUPPRIMER
> ADMINISTRATION :
* users : liste et gestion des utilisateurs avec leurs identifiants.
* configuration : configurer les aspects du logiciel avec toutes les options, dans l’onglet _Global_ 
===============================================


## Utilisation de base : Comment utiliser les fonctionnalités clés

Flux de travail : 
- Alertes et examinez les alertes non reconnues (cliquez sur alertes
  
- Consultez le tableau de bord
  # SYNTHETISER le menu déroulan
cliquer sur la flèche pour afficher les informations supplémentaires 
sélectionner HTTP, pour filtrer les données collectées pour votre réseau. 

![image](https://github.com/user-attachments/assets/ab071ac4-8d84-4f84-8b45-ea250a2c0be7)

![Dashboard _ SecurityOnion](https://docs.securityonion.net/en/2.4/_images/53_dashboards.png)

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
