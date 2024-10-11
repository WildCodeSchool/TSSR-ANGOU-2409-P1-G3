# Documentation Utilisateur

## Utilisation de base : Comment utiliser les fonctionnalités clés

Flux de travail : 
- Alertes et examinez les alertes non reconnues 
- Consultez le tableau de bord
  
 ![Dashboard _ SecurityOnion](https://docs.securityonion.net/en/2.4/_images/53_dashboards.png)
  
- Passer à Hunt, interface qui cible plus précisemmment les requêtes en regroupant plusieurs champs du Tableau de bord, etudiez et étendre votre recherche, les journaux supplémentaires relatifs aux adresses IP source et de destination.
- Si l'une de ces alertes, vous semble intéressant passer PCAP ( packet capture ) interface de programmation permettant de capturer un trafic réseau pour examiner.
- En fonction de vos recherches, envoyez a CyberChef pour une analyse et un decodage plus approfondie.
- Transférez les alertes et les journaux vers les dossiers. Passez à Hunt pour élargir votre champ d'action.
- Si vous avez déployé ElasticAgent, rechercher des journaux d'hôte supplémentaires ou exécuter des requêtes à l'aide d'osquery.
- Enfin, revenez aux dossiers et documentez l’intégralité de l’enquête et fermez le dossier.

## Utilisation avancée : comment utiliser au mieux les options

Sécurity Onion, permet la sauvegarde quotidienne de certains fichiers afin de pouvoir récupérer ces derniers en cas de panne. Une sauvegarde quotidienne est disponible _/nsm/backup/_ 

![](https://docs.securityonion.net/en/2.4/_images/config-item-backup.png)

ainsi une duplication de sauvegarde est possible vers un emplacement extérieur. Cependant les données ElasticSearch ne sont pas sauvegardeés automatiquement.


FAQ : solutions aux problèmes connus et communs liés à l'utilisation
