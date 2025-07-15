---
authors:
  - thomas
categories:
  - Linux
date:
  created: 2024-01-12
---

# Premier pas dans un environnement Linux

## Découverte de l'OS Ubuntu

Les ressources sont nombreuses sur l'histoire de Linux. Le web regorge également d'infos sur l'OS **Ubuntu**. Nous ne referons pas l'histoire ici car ce n'est pas le propos.

Cet article a servi de support de formation pour la découverte d'Ubuntu et ses grands principes : l'arborescence et l'**usage de la ligne de commande** pour se familiariser avec l'environnement.

<!-- more -->

Pour compléter votre documentation => [le Wiki francophone - Ubuntu.fr](https://doc.ubuntu-fr.org/accueil)
Une autre source utilisée et sympa [Source linuxtricks.fr](https://www.linuxtricks.fr/wiki/arborescence-du-systeme-linux)

Bien sûr nous garderons en vue une finalité d'usage(s) **géomatique !**

### Arborescence type (valable pour tous les OS Linux)

[Info](https://www.linuxtricks.fr/wiki/arborescence-du-systeme-linux){.btn .btn-info}

[g-button button-url="https://www.linuxtricks.fr/wiki/arborescence-du-systeme-linux" button_type="info" button_label="Info"][/g-button]

[Source linuxtricks.fr](https://www.linuxtricks.fr/wiki/arborescence-du-systeme-linux)

- **/** => Racine, elle contient les répertoires principaux
- **/bin** => Exécutables essentiels au système, utilisables par tous les utilisateurs (ls pwd cp)
- **/boot** => fichiers permettant à Linux de démarrer
- **/dev** => Point d'entrée de tous les périphériques (disque dur, écran, partition, consoles TTY)
- **/etc** => contient les commandes et fichiers nécessaires à l'administrateur système (XXX.conf, passwd, inittab, runlevels)
- **/home** => Répertoire personnel des utilisateurs
- **/lib** => contient les bibliothèques partagées essentielles au système lors du démarrage
- **/lib64** => idem /lib mais pour les 64bits (parfois, on trouvera lib et lib32. Dans ce cas, lib = 64bits et lib32 = 32bits)
- **/mnt** **/media** => contient les point de montage des partitions temporaires (clés USB, partitions de données) , peut s'appeler aussi /media
- **/opt** => Répertoire générique pour l'installation de programmes compilés par l'administrateur (logiciels spécifiques non présents dans les dépôts)
- **/proc** => n'existe pas physiquement sur un disque, elle est créée par le noyau dans la mémoire. Cette partition permet de donner des informations sur le système.
- **/root** => Répertoire personnel de l'administrateur (le répertoire de root n'est pas dans /home, car bien souvent le /home est sur une partition à part. En cas d'échec de montage de /home, root à quand même accès à son répertoire personnel).
- **/sbin** => Contient les programmes système essentiels utilisables par l'admin uniquement.
- **/srv** => N'est pas présent dans toutes les distributions. C'est un répertoire de données pour divers services (stockage des documents de comptes FTP, ou pages de sites web)
- **/tmp** => Répertoire fichier temporaires
- **/usr** => Contient des programmes installés (/usr/bin) avec leur librairies (/usr/lib ou /usr/lib64) tels que firefox, libreoffice, ... quelques programmes réservés à l'admin système (/usr/sbin) et les fichiers de code source (/usr/src)
- **/var** => contient les données variables (fichiers de log) mais parfois les bases de données (/var/lib/mysql) et les pages de site web (/var/www/html)

En bonne pratique, on va pouvoir créer à la racine un dossier **"/data"** pour y stocker les tablespaces de nos bases PostgreSQL/GIS, nos fichiers geopackage ou shapefiles. L'emplacement à la racine des données permet d'optimiser l'accés et de bien s'organiser en vu aussi de pouvoir simplement les déplacer.

## Commandes courantes

**sudo** => passer une commande en super utilisateur

**sudo su** => passer en utilisateur super user

**```~$ _commande_ --help```** => l'aide usuelle de chaque outil / programme qui décrit l'usage et les options de "commande"

**mkdir** => création d'un dossier (make directory)

```~$ mkdir /data```=> création du dossier "data" à la racine "/"
