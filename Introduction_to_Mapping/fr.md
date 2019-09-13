{{\#customtitle:Introduction à la création de carte|Introduction à la création de carte}} __TOC__

Introduction
------------

### Qu'est-ce que MapTool ?

Bien que vous ayez probablement une idée de ce qu'est MapTool et qu'il fait, nous voulons juste prendre un moment pour réaffirmer l'objectif premier de MapTool :

**MapTool est un programme qui vous aide à partager une “table de jeu virtuelle” avec vos amis, afin que vous puissiez jouer ensemble.**

C'est ce que MapTool fait, et ses fonctionnalités sont pensées pour fournir un ensemble d'options, de la plus simple à la plus complexe, pour atteindre cet objectif.

Parmi tout le blabla sur les macros, propriétés, tables, programmation qui va suivre dans ce guide et d'autres, ne perdez pas de vue la raison pour laquelle vous essayez MapTool : c'est un moyen de jouer avec vos amis.

### A propos de ce guide

Le but de ce guide n'est pas de plonger dans les arcanes des système de programmation de macros de MapTool, d'éclairage, de propriétés ou n'importe quel autre “truc” compliqué. Au lieu de cela, ce guide devrait vous permettre de démarrer dans l'utilisation de MapTool, en l'utilisant comme un outil de création de carte pour les Jeux de Rôles. D'autres guides abordent des sujets comme

[héberge une partie en ligne](Introduction_to_Game_Hosting/fr "wikilink"), [utiliser les pions](Introduction_to_Tokens/fr "wikilink"), [mettre en place la gestion de la vision et de la luminosité](Introduction_to_Lights_and_Sights "wikilink") et [écrire des macros](Introduction_to_Macro_Writing "wikilink").

Les instructions qui suivent devraient vous permettre de démarrer et d'utiliser MapTool comme un outil de création et d'utilisation de cartes tactiques. Cependant, cela nécessite quelques prérequis :

1.  Vous savez comment créer ou récupérer des images de carte. Il y a des teraoctets d'images de carte disponibles sur le web. Fouillez par exemple [la galerie de RPTools](http://gallery.rptools.net) ou[RPGMapShare](http://www.rpgmapshare.com).

<!-- -->

1.  Vous pouvez démarrer MapTool sur votre ordinateur. MapTool nécessite Java 1.5 (minimum).

Donc, nous y voilà. Pour commencer :

1.  Récupérez MapTool à partir de <http://rptools.net>. La dernière version de MapTool peut toujours être trouvée au début de [cette liste](http://www.rptools.net/index.php?page=downloads#MapTool). **NOTE**: Vous pouvez aussi démarrer via [le Java WebStart](http://www.rptools.net/index.php?page=launch) sans avoir à télécharger et dézipper de fichier.
2.  Si vous téléchargez le fichier zip de MapTool, décompressez le quelque part sur votre ordinateur et assurez vous qu'il démarrer. Les fichier .bat fournis renseignent quelques paramètres automatiquement, comme la mémoire allouée. MapTool démarrera si vous double-cliquez sur le fichier .jar, mais en affichant quelques avertissements. Si vous utilisez Windows, il est possible d'utiliser le “Windows Launcher” aussi, qui permet de modifier aisément le paramétrage.

Maintenant, cartographions utile.

Ajouter des Images à votre bibliothèque de Ressources MapTool
-------------------------------------------------------------

La **Bibliothèque de Ressources** de Maptool est en fait une collection de “pointeurs” ou “liens” vers des répertoires de votre ordinateur, contenant des images que vous voulez utiliser avec MapTool. MapTool est livré avec un ensemble d'images, mais vous pouvez ajouter n'importe quelle image - vous contrôlez quelles images sont disponibles dans MapTool.

![](Mt-f-addtoreslib.jpg‎ "fig:Mt-f-addtoreslib.jpg‎")

![](File-dialog.jpg "File-dialog.jpg")

1. Obtenez quelques images (des cartes par exemple) : téléchargées du web ou créées par vos soins. Placez les dans un répertoire que vous retrouverez - ce répertoire est important pour l'étape 3.

2. Lancez MapTool.

3. Sélectionnez le menu **Fichier -&gt; Ajouter à la bibliothèque de Ressources** (voir les images à gauche). Cela ouvrira la fenêtre de dialogue appelée **Charger une bibliothèque de Ressources** (cliquez sur la miniature pour voir une image grande taille).

4. Dans la fenêtre de dialogue, placez-vous dans le répertoire où vous avez placé les images que vous voulez ajouter, et cliquez sur **Ouvrir**. MapTool parcourera les images contenues dans le répertoire indiqué et ajoutera un nouveau dossier dans l'arborescence “Resource Library” dans MapTool.

**NB** : le nom du dossier dans la “Resource Library” de MapTool sera le même que le nom du répertoire choisi à l'étape 3.

![](Mtreslib.jpg "fig:Mtreslib.jpg")

5. Ensuite, si vous sélectionnez un des dossiers dans la “Ressouce Library” (cf. l'image ci-dessous), vous verrez des miniatures des images de ce dossier. NB : si votre répertoire a des sous-répertoires, cliquez sur le **+** pour déployer l'arborescence. De plus, vous n'aurez pas besoin d'ajouter de nouveau ce répertoire - MapTool se souviendra de ce que vous avez choisi.

**NB** : Puisque les dossiers qui apparaissent dans la “Ressource Library” sont en réalité des liens vers des répertoires du disque dur, MapTool ne duplique pas chaque fichier -- la “Ressource Library” est juste un moyen pour MapTool de savoir où se trouvent les images.

Créer une Carte
---------------

![](Map-newmap.jpg "Map-newmap.jpg")

![](Map-new-dialog.jpg "Map-new-dialog.jpg")

1. Menu **Carte -&gt; Nouvelle carte...**. Cela affichera la fenêtre de dialogue *Map Properties*.

2. Sur le côté gauche de la fenêtre *Map Properties*, vous trouverez plusieurs options et zones de texte.

-   **Name**: ceci est le titre de la carte. Notez bien que si vous sélectionnez une image de carte (“map image”), le titre sera réinitialisé au nom du fichier image mais vous pourrez le remodifier par la suite.
-   **Cell Type**: grille hexagonale ou carrée ou sans grille du tout.
-   **Distance Per Cell**: combien d'unités de mesure arbitraires couvre chaque case/hexagone de la grille (*par exemple*, pour Donjons & Dragons 4, mettez “1”, étant donné que toute distance est comptabilisée en “cases”. Pour Donjons & Dragons 3, mettez “5” étant donné que tout y est mesuré en “pieds”)
-   **Pixels per cell**: combien de pixels chaque case/hexagone couvrira – la valeur par défaut est 50. Ce paramètre est important pour mettre la grille à l'échelle de l'image de carte éventuellement utilisée.
-   **Vision Distance**: MapTool gère la vision, le Brouillard de Guerre, et d'autres fonctions, et ceci indique à quelle distance, par défaut, un personnage peut voir dans la carte.

![](Background-dialog.jpg "fig:Background-dialog.jpg")

3. Cliquez sur le bouton **Background** (arrière-plan) : une fenêtre de dialogue propose différentes options. La texture et/ou couleur d'arrière-plan sont répétées à l'infini dans toutes les directions.

-   **Swatch** (Palette) : permet d'utiliser une couleur uniforme, choisie dans une palette, comme arrière-plan de la carte.

<!-- -->

-   **Hue/RGB** (Nuancier/RVB) : permet de choisir une couleur d'arrière-plan via les composantes rouge/vert/bleu ou un nuancier.
-   **Texture** : donne accès à la bibliothèque de ressources pour choisir une texture (une image) comme arrière-plan.

![](Map-mapbutton.jpg "fig:Map-mapbutton.jpg")

4. Si vous avez une image de carte à l'esprit (téléchargée ou créée via Photoshop, Dundjinni ou autre logiciel de ce type), cliquez le bouton **Map** (carte). Une fenêtre de dialogue s'ouvrira sur la bibliothèque de Ressources. Sélectionnez l'image que vous voulez utilisée. Cette image sera “posée” au-dessus de l'arrière-plan choisie précédemment.

![](Map-create-done.jpg "fig:Map-create-done.jpg")

5. Lorsque vous êtes satisfait de l'arrière-plan et de la carte – une miniature de prévisualisation permet de vérifier, voir ci-dessous - saisissez un titre, et cliquez sur **OK**. La carte sera chargée dans la fenêtre princiaple de MapTool.

### Créer plusieurs Cartes dans une seule Campagne

MapTool vous permet de créer plusieurs cartes dans une seule campagne (fichier .cmpgn). Le processus est très simple : vous répétez simplement les étapes de [Créer une Carte](Introduction_to_Mapping#Créer_une_Carte "wikilink") pour chaque carte.

Chaque nouvelle carte sera automatiquement créée dans la campagne sur laquelle vous travaillez actuellement (créer une nouvelle carte ne sauvegarde pas automatiquement la campagne, donc assurez-vous de [sauvegardez votre travail](Introduction_to_Mapping#Saving_Your_Work "wikilink") lorsque vous avez terminé).

Vous pouvez aussi ajouter de nouvelles cartes à des campagnes déjà sauvegardées : ouvrez simplement le fichier de campagne (menu **Fichier &gt; Ouvrir Campagne...**) et suivre les étapes pour créer une nouvelle carte.

Fenêtre Principale de MapTool
-----------------------------

### Les calques de MapTool

![](Layer-window.png "Layer-window.png")

Une fois qu'une carte est chargée, vous verrez une petite boîte dans la fenêtre de carte, avec pour titre *Layer* (Calque). Les cartes de MapTool ont quatre niveaux de calque :

-   **Background** (Arrière-plan) : c'est le calque pour les images, cartes d'arrière-plan et tout ce qui n'est pas destiné à bouger/être déplacer.
-   **Hidden** (Caché) : concernant les parties/jeux en ligne, c'est le calque que seul le MJ (GM) peut voir.
-   **Object** (Objet) : c'est le calque pour les “pions” de type “objets”, qui peuvent bouger ou être bougés par les joueurs et MJ (lampes, tables etc.).
-   **Token** (Pion) : ce calque est celui des pions. Les pions sont de petites images qui représentent les Personnages Joueurs (PJ, PC en anglais) et Non Joueurs (PNJ, NPC en anglais). Assurez-vous d'avoir sélectionné le calque “Token” lorsque vous ajoutez des personnages ou ennemis sur la carte.

Pensez aux calques de MapTool comme à quatre différentes feuilles de papier transparent empilées l'une sur l'autre. La plus en-dessous - **Background** (Arrière-plan) - est celle où vous dessinez les éléments basiques de la carte : murs, sols, arbres etc. Sur la page suivante, celle appelée **Object** (Objet), vous dessinez les *choses* que vos personnages pourraient utiliser, ou briser : portes, coffres, tables, chaises etc. Sur la feuille au-dessus - le calque **Hidden** (Caché) - vous placez les choses que seul le MJ peut voir (qui peuvent être des objets ou des personnages cachés qui seront révélés ultérieurement). Finalement, la feuille la plus au-dessus, - le calque **Token** (Pion) -, vous placez vos “figurines” virtuelles : les monstres, personnages joueurs et non joueurs.

Les Pions peuvent être déplacés sur n'importe laquelle des 4 calques de MapTool. Pour ce faire, faites un clic-droit sur l'image du pion et sélectionnez dans le menu contextuel : **Change To &gt;**. Dans le sous-menu qui s'affiche, choisissez le calque de destination du pion, et il y sera déplacé.

### Passer d'une carte à l'autre

![](Blueglobe.jpg "Blueglobe.jpg")

![](Maplist.jpg "Maplist.jpg")

Si vous ne créez qu'une carte dans votre campagne, elle sera chargée par défaut et sera la seule carte que vous pourrez voir.

Si vous avez [créé plusieurs cartes](Introduction_to_Mapping#Cr.C3.A9er_plusieurs_Cartes_dans_une_seule_Campagne "wikilink") ou jouez avec une campagne comportant plusieurs cartes, vous pouvez choisir parmi elles en cliquant sur le globe bleu, la mappemonde, dans le coin supérieur droit de la fenêtre de MapTool. Cela affichera une liste des cartes disponibles. Si vous n'avez qu'une seule carte, cliquer sur la mappemonde affichera le nom de cette carte.

### Zoomer et Déplacer

Pour zoomer sur la carte, vous pouvez utiliser la molette de la souris, ou les touches + et -.

Pour (se) déplacer la carte, faites un clic droit maintenu et bougez la souris.

Pions : les bases
-----------------

Les [Pions](Token:token "wikilink") de MapTool (ou “Tokens”) sont de petites images destinées à représneter de nombreux éléments sur une carte MapTool. L'usage le plus commun pour les Pions est de représenter les personnages joueurs (PJ) et non joueurs (PNJ) - en d'autres termes, les pions prennent la place des figurines sur la table de jeu virtuelle.

Les Pions, comme tout le reste, viennent d'images stockées dans votre [Bibliothèque de Ressources](Macros:Glossary#R "wikilink"). MapTool met à disposition des Pions par défaut (et il existe un excellent programme distinct qui vous permet de créer des Pions : [TokenTool](http://www.rptools.net/index.php?page=tokentool)), ou vous pouvez utiliser les votres, d'où qu'ils viennent.

Cette section de l'Introduction à la Cartographie ne traite que quelques uns des aspects les plus communs et basiques des possibilités offertes par les Pions dans MapTool. Il y a de *nombreuses* fonctionnalités, trucs et fonctions cool disponibles lorsque l'on travaille avec les pions - tant qu'elles méritent un guide à part entière.

### Placer les Pions sur la Carte

![](Default-library.jpg "Default-library.jpg")

1. Pour visualiser les pions par défaut mentionnés ci-dessus, sélectionnez le dossier “Default” dans la Bibliothèque de Ressources (*Resource Library*), et cliquez le **+** pour le développer.

![](Default-tokens.jpg "fig:Default-tokens.jpg")

2. Sélectionnez le dossier des pions (Tokens).

![](Token-drag-to-map.jpg "fig:Token-drag-to-map.jpg")

![](Token-on-map.jpg "Token-on-map.jpg")

3. Dans la fenêtre en-dessous (où les miniatures apparaissent), utilisez la souris pour glisser-déposer le pion sur la carte. Le curseur se transformera en main et vous devez simplement amener le pion sur la carte et relâchez le bouton de gauche de la souris.

En relâchant le bouton de la souris, le pion apparaîtra sur la carte, avec le même aspect que la miniature, comme montré dans la capture d'écran ci-contre.

### Déplacer les Pions

Une fois qu'un pion est placé sur la carte, il peut être déplacé en utilisant la souris (clic gauche maintenu) ou bougé case par case en le sélectionnant (un clic dessus) puis en utilisant les flèches du clavier et en pressant la touche **D** pour terminer le mouvement.

Si vous voulez parcourir un chemin complexe (avec des virages), vous pouvez appuyer sur la touche **Espace** pour créer une ou plusieurs étapes, en cours de mouvement.

### Modifier le nom, nom MJ et label d'un Pion

![](Token-default-name.jpg "Token-default-name.jpg")

![](Edit-token.jpg "Edit-token.jpg")

On peut assigner jusqu'à trois noms à chaque pion. Quand un pion est déposé pour la première fois sur la carte, MapTool lui affecte un nom par défaut (typiquement, le même que le fichier source du pion, sans l'extension). Par exemple, le pion montré dans l'image ci-dessous a été déposé depuis le jeu de pions par défaut de MapTool, et son nom par défaut est “Hero.”

Les trois noms possibles, qu'un pion peut avoir, sont :

-   **Token Name** (Nom du Pion): Le nom sous lequel le pion apparaîtra à tous les utilisateurs (joueurs, MJ et observateurs). Il est obligatoire.
    -   <font color="red">**NB**: Assurez-vous que CHAQUE pion sur la carte a un nom UNIQUE ! Sinon, les macros de MapTool peuvent fonctionner de manière imprévisible.</font>
-   **GM Name**(Nom MJ) : Ce nom n'apprait que pour les personnes connectés à MapTool avec le rôle de MJ (“GM” en anglais).

<!-- -->

-   **Label** (Étiquette): Ce texte apparait (si renseigné) sous le nom du pion, et est visible de tous.

Pour modifier un de ces noms :

1. Double-cliquez sur l'image du pion sur la carte. Cela ouvrir la fenêtre de dialogue **Edit Token** (Modification du Pion), comme le montre la capture d'écran ci-contre.

![](Edit-token-changednames.jpg "fig:Edit-token-changednames.jpg")

![](New-token-names.jpg "New-token-names.jpg")

2. Dnas le champ **Name** (Nom), entrez ce que vous voulez. Dans l'exemple a été saisi “Bork the Brave” (Bork le Courageux).

3. Dans le champ **GM Name** (Nom MJ), saisissez un nom. Dans l'exemple “Cork the Cowardly” (Cork le Couard).

4. Dans le champ **Label** (Étiquette), saisissez un qualificatif. Dans l'exemple “Human Warrior” (Guerrier Humain).

5. Cliquez **OK** pour sauvegarder vos modifications.

Après que vous ayez cliqué sur “Ok”, vous constaterez que le pion a changé :

Vous pouvez réitérer ce processus de modification des noms avec n'importe quel pion sur la carte.

### Modifier l'image d'un Pion

Parfois, quand vous créez un nouveau pion, vous voudrez modifier l'image de celui-ci. Par exemple, vous trouvez une nouvelle image cool que vous *devez* utiliser pour votre Super Méchant, mais vous avez déjà créer un pion pour ce personnage - vous ne voudrez pas effacer intégralement le pion juste pour modifier son image, n'est-ce pas ? A la place, changez juste l'image du pion en utilisant les étapes suivantes :

![](Edit-token.jpg "Edit-token.jpg")

1. Assurez d'avoir une nouvelle image pour le pion, au format PNG ou JPG, déjà disponible dans votre Bibliothèque de Ressources MapTool. Si vous lisez la section [Ajouter des Images à votre bibliothèque de Ressources](Introduction_to_Mapping#Ajouter_des_Images_.C3.A0_votre_biblioth.C3.A8que_de_Ressources_MapTool "wikilink"), au-dessus, cela explique comment obtenir et ajouter des images à votre Bibliothèque de Ressources : en fait, les images de pion (en fait, *n'importe quelle* image) peuvent être ajoutées à votre bibliothèque de ressources de la même façon.

2. Double-cliquez sur le pion pour ouvrir la fenêtre de dialogue **Edit Token** (Modifier le pion).

![](Edit-token-changeimage.jpg "fig:Edit-token-changeimage.jpg")

3. Dans le coin supérieur gauche de la fenêtre, cliquez sur le petit signe plus vert.

![](New-image-picked.jpg "fig:New-image-picked.jpg")

4. Dans la fenêtre de dialogue **Choose Image** (Choisir l'image), sélectionnez le dossier de la bibliothèque de ressources contenant la nouvelle image du pion (une bordure rouge et blanche indique l'image sélectionnée), et cliquez sur **OK**.

![](Token-image-changed.jpg "fig:Token-image-changed.jpg")

5. Une fois le bouton **OK** cliquée, vous êtes ramené à la fenêtre de modification du pion et vous verrez que l'image du pion a été changée pour celle que vous venez de choisir.

### Taille du Pion

![](Token-rightclick.jpg "Token-rightclick.jpg")

Par défaut, les pions ont la taille d'une case de la grille (soit 50x50 pixels si vous avez utilisé la taille de la grille proposée par défaut par MapTool). Si vous faites un clic-droit sur un pion, le menu contextuel montre de nombreuses options, dont l'une est **Size** (Taille). Vous pouvez la modifier en choisissant l'une des valeurs proposées, vous permettant de créer des créatures géantes, gargantuesques ou petites, minuscules etc. L'image ci-dessous illustre le menu contextuel d'un pion.

NB : les valeurs de taille ne s'appliquent qu'aux cartes ayant une grille (rappelez-vous que la grille se définit au moment de la création de la carte). Sur une carte sans grille, les différentes valeurs de taille sont plus fines.

Sauvegarder votre Travail
-------------------------

Le format de sauvegarde par défaut de MapTool est appelé un *fichier de Campagne* (Campaign File). Le fichier de campagne (dont l'extension est *.cmpgn*) contient les cartes et pions que vous avez mis en place. Si vous êtes intéressés par ce genre de chose, le fichier de campagne est en réalité un fichier XML zippé.

Pour sauvegarder votre travail, utilisez le menu **Fichier -&gt; Enregistrer Campagne**, donnez un nom à votre campagne et voilà tout.

Lorsque vous sauvegardez une campagne, MapTool conserve la position de tous les pions sur toutes les cartes, ainsi vous pouvez reprendre l'aventure exactement là où vous l'avez laissée !

Exporter l'image d'une Carte
----------------------------

MapTool peut exporter l'image d'une carte vers un fichier PNG. Pour exporter l'image vers un emplacement de votre choix :

1. Utilisez le menu '''Fichier -&gt; Exporter ''' et choisissez **Capture d'écran Sous...**.

2. Dans la fenêtre de dialogue qui s'ouvre, choisissez une “View” (Vue) - soit la vue MJ (GM view), où l'on peut tout voir, ou la vue Joueur (Player view), où seuls les éléments visibles par les *joueurs* seront exportés -.

3. Choisissez la destination du fichier en utilisant le bouton Parcourir (Browse...). Alternativement, vous pouvez l'envoyer vers un serveur FTP.

4. Cliquez **Export**.

Étapes Suivantes
----------------

Maintenant que vous savez comment créer une carte basique et y placer des pions, l'étape suivante est de vous connecter avec quelques amis via Internet (ou en face à face sur un réseau local) et utiliser tout cela pour une session de jeu !

Ce sujet est abordé dans [Introduction à l'hébergement de partie](Introduction_to_Game_Hosting "wikilink").

<Category:MapTool> <Category:Tutorial>