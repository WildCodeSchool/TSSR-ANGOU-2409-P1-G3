# Projet 1 - Groupe 3 - Sujet : Plateforme de surveillance de sécurité

## Présentation du projet, objectifs finaux

L'objectif principal de ce projet est de mettre en place une plateforme de surveillance réseau, via l'utilisation du logiciel Security Onion, tout en réalisant une documentation complète et correcte.

Un objectif secondaire est proposé et consiste à initier des règles de détection d'intrusion.

## Introduction : Mise en contexte

Dans un monde où la cybersécurité prend de plus en plus de place et d'importance, certains logiciels permettent d'assurer une meilleure sécurité des infrastructures réseaux.
C'est le cas du logiciel Security Onion. Cet outil est utilisé dans différents buts. Il est dédié notemment à la surveillance du réseau en traquant les activités suspectes tels que les accès non autorisés, les logiciels malveillants ou tout comportement suspect. Il garantit la surveillance de la sécurité des entreprises et la gestion des journaux. Distribué par l'OS Linux, c'est un logiciel open source téléchargé aujourd'hui par plus de deux millions d'utilisateurs. 


## Membres du groupe de projet (rôle par sprint)

### Rôles Sprint semaine 1

> Mathieu Leroux : _Scrum Master_  
> Thomas Garreau : _Technicien_  
> Axel Charpentier : _Product Owner_  

### Rôles Sprint semaine 2

> Mathieu Leroux : _Technicien_  
> Thomas Garreau : _Product Owner_  
> Axel Charpentier : _Scrum Master_  

### Rôles Sprint semaine 3

> Mathieu Leroux : _Product Owner_  
> Thomas Garreau : _Scrum Master_  
> Axel Charpentier : _Technicien_  

## Outils utilisés

- [Miro](https://miro.com/app/board/uXjVLUlrqs8=/) est un espace de travail collaboratif en lien avec la gestion de projet.
- [Discord](https://discord.com/) est un logiciel de communication (VoIP) et de messagerie instantanée.
- [Github](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3) est une plateforme collaborative qui permet de stocker et d'éditer du code pour différents projets.

## Choix techniques : quel OS, quelle version, etc

> OS : Security Onion 2.4  
> Type : Linux  
> Version : Oracle Linux 9.x  


## Introduction au logiciel Security Onion 
- Policies, procedures, awarenesss 
- Sécurité physique
- Sécurité de périmètre
- Réseau interne
- Sécurité de l'hôte
- Sécurité d'application
- Sécurité des données

Principales Caractéristiques de Sécurity Onion

![](https://github.com/user-attachments/assets/ae80f994-ea60-4e09-af1e-74d3ce353263)


__________________________________________________________________________

### Logiciels inclus dans Security Onion 

Security Onion contient plusieurs outils de NSM ( Network Security Monitoring ).

> **ELASTIC SEARCH** 
Security Onion propose ElasticSearch, qui assure la collecte des données ainsi le moteur, utilisé pour l'analyse et la visualisation des journaux, la recherche en texte intégral, la veille sécuritaire, l'analytique commerciale et l'intelligence opérationnelle. les requêtes en direct via osquery et la gestion centralisée à l’aide d’Elastic Fleet. Elasticsearch est devenu le moteur de recherche d’entreprise le plus populaire. 

> **SURICATA** : logiciel open source de détection d'intrusion (IDS), de prévention d'intrusion (IPS), une détection basée sur les signatures, intégré au logiciel Sécurity Onion, un moteur d’alerte qui permet la détection des menaces et d’intrusions réseaux en inspectant le trafic, reporter dans l'onglet Alertes de l'interface. 

> **ZEEK, ancien nom BRO** : Protocole et l’extraction de fichiers, outil permettant la surveillance réseau, il signale à la fois la perte de paquets et la perte de capture via Stenographer et l’analyse de fichiers via Strelka. 

> **WAZUH** : HIDS Host Intrusion Detection Systems, puissant système de détection d'intrusions machine basé sur OSSEC.

> **STENOGRAPHER**  : outil de capture de paquets, et d'analyse détection d'intrusion et d'incidents. 



## Difficultés rencontrées : problèmes techniques rencontrés

Problème du mode "NAT" : permet à la VM d'accéder à Internet sans pour autant obtenir une adresse IP sur le réseau local. C'est le serveur DHCP de VirtualBox qui va attribuer une adresse IP à la machine virtuelle et non le serveur DHCP du réseau local. VirtualBox va donc créée un réseau local virtuel et isolé du reste des machines physiques. 

ou 

Problème du mode "NAT" : Le mode "NAT" permet un accès des machines du réseau virtuel vers l'extérieur, mais ne permet pas l'accès du réseau externe vers les VM. 

## Solutions trouvées : Solutions et alternatives trouvées

### Product Bakclog

### Retours entretiens client ?

## Améliorations possibles : suggestions d’améliorations futures
