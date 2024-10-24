
<div align="center"><h1>Documentation Administrateur</h1></div>

## Prérequis techniques

- [ Téléchargement de Security Onion Desktop ISO](https://github.com/Security-Onion-Solutions/securityonion/raw/2.4/main/sigs/securityonion-2.4.110-20241004.iso.sig)

Dans le cas d'une utilisation _STANDALONE_, il vous faut allouer :
* 4 cɶurs
* 16 Gb RAM
* 200 Gb de stockage (SSD préférable, mais un HDD conviendra)

Dans notre situation, utilisation d'une version _EVAL_ :
* 4 cɶurs
* 8 Gb RAM
* 200 Gb de stockage

La liste complète des prérequis techniques en fonction du type d'installation peut être trouvée [ici](https://docs.securityonion.net/en/2.4/hardware.html).
_____________________________________________________________________________________________________________________________________________________________________________
## Etapes d'installation et de configuration : 
> Instruction étape par étape

________________
### Vérification de l'intégrité de l'ISO

**Linux :** 

Téléchargement et importation de la clé de signature avec le gestionnaire de signature **GPG**
```bash
wget https://raw.githubusercontent.com/Security-Onion-Solutions/securityonion/2.4/main/KEYS -O - | gpg --import -  
```
Téléchargement du fichier de signature :
```bash
wget https://github.com/Security-Onion-Solutions/securityonion/raw/2.4/main/sigs/securityonion-2.4.110-20241004.iso.sig
```
Vérification du fichier ISO avec **GPG** :
```bash
gpg --verify securityonion-2.4.110-20241004.iso.sig securityonion-2.4.110-20241004.iso
```
Si l'image signature et l'ISO correspondent, le résultat de la commande **GPG** devrait afficher "**Good signature**" dans le terminal
```bash
gpg: Signature made Sat 05 Oct 2024 03:31:57 PM CEST
gpg:                using RSA key C804A93D36BE0C733EA196447C1060B7FE507013
gpg: Good signature from "Security Onion Solutions, LLC <info@securityonionsolutions.com>" [unknown]
gpg: WARNING: This key is not certified with a trusted signature!
gpg:          There is no indication that the signature belongs to the owner.
```
L'emprunte de la clé primaire doit correspondre à :
```bash
Primary key fingerprint: C804 A93D 36BE 0C73 3EA1  9644 7C10 60B7 FE50 7013
```
________________
**Windows :**

Dans un premier temps, téléchargez l'ISO [ici](https://download.securityonion.net/file/securityonion/securityonion-2.4.110-20241004.iso).

Une fois téléchargé, installez [HashCheckSetup-v2.4.0](https://www.softpedia.com/get/System/OS-Enhancements/HashCheck-Shell-Extension.shtml). Ce logiciel va permettre de vérifier les hachages de l'ISO securityonion et vous permettre de contrôler l'image ISO téléchargée en la comparant aux valeurs indiquées sur ce [lien](https://github.com/Security-Onion-Solutions/securityonion/blob/d5df002f980ab1e4a442d410fd56ec976cdd9768/DOWNLOAD_AND_VERIFY_ISO.md) Github.

Pour se faire : clic droit sur l'image ISO, sélectionnez "Propriétés", vous devriez arriver sur cet écran : 

![PROPRIETES_ISO.PNG](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/Images%20doc/PROPRIETES_ISO.png)

Une fois cette étape réalisée, cliquez sur "Hashages". Un chargement se lance (allant de quelques dizaines de secondes à quelques minutes selon la puissance de votre machine). Une fois le chargement terminé, vous êtes en mesure d'observer les clés à comparer :

![FIN_CHARGEMENT_HASHAGES](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/Images%20doc/FIN_CHARGEMENT_HASHAGES.png)

Dans ce cas précis, les clés correspondent.
________________
### Configuration de la VM

Depuis le logiciel VirtualBox créer une nouvelle VM :

![NOUVELLE_VM.PNG](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/Images%20doc/NOUVELLE_VM.PNG)

Renseigner le nom de la VM. Celui-ci n'a pas d'importance, il vous permettra seulement de l'identifier parmi vos autres VM : 

![RENSEIGNER_NOM_VM.PNG](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/Images%20doc/RENSEIGNER_NOM_VM.PNG)

Sélectionner l'ISO de security onion précédemment téléchargée : 

![SELECTIONNER_ISO.PNG](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/Images%20doc/SELECTIONNER_ISO.PNG)

Définir la quantité de RAM et le nombre de Cɶurs (d'après les prérequis techniques mentionnés plus haut, dans cet exemple la configuration correspond à la version EVAL) : 

![RAM_COEURS.PNG](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/Images%20doc/RAM_COEURS.PNG)

Définir l'espace disque requis pour le bon fonctionnement de la VM : 

![ESPACE_DISQUE.PNG](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/Images%20doc/ESPACE_DISQUE.PNG)

Votre VM est prête.
________________
**Configuration des paramètres réseaux de la VM**

Pour l'installation du serveur Security Onion, la mise en place de deux cartes réseaux est nécessaire (les paramètres qui vont être sélectionnés correspondent à une installation sur un réseau local).

Cliquer sur la VM dont il est question, une fois fait allez dans la partie "Configuration" :

![ONGLET_CONFIGURATION.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/ONGLET_CONFIGURATION.PNG).

Passez en configuration "Expert" :

![ONGLET_EXPERT.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/ONGLET_EXPERT.PNG).

Accédez à la rubrique "Réseau" :

![ONGLET_RESEAU.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/ONGLET_RESEAU.PNG).

Dans l'adapater 1 :
  - Cochez "Activer l'interface réseau"
  - Choisissez le Mode d'accès réseau "Accès par pont"

![ONGLET_CARTE_1.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/ONGLET_CARTE_1.PNG).
![COCHER_ACTIVER_1.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/COCHER_ACTIVER_1.PNG)
![MODE_RESEAU_BRIDGED.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/MODE_RESEAU_BRIDGED.PNG).

Dans l'adapter 2 :
- Cochez également "Activer l'interface réseau"
- Choisissez le Mode d'accès "Réseau interne"

![ONGLET_CARTE_2.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/ONGLET_CARTE_2.PNG).
![COCHER_ACTIVER_2.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/COCHER_ACTIVER_2.PNG).
![MODE_RESEAU_INTERNE.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/MODE_RESEAU_INTERNE.PNG)

Avant de poursuivre dans cette partie, enchaînez avec la suivante : [Configuration de l'ISO / OS](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/INSTALL.md#configuration-de-liso--os)

Une fois l'initialisation du serveur terminée, vous allez devoir modifier ces paramètres réseaux pour permettre la communication de votre machine hôte et/ou d'une VM cliente avec votre serveur.

Pour se faire :

La machine hôte est l'ordinateur de la personne qui lance le serveur sur son virtualbox : 
Ouvrir les paramètres Réseau et Internet de l'ordinateur ==> 
Paramètres réseau avancés ==> 
Clic gauche la carte réseau VirtualBox Host-Only Ethernet Adapter ==> 
Modifier ==> 
Double Clic sur Protocole Internet version 4 (TCP/IPv4) ==> 
Entrer l'adresse IP : 172.16.10.40 et masque de sous-réseau : 255.255.255.0 ==> 
OK.

Configuration de la carte Virtualbox depuis Fichiers ==> 
Outils ==> 
Network Manager ==> 
Clic gauche sur la carte : VirtualBox Host-Only Ethernet Adapter ==> 
Propriétés ==> 
Configurer la carte manuellement ==> 
Lui attribuer l'adresse IPv4 : 172.16.10.50/24 et masque réseau IPv4 : 255.255.255.0.




________________
### Configuration de l'ISO / OS

Le DHCP à partir d'un réseau fixe fonctionne, mais dans notre cas (réseau CCI Angoulême / partage de connexion mobile), le choix du DHCP n'est pas pertinent. 

Une fois la VM lancée à partir de l'image ISO de Security Onion, le menu de démarrage apparaît :

![MENU_DEMARRAGE.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/MENU_DEMARRAGE.png)

Tapez "yes" pour continuer l'installation :

![YES_TO_PROCEED.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/YES_TO_PROCEED.png)

Un nom d'hôte utilisateur et un mot de passe vous sont demandés :

![HOST_LOGIN.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/HOST_LOGIN.png)
![SET_PASSWORD.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/SET_PASSWORD.png)

Une fois ces premières étapes d'installation terminées, vous êtes invité à redémarrer :

![INSTALL_COMPLETE.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/INSTALL_COMPLETE.png)

Après le redémarrage, connectez-vous avec le nom d'utilisateur et le mot de passe établis précédemment, puis l'installation se déclenchera automatiquement :

![YES_CONTINUE.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/YES_CONTINUE.png)

Pour cette étape, sélectionnez le type d'installation souhaité :
> L'installation _STANDALONE_ est à privilégier mais comme annoncé précédemment nous nous occuperons de la version _EVAL_.

![TYPE_INSTALL.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/TYPE_INSTALL.png)

Si votre VM Security Onion dispose d'un accès Internet complet, sélectionnez "Standard" (sinon, comme dans notre cas, sélectionnez Airgap) :

![AIRGAP.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/AIRGAP.png)

Pour continuer veuillez accepter les termes de la licence en tapant "agree" : 

![AGREE.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/AGREE.png)

Définissez le nom d'hôte (celui-ci n'a pas vraiment d'importance, il vous permettra toutefois d'identifier cette machine) :

![NOM_HOTE.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/NOM_HOTE.png)

Dans le cas où vous auriez laissé le nom d'hôte par défaut et que vous souhaitez tout de même l'utiliser, sélectionnez "Use anyway" (cependant, si vous décidiez de créer une nouvelle machine, elle ne pourra pas posséder ce même nom d'hôte) :

![USE_ANYWAY.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/USE_ANYWAY.png)

Dans cette étape, choisissez la première carte réseau établie plus haut : 

![CARTE_RESEAU_1](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/CARTE_RESEAU_1.png)

Dans notre exemple, une adresse IPv4 statique est demandée, toutefois, si vous avez accès à un réseau fixe / personnel (ex : box Internet domicile) l'utilisation du DHCP est possible et la configuration de l'adresse IPv4 fixe sera possible plus tard :

![IPv4_STATIC.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/IPv4_STATIC.png)

Dans le cas où vous rentrez une adresse fixe, renseignez cette dernière (dans le cadre de notre projet, l'Ipv4 demandée est 172.16.10.10/24) :

![IPv4_SET.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/IPv4_SET.png)

Définissez maintenant la passerelle (dans notre cas : 172.16.10.254) :

![PASSERELLE_IPv4.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/PASSERELLE_IPv4.png)

Renseignez les serveurs DNS (ici les serveurs DNS Google classique) :

![DNS.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/DNS.png)

Donnez le domaine de recherche DNS (nous avons laissé le nom par défaut ) : 

![DNS_SEARCH_DOMAIN.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/DNS_SEARCH_DOMAIN.png)

Par défaut nous avons gardé le Docker IP range : 

![DOCKER_IP.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/DOCKER_IP.png)

Sélectionnez Direct : 

![DIRECT.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/DIRECT.png)

Rentrez une adresse mail qui sera utilisée pour la Web Interface en tant qu'Administrateur du logiciel :

![MAIL_ADMIN.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/MAIL_ADMIN.png)

Définissez le mot de passe pour ce compte : 

![PASSWORD_ADMIN.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/PASSWORD_ADMIN.png)

Confirmez le : 

![CONFIRM_PASSWORD_ADMIN.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/CONFIRM_PASSWORD_ADMIN.png)

Dans la statégie d'accès, choisissez IP : 

![SELECTION_ACCES_WEB_INTERFACE.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/SELECTION_ACCES_WEB_INTERFACE.png)

Autorisez l'accès en sélectionnant "yes" :

![ALLOW_ACCESS.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/ALLOW_ACCESS.png)

Donnez une IP unique ou une range à autoriser via le pare-feu basé sur l'hôte :

![IP_RANGE.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/IP_RANGE.png)

Confirmez les informations renseignées dans le récap :

![RECAP_CONFIG.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/RECAP_CONFIG.png)

Une fenêtre de fin d'installation s'ouvre :

![]()

L'installation est terminée ! [Vous pouvez retourner à la rubrique précédente pour la modification des paramètres des cartes réseau](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/INSTALL.md#configuration-de-la-vm).

________________
### Connexion web interface Administrateur

Pour accéder à l'interface, rentrez l'adresse ip de votre serveur dans un moteur de recherche :

![IP_WEB_BROWSER.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/IP_WEB_BROWSER.png)

Pour vous connectez à l'Interface Web, rentrez l'adresse mail administrateur établie et le mot de passe [plus haut](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/edit/main/INSTALL.md#configuration-de-liso--os) :

![FENETRE_CONNEXION.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/FENETRE_CONNEXION.png)

En renseignant les bons identifiants, vous arriverez sur cette page :

![CONNEXION_REUSSIE.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/CONNEXION_REUSSIE.png)

Vous êtes connecté à l'interface Web !
________________
### Configuration nouvel utilisateur sur la web interface

Depuis l'interface web, en tant qu'administrateur, il vous est possible de créer de nouveaux utilisateurs. Pour se faire, cliquez sur la rubrique "Administration"

![ONGLET_ADMINISTRATION.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/ONGLET_ADMINISTRATION.png)

Cliquez sur "USERS" : 

![ONGLET_USERS.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/ONGLET_USERS.png)

Puis sur le "+" : 

![ONGLET_USERS_+.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/ONGLET_USERS_%2B.PNG)

Rentrez les informations pour un nouvel utilisateur : 

![INFORMATIONS_UTILISATEUR.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/INFORMATIONS_UTILISATEUR.png)

Vous pouvez sélectionner le type d'utilisateur : 

![SELECTION_TYPE_UTILISATEUR.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/SELECTION_TYPE_UTILISATEUR.png)

Et voilà ! Vous avez créée un nouvel utilisateur.
_____________________________________________________________________________________________________________________________________________________________________________
## FAQ : solutions aux problèmes connues et communs liés à l'installation et à la configuration

Comment dois-je configurer les paramètres réseaux de ma VM ?

Les paramètres réseaux si machine hôte ?

Les paramètres réseaux si VM Client ?

Comment me connecter en tant qu'administrateur  ?

Comment gérer les utilisateurs non administrateur ?

Comment vérifier les clés ISO ?

Quelle version de Security Onion dois-je utiliser ?


