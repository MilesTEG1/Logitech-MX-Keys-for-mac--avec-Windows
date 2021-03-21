Faire fonctionner le clavier Logitech MX Keys for Mac sous Windows (10) <!-- omit in toc -->
============

L'objectif de ce qui suit est de faire fonctionner le clavier Logitech MX Keys for Mac sous Windows (10), car de base vous n'aurez que la disposition AZERTY FR PC classique, donc pas ce qui est sérigraphié sur le clavier.

Je vais m'appuyer sur un autre tuto que j'ai réalisé pour avoir les majuscules accentuées avec la touche Verrouillage Majuscule (comme sur les vrais MAC) : [ce tuto est disponible ici](https://github.com/MilesTEG1/Majuscules_Accentuees_clavier_Windows).
Je ne détaillerais donc pas l'utilisation du logiciel MS Keyboard Layout Creator qui m'a servi à récupérer la disposition clavier installée par les pilotes Apple BootCamp pour l'utilisation d'un clavier Apple Filaire.

## Table of Contents <!-- omit in toc -->

- [1. Introduction](#1-introduction)
- [2. Méthode à suivre](#2-méthode-à-suivre)
  - [2.1. SharpKeys](#21-sharpkeys)
  - [2.2. Layout de clavier Apple FR AZERTY](#22-layout-de-clavier-apple-fr-azerty)
    - [2.2.1 Installer le pilote clavier avec BootCamp (long)](#221-installer-le-pilote-clavier-avec-bootcamp-long)
    - [2.2.2 Utiliser un layout Apple FR AZERTY (original ou modifié)](#222-utiliser-un-layout-apple-fr-azerty-original-ou-modifié)
  - [2.3. Utilisation de SharpKeys pour modifier certaines affectations de touches](#23-utilisation-de-sharpkeys-pour-modifier-certaines-affectations-de-touches)
  - [3. Fin](#3-fin)

# 1. Introduction

<img src="https://raw.githubusercontent.com/MilesTEG1/Logitech-MX-Keys-for-mac--avec-Windows/main/Screenshots/touche-non-affectée.JPEG" align="right" height="350" />
<img src="https://raw.githubusercontent.com/MilesTEG1/Logitech-MX-Keys-for-mac--avec-Windows/main/Screenshots/touches-interverties.png" align="right" height="350" />
<br/><br/><br/>
Je ne sais toujours pas pourquoi avec le MX Keys for mac sous windows j'ai deux touches qui sont interverties...

J'ai aussi constaté que la touche **=** située au-dessus du pavé numérique ne fonctionnait pas.
<br/><br/><br/>
Ce tuto va remettre tout ça en place.
<br/><br/><br/><br/><br/>
<br/>

# 2. Méthode à suivre

## 2.1. SharpKeys

Il faudra télécharger et installer le logiciel SharpKeys : https://github.com/randyrants/sharpkeys/ 

C'est le logiciels le plus simple qui fonctionne parfaitement. J'ai voulu essayer avec les nouveaux [Microsoft PowerToys](https://github.com/microsoft/PowerToys) et plus précisément le Keyboard Manager, mais ce dernier ne fonctionne que quand la session est lancée... SharpKeys fonctionne même si la session n'est pas encore lancée car il modifie la base de registre.

Si vous avez une alternative fonctionnelle, n'hésitez pas à la proposer.

## 2.2. Layout de clavier Apple FR AZERTY

Comme il s'agit d'un clavier "for Mac", il faudra également installer un layout Apple FR AZERTY.
Il y a plusieurs méthodes pour y parvenir.

### 2.2.1 Installer le pilote clavier avec BootCamp (long)

Partir de zéro en installant les pilotes du clavier Apple avec BootCamp, c'est un peu long, car faut télécharger bootcamp... <br/>
Je ne vais pas trop détailler mais voilà succinctement les étapes :
- Récupérer `Brigadier` : https://github.com/timsutton/brigadier <br/> J'ai cloné le dépôt pour avoir le fichier `brigadier.ps1` et ses potentielles dépendances (pas sur ce que ce soit utile, peut-être que seul le fichier suffit...). [Ne pas utiliser/téléchager l'exécutable]

- Ouvrir le dossier dans un PowerShell et lancer le script `brigadier.ps1` : <br/>
![](https://raw.githubusercontent.com/MilesTEG1/Logitech-MX-Keys-for-mac--avec-Windows/main/Screenshots/01.png)
![](https://raw.githubusercontent.com/MilesTEG1/Logitech-MX-Keys-for-mac--avec-Windows/main/Screenshots/02.png)

- Une fois la procédure terminée, il y aura un dossier `BootCamp-xxx-xxxxxxx` dans lequel se trouveront plein de pilotes prévus pour le modèle utilisé lors du lancement de la commande. Dans mon cas, j'ai choisi un MBA de 2015, modèle `MacBookAir7,2`, vous pouvez en choisir un autre si vous le souhaitez...<br/>
![](https://raw.githubusercontent.com/MilesTEG1/Logitech-MX-Keys-for-mac--avec-Windows/main/Screenshots/03.png)
- Il faut copier dans un nouveau dossier uniquement les deux fichiers suivants :<br/>
![](https://raw.githubusercontent.com/MilesTEG1/Logitech-MX-Keys-for-mac--avec-Windows/main/Screenshots/04.png)<br/>
Car il faut installer avec BootCamp.msi, sinon le layout du clavier n'est pas installé. Et si tous les autres .exe sont dans dossier au moment où vous lancer le .msi, ils seront aussi installés, ce qui ne nous intéresse pas du tout ici.
- Il faudra passer sur un message d'erreur potentiel, et poursuivre l'installation et redémarrer l'ordinateur.
- Ensuite il faudra suivre la procédure du [§2.4 du tuto des lettres majuscules accentuées](https://github.com/MilesTEG1/Majuscules_Accentuees_clavier_Windows#24-installation-du-layout-du-clavier-personnalis%C3%A9).


### 2.2.2 Utiliser un layout Apple FR AZERTY (original ou modifié)

Le plus simple/rapide est de prendre [un des layouts sur ce dépôt](https://github.com/MilesTEG1/Logitech-MX-Keys-for-mac--avec-Windows/tree/main/Keyboard%20Layout) ou celui de [mon tuto des lettres majuscules accentuées](https://github.com/MilesTEG1/Majuscules_Accentuees_clavier_Windows).

Il y a deux versions :

- Une version originale, c'est-à-dire non modifiée, c'est celle que vous obtiendrez avec le [§2.2.1 précédent](#221-installer-le-pilote-clavier-avec-bootcamp-long).

- Une version modifiée pour avoir les lettres majuscules accentuées avec la touche verrouillage majuscule : [voir mon autre tuto](https://github.com/MilesTEG1/Majuscules_Accentuees_clavier_Windows) que je vous invite à lire quand-même :).

## 2.3. Utilisation de SharpKeys pour modifier certaines affectations de touches

Vu que certaines touches sont inversées malgré l'utilisation du layout Apple_FR AZERTY, il faut les remapper avec SharpKeys.

J'ai mis dans le dossier [SharpKeys-Scripts](https://github.com/MilesTEG1/Logitech-MX-Keys-for-mac--avec-Windows/tree/main/SharpKeys-Scripts) le fichier que vous pouvez charger dans SharpKeys et qui vous donnera ceci :<br/>
![](https://raw.githubusercontent.com/MilesTEG1/Logitech-MX-Keys-for-mac--avec-Windows/main/Screenshots/SharpKeys-1.png)

Pour arriver à ce résultat, suivre ce qui suit :

- Cliquer sur le bouton "**Add**" ;

- Puis dans la fenêtre qui s'ouvre, cliquer sur le bouton "**Type Key**" de la partie de gauche *Map this key* :<br/>
![](https://raw.githubusercontent.com/MilesTEG1/Logitech-MX-Keys-for-mac--avec-Windows/main/Screenshots/SharpKeys-2.png)<br/>

- Il faudra alors appuyer sur la touche du clavier que vous voulez remapper :<br/>
![](https://raw.githubusercontent.com/MilesTEG1/Logitech-MX-Keys-for-mac--avec-Windows/main/Screenshots/SharpKeys-3.png)<br/>

- Puis refaire la manipulation précédente pour la partie de gauche *To this key* :<br/>
![](https://raw.githubusercontent.com/MilesTEG1/Logitech-MX-Keys-for-mac--avec-Windows/main/Screenshots/SharpKeys-4.png)<br/>

- Pour la touche = du pavé numérique, je l'ai réaffectée à la touche = se trouvant à gauche de la touche MAJ de droite, en suivant la procédure précédente.

- Sauvegarder vos réaffectations de touche avec le bouton "**Save keys...**" de la fenêtre principale.

- Enfin, cliquer sur le bouton "**Write to Registry**" pour sauvegarder dans la base de registre les modifications souhaitées puis redémarrer l'ordinateur (une déconnexion/reconnexion peut éventuellement suffire).

## 3. Fin

Voilà, vous pouvez maintenant utiliser votre clavier Logitech MX Keys for Mac avec windows (10) comme si vous étiez sur un vrai MAC.
Ce qui est encore plus vrai si vous avez opté pour le layout modifié pour avoir la possibilité de faire les lettres ``É È À Ç Ù``  avec la touche **``CAPS-LOCK``** sous windows, comme sur un vrai mac.

Bonne utilisation de ce super clavier :)