# Documentation administrateur

## Prérequis techniques

- [ Téléchargement de Security Onion Desktop ISO](https://github.com/Security-Onion-Solutions/securityonion/raw/2.4/main/sigs/securityonion-2.4.110-20241004.iso.sig)

![CARACTERISTIQUES_TECHNIQUES_NECESSAIRES.PNG](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/Images%20doc/CARACTERISTIQUES_TECHNIQUES_NECESSAIRES.png)

La liste complète des prérequis techniques peut être trouvée [ici](https://docs.securityonion.net/en/2.4/hardware.html).

## Etapes d'installation et de configuration : 
> Instruction étape par étape

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




**Windows :**

Dans un premier temps, téléchargez l'ISO [ici](https://download.securityonion.net/file/securityonion/securityonion-2.4.110-20241004.iso).

Une fois téléchargé, installez [HashCheckSetup-v2.4.0](https://www.softpedia.com/get/System/OS-Enhancements/HashCheck-Shell-Extension.shtml). Ce logiciel va permettre de vérifier les hachages de l'ISO securityonion et vous permettre de contrôler l'image ISO téléchargée en la comparant aux valeurs indiquées sur ce [lien](https://github.com/Security-Onion-Solutions/securityonion/blob/d5df002f980ab1e4a442d410fd56ec976cdd9768/DOWNLOAD_AND_VERIFY_ISO.md).

Pour se faire : clic droit sur l'image ISO, sélectionnez "Propriétés", vous devriez arriver sur cet écran : 
![PROPRIETES_ISO.PNG](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/Images%20doc/PROPRIETES_ISO.png)

Une fois cette étape réalisée, cliquez sur "Hashages. Un chargement se lance (allant de quelques dizaines de secondes à quelques minutes selon la puissance de votre machine). Une fois le chargement terminé, vous êtes en mesure d'observer les clés à comparer :
![FIN_CHARGEMENT_HASHAGES](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/Images%20doc/FIN_CHARGEMENT_HASHAGES.png)

Dans ce cas précis, les clés correspondent.

### Configuration de la VM

Depuis le logiciel VirtualBox créer une nouvelle VM :

![NOUVELLE_VM.PNG](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/Images%20doc/NOUVELLE_VM.PNG)

Renseigner le nom de la VM. Celui-ci n'a pas d'importance, il vous permettra seulement de l'identifier parmi vos autres VM : 

![RENSEIGNER_NOM_VM.PNG](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/Images%20doc/RENSEIGNER_NOM_VM.PNG)

Sélectionner l'ISO de security onion précédemment téléchargée : 

![SELECTIONNER_ISO.PNG](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/Images%20doc/SELECTIONNER_ISO.PNG)

Définir la quantité de RAM et le nombre de Cɶurs (d'après les prérequis techniques mentionnés plus haut) : 

![RAM_COEURS.PNG](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/Images%20doc/RAM_COEURS.PNG)

Définir l'espace disque requis pour le bon fonctionnement de la VM : 

![ESPACE_DISQUE.PNG](https://github.com/WildCodeSchool/TSSR-ANGOU-2409-P1-G3/blob/main/Images%20doc/ESPACE_DISQUE.PNG)

Votre VM est prête.

### Configuration de l'ISO / OS

### Configuration Réseau de l'OS
configuration réseau de la VM  ?

## Installation du logiciel Security Onion

### Configuration Administrateur

### Configuration nouvel utilisateur

## FAQ : solutions aux problèmes connues et communs liés à l'installation et à la configuration
