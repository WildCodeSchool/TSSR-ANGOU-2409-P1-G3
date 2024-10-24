<div align="center"><h1>Projet 1 - Groupe 3 - Sujet : Plateforme de surveillance de sécurité</h1></div>

## Présentation du projet, objectifs finaux

Le but principal de ce projet est la mise en place d'une plateforme de surveillance réseau, via l'installation du logiciel Security Onion et la mise en service d'un réseau pour en comprendre son utilisation et ses capacités mais egalement d'initier des règles de détection d'intrusion afin de prévenir les eventuelles menaces et d'en atténuer les riques.

## Introduction : Mise en contexte

> D'après Forbes : 59 % des employés utilisent encore leur nom d’utilisateur et leur mot de passe comme principal moyen d’authentification de leurs comptes. 3 milliards d’e-mails de phishing sont envoyés dans le monde chaque jour.

Dans un monde où la cybersécurité prend de plus en plus de place et d'importance, une plateforme de cybersécurité est devenu essentielle pour une entreprise dont certains logiciels permettent d'assurer une meilleure sécurité des infrastructures réseaux. 

C'est le cas de Security Onion, outil de détection et de réponses aux menaces d'intrusions visant à renforcer la sécurité des réseaux informatiques. Développé pour répondre aux attentes des entreprises depuis l'attaque de Wannacry en 2017. Cet outil est utilisé dans différents buts. Il est dédié notemment à la surveillance du réseau en traquant les activités suspectes tels que les accès non autorisés, les logiciels malveillants ou tout comportement suspect. Il garantit la surveillance de la sécurité des entreprises et la gestion des journaux. Distribué par l'OS Linux, c'est un logiciel open source téléchargé aujourd'hui par plus de deux millions d'utilisateurs. 

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
| Outils    | Description      |
|---    |:-:    |
| [Miro](https://miro.com/app/board/uXjVLUlrqs8=/)      | Espace de travail collaboratif en lien avec la gestion de projet      |
| [Discord](https://discord.com/)      | Logiciel de communication (VoIP) et de messagerie instantanée      |
| [Github](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3)      | Plateforme collaborative qui permet de stocker et d'éditer du code pour différents projets      |

## Choix techniques : quel OS, quelle version, etc

> OS : Security Onion 2.4  
> Type : Linux  
> Version : Oracle Linux 9.x  


## Introduction au logiciel Security Onion 

Security Onion est une distribution open-source Linux, il est recommandé d'avoir comme système d'exploitation Ubuntu, CentOS étant arrivé a son terme depuis le 30 juin 2024, le choix s'est porté sur Oracle Linux afin de garantir une compatibilité optimale. Son architecture conçue par couches tel un oignon, garanti une surveillance multidimensionnelle et permettant ainsi l'analyse du trafic réseau, la collecte des données, et les alertes sur les menaces potentielles en temps réel.

- Politiques, procédures, sensibilisation
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

Security Onion comprends plusieurs outils de NSM ( Network Security Monitoring ).

> **ELASTIC SEARCH** 
Security Onion propose ElasticSearch, qui assure la collecte des données ainsi le moteur, utilisé pour l'analyse et la visualisation des journaux, la recherche en texte intégral, la veille sécuritaire, l'analytique commerciale et l'intelligence opérationnelle. les requêtes en direct via osquery et la gestion centralisée à l’aide d’Elastic Fleet. Elasticsearch est devenu le moteur de recherche d’entreprise le plus populaire. 

> **SURICATA** : logiciel open source de détection d'intrusion (IDS), de prévention d'intrusion (IPS), une détection basée sur les signatures, intégré au logiciel Sécurity Onion, un moteur d’alerte qui permet la détection des menaces et d’intrusions réseaux en inspectant le trafic, reporter dans l'onglet Alertes de l'interface. 

> **ZEEK, ancien nom BRO** : Protocole et l’extraction de fichiers, outil permettant la surveillance réseau, il signale à la fois la perte de paquets et la perte de capture via Stenographer et l’analyse de fichiers via Strelka. 


## Difficultés rencontrées : problèmes techniques rencontrés

Problème du mode "NAT" : permet à la VM d'accéder à Internet sans pour autant obtenir une adresse IP sur le réseau local. C'est le serveur DHCP de VirtualBox qui va attribuer une adresse IP à la machine virtuelle et non le serveur DHCP du réseau local. VirtualBox va donc créée un réseau local virtuel et isolé du reste des machines physiques. Le mode "NAT" permet un accès des machines du réseau virtuel vers l'extérieur, mais ne permet pas l'accès du réseau externe vers les VM. De plus, ce mode réseau ne permet pas aux VMs de communiquer entre elles.

Problème du mode "Accès par pont" : Une fois l'installation de l'OS terminée et donc le lancement du serveur. Il n'était pas possible de se connecter à l'adresse IPv4 du serveur sur le navigateur et d'accéder à l'interface Web.

## Solutions trouvées : Solutions et alternatives trouvées

Solution mode "NAT" : pour remédier aux problèmes liés à cette configuration pour l'installation de l'OS, nous avons choisi le mode "Accès par pont".

Solution mode "Accès par pont" : 

* Passer la carte réseau de l'OS Serveur en "Réseau privé hôte".

* La machine hôte est l'ordinateur de la personne qui lance le serveur sur son virtualbox : Ouvrir les paramètres Réseau et Internet de l'ordinateur ==> Paramètres réseau avancés ==> Clic gauche la carte réseau VirtualBox Host-Only Ethernet Adapter ==> Modifier ==> Double Clic sur Protocole Internet version 4 (TCP/IPv4) ==> Utiliser l'adresse IP suivante ==> Entrer l'adresse IP : 172.16.10.40 et masque de sous-réseau : 255.255.255.0 ==> OK.

* Configuration de la carte Virtualbox depuis Fichiers ==> Outils ==> Network Manager ==> Clic gauche sur la carte : VirtualBox Host-Only Ethernet Adapter ==> Propriétés ==> Configurer la carte manuellement ==> Lui attribuer l'adresse IPv4 : 172.16.10.50/24 et masque réseau IPv4 : 255.255.255.0.

* L'accès d'une VM extérieure à l'interface web est possible, dans notre cas nous l'avons effectué via un Client sous Ubuntu 24.04 LTS, dont l'IPv4 suivante lui a été attribuée : 172.16.10.20/24.


### Product Bakclog

### Retours entretiens client ?

Grâce à Security Onion notre client souhaiterais pouvoir surveiller :
- Si un equipement a changé d'adresse MAC (attque dîte **ARP Spoofing**)
- Si un equipement n'est plus connecté au réseau
- Si un equipement subis ou a subis une attaque par dictionnaire.

## Améliorations possibles : suggestions d’améliorations futures
