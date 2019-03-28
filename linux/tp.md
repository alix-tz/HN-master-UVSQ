# Introduction à Linux - TP

---
## Prompt

1. Connectez-vous sur le site qui émule un environnement Linux en ligne de commande :  
https://bellard.org/jslinux/vm.html?cpu=riscv64&url=https://bellard.org/jslinux/buildroot-riscv64.cfg&mem=256  
**Attention : ne rafraichissez pas la page durant le TP !**  

>  Quelle invite de commande s'affiche ?  
> .  
> .  
> .  

--- 
## Explorer, naviguer

La commande `ls` permet d'afficher le contenu d'un répertoire. Par défaut, `ls` affiche le contenu du répertoire courrant. 

La commande `cd` (*change directory*) permet de se déplacer dans les répertoires. Elle est généralement suivie d'un argument exprimant le chemin à suivre pour effectuer de déplacement. Ce chemin peut être absolu ou relatif.  
Utilisée sans argument, elle nous déplace vers le dossier de l'utilisateur, symbolisé dans l'invite de commande par `~`. 

---
## Connais-toi toi-même

Tapez les commandes suivantes : 
```
whoami 
pwd
```

`whoami` permet d'afficher votre nom d'utilisateur.  

Dans cette simulation, vous êtes "root", le super-utilisateur. Vous avez donc tous les droits.  

`pwd` pour "path to working directory" affiche le chemin absolu vers le répertoire courrant.

> Comment expliquez-vous la différence entre ce qu'affiche `whoami` et ce qu'affiche `pwd` ?
> .  
> .  
> .  
> .   


---
## Sache d'où tu viens pour savoir où tu vas
Tapez les commandes suivantes : 
```
cd ..
pwd
ls
```


`.` et `..` sont utiles pour réaliser des déplacement relatifs entre le système de fichiers. 
- `.` est l'équivalent du répertoire courrant, il est souvent implicite comme dans la commande `# ls  `, qui pourrait aussi être exprimée ainsi : `# ls .` pour le même résultat.
- `..` est l'équivalent d'un "précédent" pour se déplacer vers le niveau précédent le répertoire courrant. 

On peut enchaîner plusieurs "précédents" en les séparant par `/` qui signale alors un changement de niveau dans un chemin de fichier : `../..` signifie donc "*remonter deux niveaux en arrière*". C'est strictement équivalent à `../../.`, soit "*remonter deux niveaux en arrière, depuis le répertoire courrant*".

`/`, au début d'un chemin, est aussi ce que l'on appelle "root" : la racine d'où partent tous les chemins absolus. On ne peut pas se déplacer plus "haut" que `/`.

Si vous listez le contenu de la racine (`ls /`), le dossier "root" apparaît. Vous étiez donc précédemment dans le dossier nommé "root", un niveau après la racine ("root"). 

---
## How many players

Tapez la commande suivante : 
```
cd /home
```
> Quel effet a  cette commande ?
> .  
> .  
> .  
> .    

> Listez le contenu du dossier courrant. Que contient-il ?
> .  
> .  
> .  
> .   

Tapez la commande suivante :
```
adduser utilisatrice1
```
> Après avoir tapé un mot de passe, listez à nouveau le contenu du dossier courrant. Que contient-il ?
> .  
> .  
> .  
> .    

Tapez la commande suivante :
```
adduser utilisatrice2
```
> Après avoir tapé un nouveau mot de passe, listez à nouveau le contenu du dossier courrant. Que contient-il ?
> .  
> .  
> .  
> .   

La commande `adduser` permet de créer de nouveaux comptes utilisateurs sur la machine. Ils sont alors associés à une session qui prend la forme d'un dossier dans le dossier "home". C'est le même fonctionnement que le dossier "Utilisateurs" sur Windows. 

Tapez la commande suivante pour afficher la liste des comptes utilisateurs disponibles :
``` 
cut -d: -f1 /etc/passwd
```
> Combien y a-t-il d'utilisateur.rice.s ?
> .  
> .  
> .  
> .   

Tapez la commande suivante puis affichez à nouveau la liste des comptes utilisateurs disponibles :
```
deluser utilisatrice2
```
> Que s'est-il passé ?
> .  
> .  
> .  
> .    

> Listez à nouveau le contenu du dossier courrant. Que contient-il ? Cela vous surprend-t-il ?
> .  
> .  
> .  
> .    

---

## Surpprime
Tapez la commande suivante :
```
rm utilisatrice2
```

> Quel message vous est renvoyé ?
> .  
> .  
> .  
> .   


La commande `rm` permet de supprimer un fichier quel qu'il soit. 

Cette commande doit être activée en mode **récursif** pour supprimer un dossier : `rm -r <nom de fichier>`. Cela supprime donc l'objet "dossier" ainsi que tous les objets qu'il contient, fichiers ou dossiers.

Tapez la commande suivante :
```
rm -r utilisatrice2
```

Si vous listez le contenu du dossier courrant, vous voyez que le dossier "utilisatrice2" a désormais disparu. 

---
## Genèse

Tapez les commandes suivantes :
```
cd utilisatrice1
mkdir creation1
touch creation2
touch creation3.txt
```

> Donnez le chemin absolu du dossier courant.
> .  
> .  
> .  
> .   

> Quelle est la différence entre l'objet **creation1** et **creation2** ?
> .  
> .  
> .  
> .   

> Quelle est la différence entre l'objet **creation2** et **creation3** ?
> .  
> .  
> .  
> .    

> Qu'en déduisez-vous des effets respectifs des commandes `touch` et `mkdir` ?
> .  
> .  
> .  
> .   

---
## Connecté !
Tapez les commandes suivantes :
```
wget https://github.com/alix-tz/supports-cours-uvsq/blob/master/linux/lorem.md

wget https://raw.githubusercontent.com/alix-tz/supports-cours-uvsq/master/linux/linux.jpg
```

Si vous listez le contenu du répertoire courrant, vous voyez que deux nouveaux fichiers sont apparus : `lorem.md` et `linux.jpg`. 

En effet, `wget` vous permet de télécharger des fichiers depuis une adresse url. 

---
## Ca déménage

Tapez les commandes suivantes :
```
mv linux.jpg /home/utilisatrice1/
mv lorem.md creation1/lorem2.md
```
Si vous listez le contenu du dossier courrant, vous voyez que les fichiers `linux.jpg` et `lorem.md` ont disparu. 

> Où se trouvent-il respectivement ?
> .  
> .  
> .  
> .   

> Qu'en déduisez-vous des deux fonctions de la commande `mv` ?
> .  
> .  
> .  
> .   

Tapez la commande suivante :
```
cp creation1/lorem2.md lorem.md
```

> Expliquez ce qu'il se passe ?
> .  
> .  
> .  
> .    

---
## Mode

Tapez la commande suivante :
```
touch .hide.txt
ls -l
ls -al
```

`-l` et `-a` sont deux arguments de la commande `ls` qui peuvent être combinés sous la forme `-al`. 
- `ls -l` permet de présenter le contenu du répertoire sous la forme d'une liste détaillée
- `-al` permet d'afficher tout le contenu du répertoire, y compris les objets dits "cachés", dont le nom commence par un `.`.

Parmi les informations affichées en mode liste, on trouve : 
- la **nature de l'objet** (`-` pour un fichier, `d` pour un dossier, `l` pour un lien symbolique, etc)
- ses **droits associés** pour le propriétaire, le groupe actif et les autres utilisateurs sous la forme de trois séries de trois lettres ou tirets (`rwx` équivaut au mode `7`, `r--` au mode `4`, etc).
- le **nombre de fichiers** non cachés qu'il contient ou représente
- le **nom d'utilisateur du propriétaire** de l'objet
- le **nom du groupe** actif
- la **taille du fichier** en octets
- sa **date de création**
- son **nom**

> Quel est le mode du fichier `.hide.txt`?
> .  
> .  
> .  
> .    

> Que se passe-t-il si vous tapez la commande suivante : `chmod 777 .hide.txt` ?
> .  
> .  
> .  
> .    

> La commande `chmod 761 .hide.txt` est-elle valide ?
> .  
> .  
> .  
> .    

---
## Du texte, du texte
Les commandes `less` et `cat` permettent de lire le contenu d'un fichier. La touche `q` permet de quitter le mode lecture de **less**. 

Pour éditer `lorem1.md` depuis la ligne de commande, tapez la commande suivante :
```
nano lorem1.md 
```
