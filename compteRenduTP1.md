# **Exercice 2:** Prise en main de l'interprétateur de commande

## Manuel

### 1) Identifier le rôle de which

Après avoir tapé la commande:

  man which

  On se rend compte que la commande **which** permet de localiser une commande ou un binaire.

### 2) Quand on consulte cette page, comment peut-on rechercher, par exemple, le mot option? 

  man which

Puis la commande:

  /option

### 3) Comment quitte-t-on le manuel ? 

  q

### 4) Chaque section du manuel a une première page, qui présente le contenu de la section. Aﬀicher la première page de la section 6; de quoi parle cette section?

  man 6 intro

La section 6 du manuel montre tout les jeux et applications ludiques du système.

## Navigation dans l’arborescence des fichiers

### 1) Allez dans le dossier /var/log

  cd /var/log

### 2) Remontez dans le dossier parent (/var) en utilisant un chemin relatif 

  cd ..

### 3) Retournez dans le dossier personnel 

  cd ..

### 4) revenez au dossier précédent (/var) 

  cd /var

### 5) Essayez d’accéder au dossier /root; que se passe-t-il? 

  cd /root
  En tant qu'utilisateur, on ne peut pas accéder au dossier administrateur car nous n'avons pas les droits.

### 6) Essayez la commande sudo cd /root; que se passe-t-il? Expliquez  

  Nous n'avons pas les permissions : "**Permission denied**"

### 7) A partir de votre dossier personnel, créez l’arborescence suivante

  mkdir nom

  touch nom

### 8) Revenez dans votre dossier personnel; à l’aide de la commande rm, essayez de supprimer Fichier1, puis Dossier1; que se passe-t-il? 

  rm Dossier1/Fichier1

  On ne peux pas supprimer le dossier mais le fichier sera supprimé si l'on utilise un chemin relatif.

### 9) Quelle commande permet de supprimer un dossier? 

  rmdir Dossier1 </code></br>

### 10) Que se passe-t-il quand on applique cette commande à Dossier2? 

 On ne peut pas car il y a des sous dossiers et des fichiers à l'intérieur.

### 11) Comment supprimer en une seule commande Dossier2 et son contenu?

  rm -r Dossier2

## Commandes importantes

### 1) Quelle commande permet d’aﬀicher l’heure? A quoi sert la commande time? 

  date

  Elle permet d'éxecuter les programmes et determine les ressources utilisées par les commandes.

### 2) Dans votre dossier personnel, tapez successivement les commandes ls puis la; que peut-on en déduire sur les fichiers commençant par un point? 

  Les fichiers commençant par un point sont des fichiers cachés.

### 3) Où se situe le programme ls? 

  Il se situe dans le dossier usr/bin/

### 4) Que fait la commande ll? 

  Elle permet de lister les fichiers et dossiers ainsi que leurs droits.

### 5) Quelle commande permet d’aﬀicher les fichiers contenus dans le dossier /bin? 

  ls usr/bin/

### 6) Que fait la commande ls ..? 

  Elle permet de lister les fichiers et dossiers du repertoire précédant.

### 7) Quelle commande donne le chemin complet du dossier courant?

  pwd

### 8) Que fait la commande echo 'yo' > plop exécutée 2 fois?

  Cette commande permet de créer un fichier nommé plop. Puis une fois créé, il inscrit dans le fichier ce qui est écrit entre '' soit yo.

### 9) Que fait la commande echo 'yo' >> plop exécutée 2 fois? 

  Cette commande permet de créer un fichier nommé plop. Puis une fois créé, il inscrit dans le fichier ce qui est écrit entre '' soit yo. Mais si on le fait 2x alors yo sera écrit à la suite du premier yo.

### 10) A quoi sert la commande file ? Essayez la sur des fichiers de types différents.

  Elle permet de déterminer le type de fichier en dehors de son extension.

### 11) Créez un fichier toto qui contient la chaîne Hello Toto ! ; créer ensuite un lien titi vers ce fichier avec la commande ln toto titi. Modifiez à présent le contenu de toto et affichez le contenu de titi : qu’observe-t-on ? Supprimez le fichier toto ; quelle conséquence cela a-t-il sur titi ?

  Afin de créer le fichier toto qui contient la chaine "Hello Toto", il faut faire la commande:
  echo "Hello Toto !" > Toto
  Apres avoir effectué le lien, lorsque l'on modifie le contenu de Toto, le contenu de Titi aussi change par conrte si l'on supprime le dossier Toto le dossier Titi quand à lui reste inchangé.

### 12) Créez à présent un lien symbolique tutu sur titi avec la commande ln -s titi tutu. Modifiez le contenu de titi ; quelle conséquence pour tutu ? Et inversement ? Supprimez le fichier titi ; quelle conséquence cela a-t-il sur tutu ?

  Après avoir créer un lien symbolique entre Titi et tutu, lorsque l'on modifie le contenu de titi, le contenu de tutu y est également changé de la même façon. De plus lorsque titi est supprimé, alors tout le contenu de tutu est supprimé également.

### 13) Affichez à l’écran le fichier /var/log/syslog. Quels raccourcis clavier permettent d’interrompre et reprendre le défilement à l’écran ?

  Les raccourcis clavier permettant de stoper le defilement puis de reprendre sont:
  **Ctrl + s** Pour stopper le défilement
  **Ctrl + q** Pour reprendre le defilement

### 14) Affichez les 5 premières lignes du fichier /var/log/syslog, puis les 15 dernières, puis seulement les lignes 10 à 20.

  Pour afficher les 5 premières lignes du fichier :
  head -5 /var/log/syslog

  Puis les 15 dernières:
  tail -15 /var/log/syslog

  Enfin les lignes 10 à 20 :
  head -n 10 /var/log/syslog | tail -n 20

### 15) Que fait la commande dmesg | less ?

  La commande dmesg | less permet de voir la mémorie tampon utilisé par le noyau pour les messages (Page par page).

### 16) Affichez à l’écran le fichier /etc/passwd ; que contient-il ? Quelle commande permet d’afficher la page de manuel de ce fichier ?

  Le fichier /etc/passwd contient tout ce qui concernent les utilisateurs (par ex: login, mot de passe...).
  La commande qui permet d'afficher la page de manuel de ce fichier est: man passwd

### 17) Affichez seulement la première colonne triée par ordre alphabétique inverse

  Afin d'afficher la première colonne triée apr ordre alphabetique inverse, il faut tapper:
  sort +0 -r /etc/passwd

### 18) Quelle commande nous donne le nombre d’utilisateurs ?

  Pour voir le nombre d'utilisateurs il faut tapper la commande:
  wc -l /etc/passwd

### 19) Combien de pages de manuel comportent le mot-clé conversion dans leur description ?

  Après avoir tappé la commande: 
  man -k conversion 
  on voit que le mot-clé conversion apparait dans 4 pages de manuel.

### 20) A l’aide de la commande find, recherchez tous les fichiers se nommant passwd présents sur la machine

  Pour celà, il suffit de tapper la commande: 
  find / -name passwd

### 21) Modifiez la commande précédente pour que la liste des fichiers trouvés soit enregistrée dans le fichier ~/list_passwd_files.txt et que les erreurs soient redirigées vers le fichier spécial /dev/null

  Il faut pour cela tapper la commande:
  find / -name passwd > ~/list_passwd_files.txt 2>> /dev/null

### 22) Dans votre dossier personnel, utilisez la commande grep pour chercher où est défini l’alias ll vu précédemment

  Apres avoir tappé la commande: 
  grep ll
  on sait que l'alias ll est defini dans les options de grep. (Marqué grep[Option])

### 23) Utilisez la commande locate pour trouver le fichier history.log

  Après avoir tapper la commande: 
  locate history.log
  Le fichier history.log apparait selon le chemin suivant: /var/log/apt/history.log

### 24) Créer un fichier dans votre dossier personnel puis utilisez locate pour le trouver. Apparaît-il ? Pourquoi ?

  Une fois le dossier créer, lorsque l'on essaye de le localiser il n'apparait pas.

