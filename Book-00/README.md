


# Sommaire 
- [Sommaire](#sommaire)
- [Avant d'apprendre à programmer](#avant-dapprendre-à-programmer)
- [Qu'est-ce qu'un octet ?](#quest-ce-quun-octet-)
- [Comment représenter un texte avec des octets ?](#comment-représenter-un-texte-avec-des-octets-)
- [Les fichiers binaires et texte](#les-fichiers-binaires-et-texte)
- [Mais les fichiers Word c'est des fichiers texte ?](#mais-les-fichiers-word-cest-des-fichiers-texte-)
- [Apprendre à créer un fichier texte](#apprendre-à-créer-un-fichier-texte)
  - [Sur Windows](#sur-windows)
  - [Sur Mac OS](#sur-mac-os)
    - [Ouvrir d'abord TextEdit](#ouvrir-dabord-textedit)
    - [Créer un fichier texte](#créer-un-fichier-texte)
    - [Enregistrer le fichier texte](#enregistrer-le-fichier-texte)
  - [Sur Linux](#sur-linux)
- [Écrire votre premier code C++](#écrire-votre-premier-code-c)
- [La terminologie](#la-terminologie)



# Avant d'apprendre à programmer
<p align="justify"> 
Avant de rentrer dans le coeur du sujet, à savoir, la programmation, je vous propose d'abord d'en apprendre plus sur la matière première de votre ordinateur : les fichiers. 
L'objectif de ce cours est donc d'abord de vous introduire la différence entre fichier binaire et fichier texte pour ensuite vous apprendre à créer un fichier texte contenant du code C++.
</p>

<p align="justify"> 

</p>

<p align="justify"> 
Ici, seules les informations dont vous avez besoin pour comprendre le cours sont introduites. Cependant, il existe des cours beaucoup plus adaptés pour apprendre la théorie de Bool, les mathématiques logiques etc.
</p>

<p align="justify"> 
Si vous n'êtes pas familiés avec l'informatique, les notions introduites dans ce premier *book* risquent d'être compliquées à comprendre. Je vous invite à le lire tout de même, à en prendre connaissance et à ne pas vous arrêter sur les détails que vous ne comprenez pas. Ayez confiance en votre cerveau, il va cogiter dessus et plus tard, avec l'expérience, tout va se lier tout seul. 😊
</p>



# Qu'est-ce qu'un octet ?
<p align="justify"> 
En décimale, chaque chiffre nous permet de compter de 0 à 9. Les nombres décimaux sont composés de chiffres et permettent de compter au-delà de 10.
En binaire, les unités sont des bits et nous permettent de compter de 0 à 1. Les octets sont composés de huits bits et permettent de compter au-delà de 1.
</p>

Ainsi, il est par exemple possible de compter avec des octets de 0 à 10 de la manière suivante : 
- 0 en décimale = 00000000 en binaire
- 1 en décimale = 00000001 en binaire
- 2 en décimale = 00000010 en binaire
- 3 en décimale = 00000011 en binaire
- 4 en décimale = 00000100 en binaire
- 5 en décimale = 00000101 en binaire
- 6 en décimale = 00000110 en binaire
- 7 en décimale = 00000111 en binaire
- 8 en décimale = 00001000 en binaire
- 9 en décimale = 00001001 en binaire
- 10 en décimale = 00001010 en binaire 


Un octet peut contenir des valeurs comprises en 0 et 255 (2<sup>8</sup>-1).


# Comment représenter un texte avec des octets ?

<p align="justify"> 
Nous allons maintenant introduire la notion de représentation d'un texte par des octets. Cette notion est assez avancée et difficile à comprendre mais elle me paraît importe à introduire pour mieux appréhender les différents types de fichiers qu'il vous est possible de rencontrer dans un ordinateur.  
</p>


<p align="justify"> 
Le caractère est une lettre ou un signe servant à la composition des textes. En informatique, un caractère peut prendre la forme d'une lettre minuscule (e.g. 'a'), d'une lettre majuscule (e.g. 'A') ou d'un caractère spécial (e.g. ',').
Une suite d'octets peut être utilisée pour représenter un texte.
Chaque octet encode un nombre (e.g. 01000001) et chaque nombre est associé à un caractère (e.g. 'A'). 
</p>


<p align="justify"> 
En suivant ce principe, des programmes utilisent ce que nous nommons la table ASCII. 
À chaque nombre est associé un caractère. 
Exemple,  le "A" (majuscule) est associé au nombre 65. 
Ainsi, chaque octet contient un caractère (possiblement une lettre) et une suite de ces octets permet d'écrire un texte. Pour écrire le mot "BONJOUR", en majuscule, il vous faut donc les octets suivants : 
</p>

- B = 66 en décimale = 01000010
- O = 79 en décimale = 01001111
- N = 78 en décimale = 01001110
- J = 74 en décimale = 01001010
- O = 79 en décimale = 01001111
- U = 85 en décimale = 01010101
- R = 82 en décimale = 01010010



Ci-dessous, un apperçu de la table ASCII en question : 

| Caractère | Nombre Décimal | Binaire (sur un octet) |
|:---------|:--------:|---------:|
| A | 65 | 01000001 |
| B | 66 | 01000010 |
| C | 67 | 01000011 |
| D | 66 | 01000100 |
| E | 67 | 01000101 |
| F | 68 | 01000110 |
| G | 69 | 01000111 |
| H | 70 | 01001000 |
| I | 65 | 01001001 |
| J | 65 | 01001010 |

<p align="justify"> 
Imaginons maintenant que je vous donne un texte sous forme d'octets. Je vais vous aider, je sépare chaque octet par un espace pour rendre le texte plus lisible :  
</p>

```01001010 00100111 01000001 01000000 01000110 01000001 01001001 01001101```

<p align="justify"> 
Notez que nous nommons cela une chaine de caractères, nous reviendrons dans quelques chapitres sur cette définition.
</p>

<p align="justify"> 
Il ne vous est pas évident de lire le mot que je viens de vous écrire en binaire.
Pour rendre ces chaines de caractères plus faciles à lire, les machines les affichent sous forme de texte. Dans la suite de ce *book*, nous allons introduire les fichiers binaires – qui n'ont pas pour objectif d'être lus par des utilisateurs (humains) – et texte.
</p>



# Les fichiers binaires et texte

<p align="justify"> 
Nous pouvons discerner deux types de fichiers sur les ordinateurs. 
Les fichiers texte et les fichiers binaires.
</p>

<p align="justify"> 
Le <strong>fichier binaire</strong> contient un ensemble d'octets dans lesquels des valeurs sont stockées. 
Le fichier tel quel ne peut être lu par un humain. 
Un programme peut cependant lire un fichier binaire pour charger la carte d'un jeu vidéo par exemple. L'image ci-dessous vous montre le contenu d'un fichier son affiché sous la forme d'un texte : 
</p>

<p align="center"><img src="images/wav_file_opened_as_text.png" alt="Affichage sous la forme textuelle d'un fichier audio" width="400"/></p>

<p align="justify"> 
Le contenu de ce fichier n'étant pas du texte, il nous est impossible d'interpréter son contenu à partir de son affichage textuel.
</a>

<p align="justify"> 
Le <strong>fichier texte</strong> est un cas particulier du fichier binaire et, comme son nom l'indique, contient une suite de caractères (a, b, c, à, 0, 7 etc ...) qui forme un texte. Un programmeur écrit généralement son code dans un fichier texte. Par exemple, j'écris ce cours en markdown comme illustré ci-dessous : 
</p>

<p align="center"><img src="images/markdown.png" alt="Exemple de code markdown ouvert sur un éditeur de texte simple" width="400"/></p>

<p align="justify"> 
Les étoiles sont un élément de syntaxe qui permet au programme de comprendre que le texte doit être mis en gras. D'autres éléments syntaxes existent et peuvent être utilisés pour agrémenter le texte. Vous noterez aussi que le contenu du fichier, dont les éléments de syntaxe, est un texte et qu'il est facile à lire.
</p>



# Mais les fichiers Word c'est des fichiers texte ? 
<p align="justify"> 
Et bien non ! Si j'en parle ici, c'est parce que j'ai déjà vu des étudiants essayer de coder depuis "Word". Cela en fera rire certains. Pour ma part, je trouve ça intéressant. Le principe de fichier texte n'est pas forcément évident à appréhender la première fois et non, Word n'enregistre pas vos fichiers au format texte. 
</p>

<p align="justify"> 
En effet, les fichiers Word sont des fichiers binaires qui sont interprétés par le logiciel de manière à les rendre compréhensibles pour l'oeil humain. Cependant, la matière première, le fichier sauvegardé, est bien un fichier binaire impossible à lire pour un humain. Ne vous y trompez pas. 
</p>

<p align="justify"> 
Ci-dessous, vous trouverez un exemple de fichier au format docx, le format word. Ce fichier est disponible dans le sous-dossier "files" de ce répertoire. La partie supérieure de l'image montre le contenu textuel du fichier tandis que l'image inférieure montre le fichier tel que LibreOffice Writer le montre.
</p>

<p align="center"><img src="images/word_file_opened_as_text.png" alt="Exemple d'affichage textuel d'un fichier word. L'image au-dessous affiche le contenu de cet affichage, l'image en-dessous montre l'affichage de ce fichier par le logiciel LibreOffice Writer." width="600"/></p>

<p align="justify">Vous pouvez constater que la partie supérieure n'est pas compréhensible. A contrario, vous n'avez aucun problème à lire le texte présent dans la partie inférieure. Dans le cas d'un fichier texte, vous n'auriez eu aucun problème à lire le fichier d'origine. </p>



# Apprendre à créer un fichier texte

Passons à la pratique ! Pour apprendre à programmer, vous allez devoir écrire votre premier fichier contenant du code C++. Puisque tout le monde n'utilise pas le même système d'opération, je vous propose ci-dessous une version pour celles et ceux qui utilisent Windows, une autre pour Mac OS et une pour Linux.

## <a name="windows"></a>Sur Windows
Sur votre ordinateur, cherchez d'abord le programme bloc-note pour écrire votre fichier en appuyant sur la touche windows. Comme décrit dans la figure ci-dessous, une fois que vous avez trouvé le logiciel bloc-note, appuyez sur la touche entrer.

<p align="center"><img src="images/windows_search_bloc_note.png" alt="Chercher un bloc note dans la barre de windows" width="600"/></p>

Une fois le logiciel ouvert, enregistrez vos fichiers en allant dans Fichier => Enregistrer sous ou en appuyant sur ctrl+s. Lors de l'enregistrement, renseignez d'abord le nom du fichier et pensez à choisir l'option "Tous les fichiers" pour le champs "type" comme illustré dans la capture ci-dessous.


<p align="center"><img src="images/windows_sauvegarde.png" alt="Sauvegarder le fichier texte au format .cpp" width="600"/></p>


## Sur Mac OS

### Ouvrir d'abord TextEdit
Pour créer un fichier texte contenant votre code C++ sur Mac OS, vous devez d'abord lancer TextEdit. Pour cela, appuyez sur ⌘+espace et écrivez TextEdit dans la barre de recherche qui s'est affiché. Puis, appuyez sur entrer.
<p align="center"><img src="images/mac_search_textedit.png" alt="Chercher textedit dans la barre de recherche de Mac" width="600"/></p>

### Créer un fichier texte
Le format par défaut de TextEdit est le format de texte enrichi – un peu l'équivalent des docx de Word. Vous pouvez changer cela en allant dans TextEdit -> Réglages et en sélectionnant Format Texte. Ensuitez, créez un nouveau fichier en appuyant sur ⌘+N ou en allant dans Fichier -> Nouveau.

<p align="center"><img src="images/mac_reglage_nouveau.png" alt="Chercher textedit dans la barre de recherche de Mac" width="600"/></p>


### Enregistrer le fichier texte
Pour finir, vous pouvez enregistrer votre fichier en appuyant sur ⌘+S ou en allant dans Fichier -> Enregistrer. Entrez d'abord un nom de fichier finissant par ".cpp" tel que "monfichier.cpp". Décochez la case avec écrit "Utiliser « .txt » à défaut d'extension".

<p align="center"><img src="images/mac_sauvegarde.png" alt="Sauvegarder un fichier avec TextPad" width="350"/></p>

## Sur Linux
Pour Linux, en partant du principe que vous utilisez ubuntu, le processus est le même que celui de Windows. Seulement, au lieu d'utiliser le logiciel "bloc-note", vous devez utiliser le logiciel "Geany".



# Écrire votre premier code C++
Maintenant que vous savez créer et sauvegarder un fichier texte au format ".cpp", je vous invite à ajouter les lignes de code suivantes dans votre fichier. Le fichier ne doit contenir que ces lignes.

```c++
#include<iostream>

using namespace std;

int main() {
  cout << "Hello World!" << endl;
  return 0;
}
```

Félicitation, vous avez créé votre premier fichier contenant du code C++. La seconde étape consiste à compiler ce fichier pour pouvoir l'exécuter. Tout cela vous est présenté dans le *book* suivant que je vous invite à lire.


# La terminologie

- **Bit :** une unité d'information pouvant prendre la valeur 0 ou 1.
- **Octet :** une suite de 8 bits. L'octet peut représenter des valeurs allant de 0 à 255.
- **Chiffre :** l'unité d'information pouvant prendre la valeur 0, 1, 2, 3, 4, 5, 6, 7, 8 ou 9.
- **Nombre Décimal :** est composé de plusieurs chiffres et permet de compter au delà de 9.
- **Caractère :** l'unité d'information d'un texte. Un caractère peut être une lettre minuscule (e.g. 'a'), une lettre majuscule (e.g. 'A') ou un caractère spécial (e.g. ',').  
- **Chaine de caractères :** est une suite de caractères, plusieurs caractères mis les uns à la suite des autres. Une chaine de caractères peut former un mot, un texte, une code etc. Exemples : "Bonjour", "BONJOUR", "BOnJouR", "Je parle tous les jours.", "if(true)", etc.
- **Fichier binaire :** est composé d'un ensemble d'octets qui n'ont pas nécessairement pour objectif d'être lus par des humains. Les programmes peuvent cependant s'en servir. Exemples : carte d'un jeu vidéo, un fichier word ou un enregistrement audio.
- **Fichier texte :** est un cas particulier du fichier et a pour vocation a être lu par un humain.
