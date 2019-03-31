<!-- $theme: default -->
<!-- page_number: true -->

Initiation à Markdown et LaTeX
====

**MIEC211 - Module 2**


-- 
Alix Chagué


*alix.chague@uvsq.fr*
*IECI - Université Versailles Saint-Quentin*

---

# Objectifs du cours
- savoir définir ce qu'est un **texte numérique**
- savoir mettre en forme un texte numérique avec **Markdown**
- savoir créer un document numérique avec **LaTeX**


---
# Plan des séances
### 1er mars :
texte numérique, Markdown et introduction de LaTeX

### 15 mars : 
approfondissement de LaTeX

---
# Evaluation
- une évaluation sur table le 15 mars (notée du 6)
- un rendu en fin de chaque séance, soit 2 au total (noté chacun sur 7)

---

Le texte numérique et ses notions clefs
===

---
# Du binaire au texte numérique (1)

Ce que comprend un ordinateur :

``` md
01010101 01010110 01010011 01010001
```

Ce que comprend un humain :

``` md
UVSQ
```

---
# Du binaire au texte numérique (2)

On appelle **`texte brut`** un texte lisible par l'humain résultant d'un encodage très simple permettant de traduire des trains binaires (suites de 0 et de 1) en quelque chose de facilement lisible par l'humain, mais sans aucune mise en forme.

Un fichier **`.txt`** ou **`.md`** est un fichier de texte brut.

---
# brut vs. binaire 
![texte brut](./images/brut.png)

![texte binaire](./images/binaire2.PNG)

---
# Encodage/décodage du binaire (1)

Le **`character set`** (jeu de caractères) détermine la manière dont les trains binaires sont interprêtés par l'ordinateur. Ces jeux de caractères sont en réalité des normes d'encodage. Il en existe énormément !

---
# Encodage/décodage du binaire (2)

Quelques exemples :
- **`ASCII`** (*American Standard Code for Information Interchange*) : très répandu parce qu'ancien (1963) : 128 codes en 7 bits pour l'anglais.
- **`UTF-8`** (*Universal character set Transformation Format - 8 bits*) : sauveur des informaticien·nes francophones (1996) : plusieurs milliers de caractères. 


> *Un `bit` est une instance de 0 ou de 1*
> *Un `octet` (8 bits) est une suite de 8 instances de 0 ou de 1*

---
# Encodage/décodage du binaire (3)

![exemple_mauvaise_décodage](./images/ex_characterset_error.PNG)

---
# Texte enrichi
Un **`texte enrichi`** est un texte encodé (comme le texte brut) mais qui contient en plus des informations de mise en forme, généralement sous la forme de balises. 

Un fichier **`.rtf`** ou **`.doc`** est un fichier de texte enrichi.

---

![exemple texte enrichi](./images/ex_text_enrichi.PNG)

![exemple texte enrichi](./images/ex_text_enrichi2.PNG)

---
# WYSIWYG vs. WYSIWYM
**`WYSIWYG`** ("*What You See Is What You Get*") : le texte est mis en forme au fur et à mesure qu'il est rédigé, et le rendu visuel est immédiat.

**`WYSIWYM`** ("*What You See Is What You Mean*") : on peut intégrer des instructions sémantiques ou de mise en forme dans le texte, mais il a besoin d'être **`compilé`** dans une chaîne éditoriale pour donner un rendu visuel de ces instructions.

---

Markdown 
===

![logo_markdown](./images/md_logo_sm.PNG)

---
# Markdown
**`Markdown`** est un langage de balisage léger qui permet d'encoder facilement la mise en page d'un texte sans gêner sa lecture. Il a été créé en 2004 par John Gruber et Aaron Swartz, deux informaticiens américains.

Après compilation, il est facilement converti en **`PDF`** ou en **`HTML`**. Markdown permet donc de créer rapidement des contenus web ou des documents... comme cette présentation ! 

Un fichier **`.md`** est encodé en Markdown.

---
# Mettre en forme avec Markdown (1)

Markdown ne permet pas de *tout* encoder de la mise en forme mais avec on peut :

Mettre en **gras**, en *italique*, ou les ***deux*** à la fois.

~~Barrer un texte~~ ou le ==surligner==  

- faire des listes non-ordonnées
1. faire des listes ordonnées
2. - et les imbriquer

Créer des [liens hypertextes](http://perdu.com/)

| Faire des tableaux | en maîtrisant | l'alignement  |
| :----------------- | :-----------: | ------------: |
| ...                | ...           | ...           |

---

# Mettre en forme avec Markdown (2)

> faire des citations


``` markdown
insérer du code en bloc
```

ou bien l'insérer `en ligne`.

insérer des images :

![logo_markdown](./images/md_logo.png)

---
# Mettre en forme avec Markdown (3)

Structure le texte avec 6 niveaux :
# titre 1
## titre 2
### titre 3
#### titre 4
##### titre 5
###### titre 6

---
# En Markdown : (1)
``` md
Mettre en **gras**, en *italique*, ou les ***deux*** à la fois.

~~Barrer un texte~~ ou le ==surligner==  

- faire des listes non-ordonnées
1. faire des listes ordonnées
2. - et les imbriquer

Créer des [liens hypertextes](http://perdu.com/)

| Faire des tableaux | en maîtrisant | l'alignement  |
| :----------------- | :-----------: | ------------: |
| ...                | ...           | ...           |

```

---
# En Markdown : (2)
``` md
---

> faire des citations

``` markdown
insérer du code en bloc
``` _

ou bien l'insérer `en ligne`.

insérer des images :
![logo_markdown](https://cdn.iconscout.com/.../markdown.png)
```

---
# En Markdown : (3)
``` md
# titre 1
## titre 2
### titre 3
#### titre 4
##### titre 5
###### titre 6
```

### Pour tout revoir d'un coup :
[https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)

---
# Markdown en pratique

https://dillinger.io/
---

---
Exercice de mise en forme avec Markdown
---

Reproduisez le plus fidèlement possible la mise en forme suivante : 
> [shorturl.at/imorN](https://github.com/alix-tz/cours_markdown-latex/tree/master/markdown)

---

![latex logo](./images/latex_logo.png)

---

# LaTeX : définition
**`LaTeX`** est un langage et un système de composition de documents. Contrairement à Markdown, LaTeX est très complet, mais aussi beaucoup plus difficile à lire sans compilation. Comme Markdown, il est libre et gratuit.

Un fichier **`.tex`** est écrit en LaTeX.

Compilé, un fichier LaTeX produit un document au format **`PDF`** de plusieurs types possibles : articles, cv, livre, présentation, ...

---
# (La)TeX

**`TeX`** a été créé en 1977 par l'américain Donald Erwin Knuth, chercheur en informatique. Le but de `TeX` est de produire des articles intégrant plus facilement des formules mathématiques dont la mise en page est complexe. 

**`LaTeX`** est une surcouche de `TeX` mise au point en 1985 par l'américain Leslie Lamport, également chercheur en informatique, pour faciliter son utilisation. 

---

# Le choix de LaTeX

**`LaTeX`** permet de créer des documents extrêmement structurés et beaux. Il gère automatiquement la mise en page, mais aussi l'intégration de normes typographiques propre à chaque langue. 

`LaTeX` crée des `PDF` dont la mise en page ne varie pas d'une machine à l'autre.

On peut installer `LaTeX` sur sa machine, ou bien utiliser un éditeur/compilateur en ligne.

---
# Anatomie d'une commande LaTeX

- commence toujours par `\ `
- suivi du nom de la commande
- suivi (ou pas) de `[]` ou de `{}` ou les deux...

Par exemple : 

``` latex
\commande[params]{params}
```

---
# Exemples de commandes

``` latex
\S 

\LaTeX

\textbf{blablabla}

\usepackage[utf8]{inputenc}
```

---
# Environnement LaTeX

- commence par `\begin{}`
- se termine par `\end{}`
- porte un nom, indiqué entre les `{}`

Comme les commandes simples, les **`environnements`** ont de nombreux usages et permettent d'appliquer des traitements à une portion de texte comprise entre le début et la fin de l'environnement.

```
\begin{env}

\end{env}
```

---
# Commenter en LaTeX

On peut intégrer des éléments de commentaire dans le fichiers. Ces commentaires n'apparaîtront pas dans le document après compilation. 

```
% ceci est un commentaire
```

---
# Caractères réservés

Les caractères réservés sont des caractères qu'on ne peut pas utiliser "normalement" car ils ont un sens pour le compilateur.

``` latex
# $ % & _ ^ { } \
```

Pour les utiliser, il faut les `échapper` :

``` latex
\# \$ \% \& \_ \^ \{ \} \backslash
```

> La plupart des erreurs de compilation résultent de l'usage d'un caractère réservé non échappé (notamment le discret `_` dans les URL)

---
# Commencer un document LaTeX
Un document LaTeX ne peut pas fonctionner sans sa structure de base : 

``` latex
\documentclass[...]{book}
\usepackage[...]{inputenc}

\begin{document}

% contenu du document

\end{document}
% fin du document
```

---
# Types de documents LaTeX
``` latex
\documentclass[a4paper, 12pt, twoside]{book}
```

La première ligne d'un fichier LaTeX, `\documentclass[]{}` indique la nature du document à générer. 

Entre `[]`, on indique des options comme la taille du papier, la taille de la police, s'il s'agit d'un document recto-verso, etc.

Entre `{}`, on indique le type de document comme : 

| `book`           | `article` | `report` | `beamer`     |
| :--------------: | :-------: | :------: | :----------: |
| livre ou mémoire | article   | rapport  | présentation |

> chaque document class a ses spécificités

---
# Import de `package` (paquet)
``` latex
\usepackage[utf8]{inputenc}
```

`LaTeX` fonctionne avec des paquets intégrés, qu'on appelle `built-in packages` qui sont disponibles dès l'installation mais qui doivent être activés, notamment avec la commande `\usepackage[]{}`.

**`inputenc`** est un paquet qui permet de spécifier l'encodage du texte, par exemple ici : **UTF-8**.

Il peut être nécessaire d'installer des paquets supplémentaires.

---
# Corps du document
Un fichier LaTeX est divisé en deux parties : 
1. le **`préambule`**, où sont données les instructions de compilation et des métadonnées.
2. le **`corps du document`**, rédigé au sein d'un `environnement` nommé "document".

``` latex
\begin{document}
...
\end{document}
```

---
# LaTeX en pratique

https://www.overleaf.com/

---
# Vademecum de LaTeX (1)

``` latex
\textit{texte en italique}
\textbf{texte en gras}
\underline{texte souligné}
\fbox{texte encadré}
\texttt{texte monospace}
\textsuperscript{texte en exposant}
\textsubscript{texte en indice}
\textsc{texte en petites capitales}
```
``` latex
% avec ou sans accolades

\tiny{texte très très petit}
\scriptsize{texte très petit}
\small{texte petit}
\normalsize{texte de taille normale}
\large{texte en grand}
\Large{texte en plus grand}
\LARGE{texte en encore plus grand}
\huge{texte de taille énorme}
```

---
# Vademecum de LaTeX (2)
``` tex
\begin{itemize}
    \item 
\end{itemize}
```
``` tex
\begin{enumerate}
    \item
\end{enumerate}
```
``` tex
\begin{enumerate}
    \item
    \begin{itemize}
      \item
    \end{itemize}
\end{enumerate}
```
---
# Vademecum de LaTeX (3)
``` tex
\begin{quotation}
...citation...
\end{quotation}

\begin{quote}
...citation...
\end{quote}
```

``` tex
\og{} % guillement ouvrant
\fg{} % guillement fermant
\\ ou \newline % retour à la ligne
\newpage ou \clearpage % nouvelle page
```

---
# Vademecum de LaTeX (4)
``` tex
% faire tableau :
\begin{tabular}{l|ccc} % alignement et séprations d'une ligne
    case 1 & a & b & c \\ % ligne 1
    case 2 & a & b & c \\ % ligne 2
    \hline 		  % trait de séparation horizontal
    case 3 & a & b & c    % ligne 3
\end{tabular} 

% insérer une image :
% -- dans le préambule, installer GRAPHICX
\usepackage{graphicx}
% -- dans le corps, appeler l'image
\includegraphics[<taille>]{chemin/vers/img}

% <taille> : widht=<>px et/ou height=<>cm ou scale=<>
```

---
# Vademecum de LaTeX (5)
``` tex
% créer une figure
\begin{figure}[<position>] % <position> : h, t, b, ou p
    \centering % pour centrer la figure horizontalement
    \includegraphics[]{} % insertion de l'image
    \caption{ceci est une légende} % peut être avant image
    \label{fig:unlabel} % pour table des figure et références
\end{figure}

% faire liste des figures ou des tableaux
\listoffigures
\listoftables

% faire des liens hypertexte
% -- dans le préambule installer HYPERREF
\usepackage{hyperref}
% -- dans le document
\url{<url>} 		% pour URL
\href{<url>}{<texte>} 	% pour lien hypertexte
```

---
# Vademecum de LaTeX (6)
``` tex
% les niveaux varient en donction des classes de document !
\part{titre de partie} 			% niveau 1
\chapter{titre de chapitre} 		% niveau 2
\section{titre de section} 		% niveau 3
\subsection{titre de sous-section} 	% niveau 4
\paragraph{titre de paragraphe}	 	% niveau 5
\subparagraph{titre de sous-paragraphe} % niveau 6

\section*{titre} 	% pour retirer niveau dans la TOC

\tableofcontents 	% afficher la TOC

% structuration supplémentaire :
\frontmatter 		% équivalent de la couverture
\maketitle 		% page de titre
\mainmatter 		% corps du document
\appendix 		% annexes
\backmatter 		% équivalent du dos
```

---
# Vademecum de LaTeX (7)
``` tex
% métadonnées dans le préambule
% elles apparaissent sur la page de titre (\maketitle)
\author{<pénom nom>}
\title{<titre du document>}
\date{<date>}
% il y en a d'autres !

% insérer des notes
\footnote{<contenu de la note de bdp>}
```

Pour faire sa bibliographie, ne pas hésiter à regarder la documentation en ligne :
- fr.wikibooks.org/wiki/LaTeX/Gestion_de_la_bibliographie