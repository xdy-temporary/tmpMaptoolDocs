.. contents::
   :depth: 3
..

.. _introduction_à_la_gestion_des_pions:

Introduction à la gestion des pions
===================================

Comme il est spécifié dans le guide `Introduction à la création de
carte <Introduction_to_Mapping/fr>`__, Un `pion <Macros:Glossary#P>`__
(token) est dans le jargon de MapTool un marqueur visuel placée sur une
carte par l'intermédiaire du logiciel. L'utilisation la plus intuitive
pour les pions est de leur faire représenter les personnages dans le jeu
- en d'autres termes, les pions remplacent les figurines sur la table de
jeu virtuelle.

.. _pré_requis:

Pré-requis
----------

Ce guide suppose que vous avez déjà lu la partie `Introduction à la
création de carte <Introduction_to_Mapping/fr>`__, et que vous savez
comment :

-  Ajouter un répertoire à votre bibliothèque de ressources, mettre à
   jour/ajouter des images dans ces répertoires pour qu'ils apparaissent
   dans votre bibliothèque de ressources.
-  Créer une carte dans MapTool.
-  Placer des Pions (Token) sur une carte et les faire bouger.
-  Modifier le nom, le nom MJ et le label d'un Pion.
-  Modifier la taille d'un pion.
-  Changer l'image d'un pion.
-  Déplacer les pions d'une carte vers une autre.

Si vous ignorez comment faire ces choses, veuillez lire la section
`Introduction à la création de carte <Introduction_to_Mapping/fr>`__ -
sinon les informations qui suivent pourraient bien n'avoir aucun sens
pour vous.

Enfin, ce guide est principalement dédié au Maître de Jeu (celui qui a
le contrôle complet sur tous les pions et les propriétés de la
campagne). Les possibilités de modifications des joueurs (ceux qui
rejoignent la partie avec le rôle "Player") sont limitées pour tout ce
qui se rapporte à la campagne en cours.

.. _les_différents_calques:

Les différents calques
----------------------

Bien que la plupart des utilisateurs utilisent le terme "pion" ou
"token" pour parler des images représentants les personnages et les
monstres sur une carte, en réalité, cela peut s'appliquer à n'importe
quel objet image déposé sur la carte. La manière dont un pion sera géré
dépend du calque de carte sur lequel il est situé. Ces calques sont
expliqués plus bas, car ils sont importants pour la compréhension du
fonctionnement des pions.

-  Les objets déposés sur le calque **Token** sont ce que nous appelons
   communément les *pions* - ils représentent les personnages, les
   monstres et les PNJ - les gens et les créatures du jeu.
-  Les objets déposés sur le calque **Object** sont des images de
   matériels divers, coffres et autres "choses" dans le monde du jeu -
   quelque chose que les créatures peuvent manipuler ou utiliser.
   MapTool les considèrera toujours comme des pions (en fait, n'importe
   quoi est un pion dans l'esprit étroit de MapTool) mais pour plus de
   clarté, la plupart des utilisateurs les appellent *Objets* pour les
   distinguer des pions représentant les *personnages*.
-  Les objets déposés sur le calque **Background** représentent ce qui
   fait le fond de la carte - murs, falaises, boue, herbe. Ils peuvent
   être uniques, mais sont plus souvent tamponnés un peu partout sur la
   carte soit à l'intérieur d'un dessin ou parce que vous utilisez
   plusieurs copies de la même image ( par exemple, utiliser plusieurs
   copies d'un mur permet de créer une pièce entière). A cause de cela,
   de nombreux utilisateurs appellent ces images des *tampons*.

.. _le_calque_caché_hidden:

Le calque caché (Hidden)
~~~~~~~~~~~~~~~~~~~~~~~~

Vous aurez remarqué que le calque **caché** n'a pas été abordé au
paragraphe précédent. C'est à cause de son utilité quelque peu
différente.

Alors que les calques Token, Object, et Background ont une utilisation
très naturelle dans la manière de concevoir le monde -- je suis une
*personne ou une créature*, cet chose là est un *objet*, et nous sommes
entourés par cet *arrière-plan* -- le calque Hidden représente tout ce
que vous *ne pouvez pas voir*. Dans MapTool, tout ce qui est placé sur
ce calque sera visible seulement pour le MJ, jusqu'à ce qu'il décide de
le déplacer vers un autre calque.

Généralement, vous voudrez placer des personnages et des objets sur ce
calque - il n'y a pas beaucoup de raisons de placer un élément de
l'arrière-plan sur le calque caché, bien que je suis sûr que vous
trouverez bien deux ou trois bonnes raisons.

Tout cela suffit pour dire que lorsque vous placez un pion sur une carte
de MapTool, cela rapporte toujours de savoir sur quel calque vous l'avez
mis !

.. _création_dun_nouveau_pion:

Création d'un nouveau Pion
==========================

Créer un nouveau pion est aussi simple que déposer une image depuis
votre bibliothèque de ressource sur le calque Token de votre carte (vous
pouvez aussi le faire directement depuis l'explorateur Windows).
Cependant comment créer d'abord une image adaptée? Il y a plusieurs
options.

.. _télécharger_une_image:

Télécharger une Image
---------------------

La communauté d'utilisateur de MapTool a créé une grande quantité
d'images de pions disponible pour votre usage. Allez sur le site
`RPTools Gallery <http://gallery.rptools.net>`__ pour voir les centaines
d'images de pions déjà téléchargeables.

.. _créer_un_pion_via_tokentool:

Créer un pion via TokenTool
---------------------------

Une autre manière de faire consiste à utiliser
`TokenTool <http://www.rptools.net/index.php?page=tokentool>`__, un
programme réalisé par les concepteurs de MapTool pour créer vos propres
images de pions rapidement et facilement. Pour cela :

1. Télécharger TokenTool et lancez-le en double-cliquant sur le fichier
comportant l'extension **.jar** (il s'agit d'un fichier "JAR" exécutable
qui fonctionne avec l'environnement java).

2. Trouvez une image qui vous convient (attention aux droits d'auteur)
et déposez la sur le panneau de gauche de le fenêtre de TokenTool (la
partie avec un petit anneau et un fond noir).

3. Quand l'image apparaît, cliquez en maintenant le bouton gauche
enfoncé sur votre image puis déplacez la de façon à faire apparaître
votre pion à l'intérieur de l'anneau. Vous pouvez avoir un aperçu de ce
à quoi votre pion ressemblera dans le coin supérieur droit de la fenêtre
TokenTool.

-  **Astuce**: Vous pouvez utiliser la molette de votre souris ou les
   boutons de zoom pour ajuster la taille de votre image jusqu'à ce
   qu'elle ait l'aspect désiré.
-  **Astuce**: Vous pouvez changer l'aspect, la couleur de la bordure,
   la taille finale de votre pion et beaucoup d'autres options en
   utilisant les menus déroulant à droite de la fenêtre TokenTool.

4. Lorsque vous êtes satisfait du résultat, allez dans **File > Save
Token**, et sauvegardez le pion ainsi créé, soit directement dans le
répertoire de votre bibliothèque de ressources, soit dans un répertoire
que vous avez prévu d'ajouter ultérieurement à celle-ci. Notez bien que
le fichier sera sauvegardé au format PNG (ce qui est une bonne chose,
puisque ce format gère la transparence ! Ainsi votre pion ne débordera
pas du cadre).

5. Retournez dans Maptool pour mettre à jour votre bibliothèque de
ressources et vous pourrez voir votre nouveau pion ! Déposez le sur la
carte et vous serez prêt à commencer.

.. _dessinez_votre_pion_vous_même:

Dessinez votre pion vous-même
-----------------------------

Vous pouvez créer une image de pion en utilisant un logiciel de dessin
et en sauvegardant le fichier au format PNG ou JPG, dans le répertoire
de votre bibliothèque de ressources ou à un autre endroit. Le format PNG
est recommandé pour les pions car il gère la transparence et présente un
meilleur aspect.

Vous pouvez aussi combiner vos propres création avec TokenTool pour
obtenir de superbe pion au format approprié.

.. _modifier_un_pion:

Modifier un Pion
================

Modifier un pion signifie changer n'importe laquelle des
caractéristiques d'un pion, que cela soit son image, ses noms ou ses
paramètres de configuration. Modifier les noms, image et taille d'un
pion sont expliqués dans `Introduction à la création de
carte <Introduction_to_Mapping>`__.

La section suivante traite des différentes options, onglets et listes
déroulantes dans la fenêtre **Edit Token**.

.. _type_de_pion:

Type de pion
------------

Les pions sont de deux types possibles dans MapTool : PC (PJ) et NPC
(PNJ). Les joueurs de jeux de rôles sont déjà familiers avec ceux-ci car
ils signifient "Personnage Joueur" et "Personnage Non Joueur", et
l'usage le plus courrant pour ces deux types est pour faire la
distinction entre les deux groupes au cours d'une partie.

En général, les pions qui appartiennent à *vos joueurs* ont le type
"PC". Ceux qui *vous* appartiennent devraient avoir le type "NPC".

.. figure:: Edit-token.jpg
   :alt: Edit-token.jpg

   Edit-token.jpg

**Remarque**: Le *type* d'un pion n'a rien à voir avec qui peut
manipuler ce pion ou voir ses propriétés - à l'inverse, ce pouvoir est
conféré au *owner* (propriétaire) ou *owners* (propriétaires) du pion.
En tant que MJ, on considère que vous avez autorité sur tous les pions
de la campagne. Voir la section
`Appartenance <Introduction_to_Tokens/fr#Appartenance>`__, plus bas,
pour plus d'information.

Pour changer le type d'un Pion :

1. Double-cliquez sur le Pion pour ouvrir la boite de dialogue **Edit
Token**.

2. Dans le coin supérieur droit, utiliser le menu déroulant pour choisir
**Pc** (PJ) ou **Npc** (PNJ).

3. Cliquez sur **OK**.

Notes
-----

.. figure:: Notes-tab.jpg
   :alt: Notes-tab.jpg

   Notes-tab.jpg

L'onglet Notes présente deux zones de texte dans lesquelles vous pouvez
saisir des remarques à propos du Pion. Ces champs acceptent les balises
HTML de base, ainsi vous pouvez mettre ces remarques au format désiré
(voir ce site sur les `Balises
HTML <http://starshoot.chez.com/html/listbalises.htm>`__ pour plus de
détails sur le sujet).

La partie supérieure est consacrée aux notes générales accessible à
tous. La partie inférieure (intitulée **GM Notes**) concerne les notes
que seul le MJ peut consulter.

Les Notes sont assez compliquées à utiliser - MapTool dispose d'un
mécanisme pour les afficher dans une jolie bulle, mais pour cela, vous
avez deux ou trois trucs à faire avant :

#. Saisissez les informations dans le champ notes du Pion.
#. Placez le Pion sur le calque **Object** ou **Background**
#. En faisant un clic droit sur le Pion puis en sélectionnant **Change
   To >**, Ramenez le sur le calque **Token**

Maintenant, vous pouvez remarquer que lorsque vous placez le curseur de
votre souris au dessus de votre Pion, le curseur se transforme en main.
Si vous double-cliquez dessus, au lieu de l'habituelle boite de dialogue
**Edit Token**, vous pouvez admirer une petite bulle dans le coin
inférieur gauche de la carte qui affiche vos remarques.

La principale leçon est que -- alors que vous pouvez accéder aux
remarques concernant le Pion de différentes manières -- un des usages
les plus courant est de placer des notes ou des penses-bêtes sur les
Pions et Objets qui se trouveront sur les calques "Object" ou
"Background".

Propriétés
----------

.. figure:: Properties-tab.jpg
   :alt: Properties-tab.jpg

   Properties-tab.jpg

Comme les **Propriétés** sont fortement liées à la création et à
l'utilisation des Macros des Pions, elles repésentent un sujet à part
entière et disposent d'un guide complet. Cette section ne rentrera donc
pas profondément dans le détail, mais présentera par contre les
informations élémentaires sur le sujet.

N'importe quel Pion déposé sur le calque *Token* d'une carte MapTool
gagne automatiquement un ensemble de **propriétés**, qui peut
typiquement être des valeurs, des caractéristiques ou des attributs
(vous savez les chiffres sur une feuille de personnage). En effet,
chaque Pion emporte avec lui sa feuille de personnage intégrée. En
langage de programmation, les propriétés peuvent être assimilées à des
variables qui peuvent être de différents types et utilisées
ultérieurement par des Macros.

-  '''Remarque: bien que la plupart des gens se réfèrent aux propriétés
   du Pion, les propriétés visibles dans la fenêtre de dialogue "Edit
   Token" concernent uniquement les propriétés qui ont été établies pour
   la campagne en cours.

Quand vous cliquez sur l'onglet **Macros** dans la fenêtre de dialogue
"Edit Token", vous voyez une liste de propriétés actuellement utilisées
dans la campagne. Si vous ouvrez une nouvelle campagne (ou simplement si
vous démarrez MapTool), vous aurez les *propriétés par défaut*, ce qui
ressemble à :

-  Strength
-  Dexterity
-  Constitution
-  Intelligence
-  Wisdom
-  Charisma
-  HP
-  AC
-  Defense
-  Movement
-  Elevation
-  Description

Pour la suite, les exemples fournis utiliseront les propriétés de la
liste précédente.

La liste de propriété que vous voyez se trouve dans une table, avec le
nom de la propriété à gauche, et une case vide à droite. Dans cet
espace, vous pouvez saisir les valeurs que vous souhaitez attribuer à
une propriété. Vous pouvez saisir du texte, des nombres et dans certains
cas plus complexes, des résultats de macros à la place d'une propriété
particulière.

Une fois que vous avez cliqué sur **OK**, cette propriété se verra
attribuer - pour le Pion en question - la valeur que vous avez saisie.
Plus tard, si vous écrivez des macros, vous pourrez vous référer à ces
propriétés pour réaliser vos calculs ou jets de dés.

Puisque les propriétés représentent un sujet majeur à elles toutes
seules, consultez le guide `Introduction aux
Propriétés <Introduction_to_Properties/fr>`__ pour plus d'information.

État
----

.. figure:: State-tab.jpg
   :alt: State-tab.jpg

   State-tab.jpg

.. figure:: State-example.jpg
   :alt: State-example.jpg

   State-example.jpg

L\ **'État** est un marqueur visuel qui peut être appliqué à un Pion
(typiquement en apparaissant en surimpression sur l'image d'un Pion) qui
peut être utilisé comme une sorte de d'indicateur dont vous pourriez
avoir besoin en cours de jeu. Par exemple, si vous souhaitez un marqueur
pour vous indiquer qu'un Pion de PNJ est mort, vous pouvez lui appliquer
l'État "Dead", et quelle que soit l'image que vous avez choisie pour
indiquer la mort, elle apparaîtra sur le Pion.

Les États chargés par défaut lorsque vous lancez MapTool sont :

-  Dead
-  Disabled
-  Hidden
-  Prone
-  Incapacitated
-  Other
-  Other 2
-  Other 3
-  Other 4

| 

.. _barre_de_santé:

Barre de santé
~~~~~~~~~~~~~~

.. figure:: Bar-example.jpg
   :alt: Bar-example.jpg

   Bar-example.jpg

L'onglet Etat contient aussi des informations pour les **barres** que
les Pions affichent ou peuvent afficher. Ces barres s'affichent en
surimpression sur l'image du Pion (au dessus, en dessous ou sur le
côté), et peuvent être utilisées pour afficher des informations comme la
santé (ou les munitions, la magie, ou tout ce qui peut être perdu ou
dépensé).

| 

Macros
------

Obsolète depuis la version 1.3.b54, l'onglet Macro n'est plus activé. Il
contenait à l'origine toutes les macros associées au Pion, mais avec la
montée en puissance des capacités des macros, cet onglet est devenu de
plus en plus inutile, jusqu'à ce qu'il soit enfin retiré. Il reste
présent dans les versions précédentes, alors si vous voulez y jeter un
œil...

Dialogues
---------

.. figure:: Speech-tab.jpg
   :alt: Speech-tab.jpg

   Speech-tab.jpg

Cet onglet contient la liste des dialogues pré-enregistrés du Pion
sélectionné. Vous pouvez l'utiliser pour configurer des phrases, des
aphorismes, des cris de batailles ou tout ce que vous pourriez vouloir
faire dire à un Pion au cours d'un Chat. Il est composé de deux champs
pour chaque objet dialogue :

-  **ID**: Ce champ est un identifiant court pour le dialogue. L'ID est
   utilisé en chat en référence au texte complet du dialogue. Cela peut
   être composé de caractères alphanumériques, aussi vous pouvez
   utiliser une combinaison de chiffres et de lettres. Toutefois, il ne
   peut pas contenir d'espace !
-  **Speech Text**: Il s'agit du texte qui sera affiché dans la fenêtre
   de Chat en résultat de votre commande.

Pour utiliser un objet dialogue, procéder comme suit :

#. Selectionnez le Pion à qui vous voulez faire "dire" quelque chose.
#. Dans la fenêtre de Chat, saisissez **/tsay ID**, ou ID est remplacé
   par l'identifiant correspondant au dialogue souhaité. Ainsi si vous
   désirez que votre Pion hurle "Mort aux gobelins unijambistes !!!", il
   faudra qu'au préalable, vous ayez saisis dans la fenêtre **Speech**,
   un *ID* (par exemple :hurle1) et le *Speech Text* souhaité. Ensuite,
   dans la fenêtre de Chat, saisissez **/tsay hurle1** et tout le monde
   comprendra que vous avez une vieille rancœur à l'égard de cette
   catégorie de créatures.

Appartenance
------------

.. figure:: Ownership-tab.jpg
   :alt: Ownership-tab.jpg

   Ownership-tab.jpg

L'appartenance d'un Pion (**ownership**) décide qui parmi les joueurs
`connectés à la partie <Introduction_to_Game_Hosting/fr>`__ est autorisé
à sélectionner, déplacer ou afficher les informations détaillées d'un
Pion donné.

Si vous êtes le **propriétaire** d'un Pion, vous pouvez le sélectionner,
double-cliquer dessus pour l'ouvrir et l'éditer, le déplacer sur la
carte. Si vous n'êtes pas le propriétaire d'un pion, vous serez limités
à observer ses mouvement sur la carte et les informations que le
propriétaire aura rendues publiques -- vous ne pourrez pas le
sélectionner, le déplacer ni voir ses propriétés ou sa configuration.

Pour attribuer un propriétaire, ouvrez l'onglet **ownership** et cocher
simplement la case à côté du nom de son nouveau propriétaire. Les noms
affichés correspondent aux noms de chaque joueur (y compris celui du MJ)
connecté à la partie. Les Pions se "souviennent" du nom de leur
précédent propriétaire aussi si vous avez récupéré le Pion via Internet,
pensez à mettre à jour son appartenance.

Si vous souhaitez que le Pion soit accessible à plusieurs joueurs, vous
pouvez cocher plusieurs noms. Si vous souhaitez que tout le monde puisse
y accéder, cochez simplement la case **All Players**.

Configuration
-------------

.. figure:: Config-tab.jpg
   :alt: Config-tab.jpg

   Config-tab.jpg

Cet onglet contient un certain nombre de réglages qui affecte
l'apparence, les mouvements et les interactions d'un Pion avec MapTool.

.. _forme_shape:

Forme (Shape)
~~~~~~~~~~~~~

Les Pions peuvent avoir trois types de forme dans MapTool :

-  **Top Down**: habituellement dessiné à la main ou créé par logiciel
   d'infographie, ils montrent des créatures, des objets ou des
   personnages comme si vous les regardiez de dessus. Choisir ce réglage
   autorise le Pion à être utilisé comme une figurine et à être tourné
   lorsque vous faites un clic-droit dessus et que vous choisissez
   **Change Facing** (de cette manière, votre figurine peut se tourner
   et faire face à ses ennemis).
-  **Circle**: Les Pions circulaires ressemblent aux jetons de poker -
   le cercle avec l'image représente une créature ou un personnage.
   Parce qu'il n'ont pas vocation à avoir un aspect réaliste, quand vous
   utilisez *Change Facing*, au lieu de tournez l'image - ce qui serait
   moche - une petite flêche jaune apparaît pour indiquer la direction à
   laquelle le pion fait face.
-  **Square**: Les Pions carré fonctionnent comme les Pions circulaires
   sauf qu'ils sont ... carrés.

   **Remarque :**\ Quelle que soit la forme et l'apparence de votre
   Pion, vous pouvez appliquer n'importe quel type des trois formes
   possibles.

.. _taille_size:

Taille (Size)
~~~~~~~~~~~~~

Un Pion peut se voir attribuer une taille, ce qui le fera grossir ou
rapetisser.

Les tailles disponibles dépendent de la grille de la carte que vous avez
`réglée <Introduction_to_Mapping>`__ et sur laquelle le Pion se trouve.
Si vous avez choisi une carte avec une grille (hexagonale ou carrée),
vous aurez quand même l'option **Free Size** (ou taille libre qui vous
permet de choisir la taille que vous voulez pour votre Pion) ou parmi
certaines tailles allant de Minuscule (Fine) à Colossal (Colossal) (Si
vous jouez à D&D, elles vous sont probablement déjà familière).

Si vous n'avez pas mis de grille quand vous avez créé la carte, vous
pourrez choisir un facteur d'échelle allant de -11 à +20.

.. _propriétés_properties:

Propriétés (Properties)
~~~~~~~~~~~~~~~~~~~~~~~

Ce champ vous permet de choisir parmi les jeux de propriétés disponibles
pour votre campagne auquel votre Pion se rapporte. Le concepteur de la
campagne peut développer plusieurs jeux différents pour être utilisés
par des Pions différents (par exemple un jeu pour les PJ, un pour les
PNJ). Ce menu déroulant vous permet de choisir lequel vous voulez
utiliser.

Vision
~~~~~~

Ce champ vous permet de choisir le type de
`vision <Introduction_to_Lights_and_Sights>`__ le Pion possède. Les
différents réglages de la **vision** autorisent le MJ à simuler
l'obscurité, la lumière, les objets cachés et les ennemis camouflés.

.. _coller_à_la_grille_snap_to_grid:

Coller à la grille (Snap to Grid)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Cette case à cocher indique simplement si le Pion doit coller à la
grille existante lorsqu'il est déplacé. Cette case décochée, le Pion ne
tiendra pas compte de la grille lorsqu'il sera déplacé sur la carte.

.. _visible_pour_les_joueurs_visible_to_players:

Visible pour les Joueurs (Visible to Players)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Cette case à cocher vous permet de rendre un Pion invisible au joueur -
lorsqu'elle est cochée, aucun joueur connecté ne peut voir ou interagir
avec d'une quelconque manière.

.. _disposition_portrait_et_présentation_layout_portrait_and_handout:

Disposition, Portrait et Présentation (Layout, Portrait and Handout)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Ces trois espaces traitent de l'apparence visuelle du Pion :

-  **Layout**: Montre comment le Pion apparaîtra sur la carte. Vous
   pouvez agir dessus pour ajuster l'image à la grille (position et
   taille).
-  **Portrait**: Il s'agit d'une image séparée qui apparaît dans le coin
   gauche de la carte quand vous passez la souris au dessus du Pion.
-  **Handout**: Vous permet d'afficher une autre image qui apparaît
   lorsque vous faites un clic-droit sur le Pion et que vous choisissez
   **Show Handout**.

{{#customtitle:Introduction à la gestion des pions|Introduction à la
gestion des pions}}

`Category:MapTool <Category:MapTool>`__
