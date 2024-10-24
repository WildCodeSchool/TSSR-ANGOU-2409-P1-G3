
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
Utiliser l'adresse IP suivante ==> 
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

Un nom d'hÔte utilisateur et un mot de passe vous sont demandés :

![HOST_LOGIN.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/HOST_LOGIN.png)
![SET_PASSWORD.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/SET_PASSWORD.png)

Une fois ces premières étapes d'installation terminées, vous êtes invité à redémarrer :

![INSTALL_COMPLETE.png](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/PHOTO_ADMIN/INSTALL_COMPLETE.png)

Après le redémarrage, connectez-vous avec le nom d'utilisateur et le mot de passe établis précédemment, puis l'installation se déclenchera automatiquement :

![]()

L'installation _STANDALONE_ est à privilégier mais comme annoncé précédemment nous nous occuperons de la version _EVAL_ : 

![]()

Pour cette étape, sélectionnez le type d'installation souhaité :

![]()

Si votre VM Security Onion dispose d'un accès Internet complet, sélectionnez "Standard" (sinon, comme dans notre cas, sélectionnez Airgap) :

![]()

Pour continuer veuillez accepter les termes de la licence en tapant "agree" : 

![]()

Définissez le nom d'hôte (celui-ci n'a pas vraiment d'importance, il vous permettra toutefois d'identifier cette machine) :

![]()

Dans le cas où vous auriez laissé le nom d'hôte par défaut et que vous souhaitez tout de même l'utiliser, sélectionnez "Use anyway" (cependant, si vous décidiez de créer une nouvelle machine, elle ne pourra pas posséder ce même nom d'hôte) :

![]()

Dans cette étape, choisissez la première carte réseaux établie plus haut : 

![]()

Dans notre exemple, une adresse IPv4 statique est demandée, toutefois, si vous avez accès à un réseau fixe / personnel (ex : box Internet domicile) l'utilisation du DHCP est possible et la configuration de l'adresse IPv4 fixe sera possible plus tard :

![]()

Dans le cas où vous rentrez une adresse fixe, renseignez cette dernière (dans le cadre de notre projet, l'Ipv4 demandée est 172.16.10.10/24) :

![]()

Définissez maintenant la passerelle (dans notre cas : 172.16.10.254) :

![]()

Renseignez les serveurs DNS (ici les serveurs DNS Google classique) :

![]()

Donnez le domaine de recherche DNS (nous avons laissé le nom par défaut ) : 

![]()

Par défaut nous avons gardé le Docker IP range : 

![]()

Sélectionnez Direct : 

![]()

Rentrez une adresse mail qui sera utilisée pour la Web Interface en tant qu'Administrateur du logiciel :

![]()

Définissez le mot de passe pour ce compte : 

![]()

Confirmez le : 

![]()

Dans la statégie d'accès, choisissez IP : 

![]()
________________
### Configuration Administrateur

Pour vous connectez à l'Interface Web, rentrez l'adresse mail administrateur établie [plus haut](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/edit/main/INSTALL.md#configuration-de-liso--os) :

![]()

Le mot de passe que vous avez mis en place à cette étape + sa confirmation :

![]()
![]()
________________
### Configuration nouvel utilisateur

Accès au logiciel Security Onion :

Cliquez sur "" : 

Puis sur "" : 

Rentrez les informations pour un nouvel utilisateur : 


_____________________________________________________________________________________________________________________________________________________________________________
## FAQ : solutions aux problèmes connues et communs liés à l'installation et à la configuration

Comment dois-je configurer les paramètres réseaux de ma VM ?

Les paramètres réseaux si machine hôte ?

Les paramètres réseaux si VM Client ?

Comment me connecter en tant qu'administrateur  ?

Comment gérer les utilisateurs non administrateur ?

Comment vérifier les clés ISO ?

Quelle version de Security Onion dois-je utiliser ?


