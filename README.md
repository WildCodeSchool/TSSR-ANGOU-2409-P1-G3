# Projet 1 - Groupe 3 - Sujet : Plateforme de surveillance de sécurité

## Présentation du projet, objectifs finaux

L'objectif principal de ce projet est de mettre en place une plateforme de surveillance réseau, via l'utilisation du logiciel Security Onion, tout en réalisant une documentation complète et correcte.

Un objectif secondaire est proposé et consiste à initier des règles de détection d'intrusion.

## Introduction : Mise en contexte

Le logiciel Security Onion est utilisé dans différents buts. Il permet la traque des menaces, la surveillance de la sécurité des entreprises et la gestion des journaux. 

## Membres du groupe de projet (rôle par sprint)

### Rôles Sprint semaine 1

> Mathieu Leroux : _Scrum Master_  
> Thomas Garreau : _Technicien_  
> Axel Charpentier : _Product Owner_  

### Rôles Sprint semaine 2

> Mathieu Leroux : __  
> Thomas Garreau : __  
> Axel Charpentier : __  

### Rôles Sprint semaine 3

> Mathieu Leroux : __  
> Thomas Garreau : __  
> Axel Charpentier : __  

## Outils utilisés

[Miro](https://miro.com/app/board/uXjVLUlrqs8=/)

## Choix techniques : quel OS, quelle version, etc

> OS : Security Onion 2.4
> Type : Linux
> Version : Oracle Linux 9.x


## Spécifications du logiciel

Flux de travail : 
- Alertes et examinez les alertes non reconnues 
- Consultez le tableau de bord
  
 ![Dashboard _ SecurityOnion](https://docs.securityonion.net/en/2.4/_images/53_dashboards.png)
  
- Passer à Hunt pour etudiez et étendre votre recherche, les journaux supplémentaires relatifs aux adresses IP source et de destination.



- PCAP ( packet capture ) interface de programmation permettant de capturer un trafic réseau


Logiciels inclus dans Security Onion 

> **SURICATA**, une détection basée sur les signatures, c’est un outil intégré au logiciel Sécurity Onion, un moteur d’alerte qui permet la détection des menaces et d’intrusions réseaux en inspectant le trafic, reporter dans l'onglet Alertes du logiciel. 

> **ZEEK, ancien nom BRO** 
Protocole et l’extraction de fichiers, outil permettant la surveillance réseau, il signale à la fois la perte de paquets et la perte de capture via Stenographer et l’analyse de fichiers via Strelka.

> **ELASTIC SEARCH** 
Pour la visibilité des hôtes, Security Onion propose ElasticAgent, qui assure la collecte des données ainsi le moteur ElasticSearch, utilisé pour l'analyse et la visualisation des journaux, la recherche en texte intégral, la veille sécuritaire, l'analytique commerciale et l'intelligence opérationnelle. les requêtes en direct via osquery et la gestion centralisée à l’aide d’Elastic Fleet. Elasticsearch est devenu le moteur de recherche d’entreprise le plus populaire. 

Sécurity Onion, permet la sauvegarde quotidienne de certains fichiers afin de pouvoir récupérer ces derniers en cas de panne. Une sauvegarde quotidienne est disponible _/nsm/backup/_ 

![](https://docs.securityonion.net/en/2.4/_images/config-item-backup.png)

ainsi une duplication de sauvegarde est possible vers un emplacement extérieur. Cependant les données ElasticSearch ne sont pas sauvegardeés automatiquement.




## Difficultés rencontrées : problèmes techniques rencontrés

## Solutions trouvées : Solutions et alternatives trouvées

## Améliorations possibles : suggestions d’améliorations futures
