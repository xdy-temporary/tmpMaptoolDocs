.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{Languages|Introduction to Lights and Sights}}

**Note de traduction** : *Le blocage de vision s'exprime en anglais
Vision Blocking Layer, d'où l'acronyme VBL que vous pouvez croiser dans
les légendes des figures.*

.. _quest_ce_que_la_vision_et_la_lumière:

Qu'est-ce que la vision et la lumière ?
=======================================

MapTool offre trois fonctionnalités qui donnent corps à l'idée que quand
un personnage s'aventure dans un endroit, il n'est pas toujours
omniscient. Ainsi, il ne peut pas voir à travers les murs, au-delà des
angles ou dans les tréfonds d'obscurs donjons. S'il est difficile de le
simuler quand on joue face à face, c'est plus aisé avec un ordinateur.
En effet, il devient possible de restreindre la vision d'un personnage à
ce qu'il peut éventuellement voir, ce qui rend le jeu plus palpitant et
peut-être aussi plus immersif. Les trois fonctionnalités qu'offre
MapTool sont la **Vision**, la **Lumière** et le **brouillard de
guerre**.

.. _la_vision:

La vision
---------

La vision est la capacité d'un `pion <Token:token>`__ à «voir» les
alentours. Dans le cas présent, ce qu'un pion d'un joueur peut voir
devient visible pour le joueur sur son instance de MapTool. À noter que
si le MJ peut toujours tout voir sur la carte, les joueurs peuvent, eux,
être limités dans ce qu'il peuvent voir avec la `Barrière de
vision <Introduction_to_Vision_Blocking>`__, la lumière et `le
brouillard de guerre <Introduction_to_Fog_of_War>`__. Cela rend le jeu
plus immersif car les joueurs vont se dire : «Qu'est-ce qu'il y a
derrière cet angle ?», ou encore «Qu'il fait sombre dans ce donjon...
j'espère que ma torche va tenir !»

.. _la_lumière:

La lumière
----------

La lumière est ce qui permet aux pions et aux objets d'éclairer les
environs. Cela implique que, dans un donjon obscur, les torches des murs
peuvent illuminer quelques endroits de-ci de-là (découvrant ainsi
l'éventuel brouillard de guerre qui couvrirait la zone) qui seront donc
visibles par les joueurs. En d'autres termes, cela signifie que toute
zone illuminée devient visible aux joueurs à condition que son pion
dispose de la vue et qu'il n'y a pas de barrière de vision entre lui et
la zone.

La lumière est critique quand une carte se trouve en mode «vision de
nuit», puisqu'en l'absence de source de lumière, un pion est perdu dans
la nuit noire ! (Il ne se verra pas lui-même)

.. _brouillard_de_guerre:

Brouillard de guerre
--------------------

Le brouillard de guerre est un système qui révèle ce qu'un pion a vu
tout au long de ses mouvements ainsi que les parties de la carte qu'il
peut voir directement depuis là où il se trouve. Il **ne faut pas
confondre** le brouillard ne guerre avec l'obscurité. Vous pouvez
activer le brouillard de guerre sans pour autant avoir de lumières ni
même utiliser le mode de vision.

Quand un pion doté de vision «voit» dans une zone brumeuse, le
brouillard est dissipé et la carte est révélée. Quand une zone qu'un
pion a vue n'est plus directement visible, la brume se reforme de
manière moins épaisse : une couche semi-transparente recouvre la zone.
Cela permet au joueur de se rappeler qu'il est déjà passé par là, mais
qu'il ne peut pas la voir *en ce moment*. Tout pion présent dans une
zone ainsi recouverte est masqué comme s'il se trouvait dans le
brouillard le plus complet.

**Souvenez-vous** : *Le brouillard de guerre indique seulement quelles
parties de la carte ont déjà été vues par un pion.*

Le brouillard de guerre est un sujet à lui tout seul. Aussi, même s'il
est intimement lié à la vision et à la lumière, il mérite son propre
tutoriel. Allez voir `L'introduction au brouillard de
guerre <Introduction_to_Fog_of_War>`__ pour trouver des détails et des
captures d'écran sur l'utilisation du brouillard dans vos parties.

.. _le_donjon_pris_en_exemple:

Le donjon pris en exemple
=========================

.. figure:: samp-dungeon.png
   :alt: samp-dungeon.png

   samp-dungeon.png

Un donjon est pris en exemple pour l'ensemble des captures d'écrans qui
illustrent ce tutoriel (ainsi que dans l'\ `introduction à la barrière
de vision <Introduction_to_Vision_Blocking>`__). Une capture de ce
donjon se trouve à droite. Vous pouvez aussi télécharger le fichier de
campagne de ce donjon `here <here>`__.

.. _configuration_des_types_de_vision_et_de_sources_de_lumière:

Configuration des types de vision et de sources de lumière
==========================================================

Les types de vision et les types de sources de lumières peuvent être
configurés dans la fenêtre des Propriétés de la campagne. Pour l'ouvrir,
aller dans *Edition > Propriétés de la campagne*.

.. _types_de_vision:

Types de vision
---------------

.. figure:: cprops-sighttab.png
   :alt: cprops-sighttab.png

   cprops-sighttab.png

L'onglet de type de vision (*Sight en anglais*) vous permet de définir
plusieurs types de vues (comme la vision nocturne, la vision normale, la
vision dans le noir ou infrarouge, etc.). MapTool fournit quelques types
par défaut quand vous l'ouvrez pour la première fois. Si vous regardez
le contenu de l'onglet Vision, vous verrez ceci :

| ``Conic Vision: cone arc=120 ``
| ``Normal Vision - Short Range: circle distance=10.0 ``
| ``Lowlight: circle x2 ``
| ``Darkvision: circle r60 ``
| ``Square Vision: square ``
| ``Normal: circle ``

Chacun de ces éléments définit un '''type de vision '''. Il est défini
avec une syntaxe précise expliquée dans la fenêtre des Propriétés de la
campagne. Le plus simple consiste en une forme :

``Normal: circle``

Cela indique simplement que la vision «Normal» est circulaire. Il n'y a
aucune limite de portée exceptée celle définie dans les *propriétés de
la carte* (lors de la création et qui est, par défaut, de 1 000 unités).

Un second exemple un peu plus complexe est celui de la vision nocture
(«Lowlight» en anglais) :

``Lowlight: circle x2``

Dans ce cas, le nom du type de vision est **Lowlight** et elle est de
forme circulaire. Toutefois, une option supplémentaire a été ajoutée :
*x2*. Cette option interagit avec les *sources de lumière* et double
(multiplie par 2, x2) leur rayon effectif pour tout pion qui a pour
vision la « Lowlight vision ». Ainsi, si un pion avec la vision « Normal
» peut voir 20 unités avec une torche, un pion avec la vision « Lowlight
» en verra 40.

Compliquons encore un peu, regardons la vision dans le noir
(«Darkvision» en anglais) :

``Darkvision: circle r60``

Cette entrée a quatre paramètres :

-  **Darkvision**: c'est, bien sûr, le *nom* du type de vue. Vous
   pourriez très bien l'appeler «Vision thermique» si vous le
   souhaitiez). Ce nom apparaît dans la fenêtre de configuration du pion
   quand vous activez sa vision.
-  **circle**: cela signifie que la forme de la zone de vision est un
   cercle.
-  **r**: c'est un code qui indique que le pion dispose d'une source de
   lumière intrinsèque que lui et *lui seul* peut voir. Même ses alliés
   ne profiteront pas de cette zone de vision.
-  **60**: c'est la portée de la zone de lumière intrinsèque, exprimée
   en unité de carte depuis le centre du pion (si votre carte a 5 unités
   par cellule, vous couvrirez un peu moins de 12 cellules; si votre
   carte est de 1 unité par cellule, vous couvrirez un peu moins de 60
   cellules). Le *un peu moins* est dû au calcul de la zone qui
   s'effectue depuis le centre du pion. De nombreux utilisateurs ajouent
   une fractions afin que la vision s'achève proprement sur une
   frontière de cellule.

La configuration des types de vues est propre au jeu auquel vous jouez,
c'est pourquoi les détails sont laissés aux mains du concepteur de la
campagne. Cependant, vous pouvez simplement retenir que la vision est
paramétrable et vous offre une grande souplesse.

.. _limites_des_types_de_vues:

Limites des types de vues
~~~~~~~~~~~~~~~~~~~~~~~~~

Malgré sa souplesse, ce système connaît quelques limites.

-  **Un seul type de vue à la fois** : les pions ne peuvent avoir qu'un
   seul type de vue actif à un moment donné (un pion ne peut donc pas
   avoir à la fois la vision dans le noir et la vision normale d'activée
   en même temps).
-  **La vision est incolore**: les types de vision ne sont pas colorés.
   Toute les couleurs visibles par les joueurs dépendront de la couleur
   de la source de lumière et non du type de vision. Toutefois, il y a
   une exception : vous pouvez demander à ce que la couleur de la vision
   d'un pion soit celle de son `aura <token.halo>`__ dans les
   `Préférences de MapTool <MapTool_Preferences>`__ (*Use halo color for
   vision* dans l'onglet *Application*).

.. _sources_de_lumière:

Sources de lumière
------------------

.. figure:: Cprops-lighttab.png
   :alt: Cprops-lighttab.png

   Cprops-lighttab.png

L'onglet Lumières («Light» en anglais) fournit une interface similaire à
celle de l'onglet Vision : une boîte de saisie de texte avec une liste
de types auxquels sont associés des paramètres. La campagne par défaut
de MapTool fournit les sources de lumière suivantes :

| ``D20``
| ``----``
| ``Candle - 5 : 5 10#000000 ``
| ``Lamp - 15 : 15 30#000000 ``
| ``Torch - 20 : 20 40#000000 ``
| ``Everburning - 20 : 20 40#000000 ``
| ``Lantern, Hooded - 30 : 30 60#000000 ``
| ``Sunrod - 30 : 30 60#000000 ``
| ``Generic``
| ``----``
| ``5 : 5 ``
| ``15 : 15 ``
| ``20 : 20 ``
| ``30 : 30 ``
| ``40 : 40 ``
| ``60 : 60 ``

Groupes
~~~~~~~

Les types de sources de lumière fournis par défaut sont divisés en deux
groupes : « D20 » et « Generic ». Un groupe est défini par son nom qui
est placé sur la ligne précédent celle qui contient *uniquement* quatre
tirets (). Les groupes ainsi définis apparaissent dans le menu
contextuel d'un pion. C'est un moyen pour permettre au MJ d'organiser
les différentes sources de lumières pour votre partie.

.. _syntaxe_dune_source_de_lumière:

Syntaxe d'une source de lumière
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Au-dessous de chaque en-tête de groupe se trouvent une liste de sources
de lumière. Leur syntaxe est semblable à celle des types de vision, à
quelques exceptions près. Regardons le bâton luminescent («Sunrod» en
anglais) :

``Sunrod - 30: 30 60#000000``

Il y a trois éléments ici :

-  **Sunrod - 30** : le nom de la source de lumière tel qu'il appraît
   dans le menu contextuel du pion avec un clic droit, rangé sous la
   bonne catégorie dans le sous-menu Source de lumière («Light Source»).
-  **30**: la portée de la *première* zone d'éclairement, en unités de
   carte.
-  **60#000000** : la portée de la *deuxième* zone d'éclairement, avec
   son code couleur hexadécimal.

   -  **Rayons des sources de lumière** : une source de lumière peut
      avoir un ou plusieurs rayons d'éclairement. Chacun peut avoir une
      couleur différente. Dans le cas du bâton luminescent, le premier
      rayon n'a pas de couleur spécifiée, il prend donc celle par défaut
      : le blanc (qui indique que toute la zone est éclairée). Le
      deuxième rayon (60) est en noir (#000000), ce que MapTool traduira
      par une zone d'obscurité (gris d'opacité moyenne) de 30 à 60
      unités de carte. L'effet global obtenu est donc une lumière
      franche sur 30 unités puis une zone à demi voilée sur 30 unités de
      plus (les éléments y brillent moins, mais sont tout de même
      visibles).

Un élément est non précisé dans cet exemple : il s'agit de la *forme*
que prend la zone éclairée. Tout comme les types de visions, les sources
de lumière peuvent avoir une forme qui est, par défaut, circulaire. Les
autres possibilités sont :

-  **Cone**: crée un zone conique en fonction de là où regarde le pion.
   Le regard peut être défini par l'action «Set Facing» dans le menu
   contextuel du pion.
-  **Square**: crée une zone carrée autour du pion.
-  **Aura**: c'est un car particulier car ce n'est pas à proprement
   parler une source de lumière : elle n'éclaire pas, ne révèle pas les
   objets cachés et est bloquée par les barrières de vision. De plus,
   elle est colorée. C'est un moyen de représentée la portée de l'aura
   d'un personnage (par ex. une aura d'apaisement des émotions).

.. _conférer_la_vue_et_la_lumière_aux_objets_et_aux_pions:

Conférer la vue et la lumière aux objets et aux pions
-----------------------------------------------------

.. figure:: Token-config-sight.png
   :alt: Token-config-sight.png

   Token-config-sight.png

.. figure:: Token-config-light.png
   :alt: Token-config-light.png

   Token-config-light.png

Pour conférier la vue et une lumière à un pion, faites ce qui suit :

#. Double-cliquez sur le pion et allez dans l'onglet «Config». Là,
   cochez la case «Has Sight» et sélectonnez le type de vision
   approprié. Souvenez-vous qu'un pion ne peut avoir qu'une vision
   d'active à la fois.
#. Cliquez sur **OK** pour sauvegarder les paramètres.
#. Cliquez droit sur le pion et aller dans le sous-menu «Light Source».
   Naviguez dans les différents sous-menus jusqu'à trouver la source de
   lumière désirée. Cliquez dessus; le pion a désormais une source de
   lumière.

.. _modes_de_vision:

Modes de vision
===============

.. figure:: Map-vision-mode.png
   :alt: Map-vision-mode.png

   Map-vision-mode.png

Les versions récentes de MapTool ont introduit le concept de *mode de
vision* qui permet au MJ de définir comment la vision et la lumière
doivent être traitées sur la carte. Il y a trois modes possibles :
**Off**, **Day**, et **Night** (respectivement aucun, jour et nuit) et
chacun provoque un comportement différent.

Dans la présentation qui suit des modes de vision, ce qui est visible
par le joueur selon les mouvements de son pion est basé sur ce qui est
visible par son pion. Ainsi, si les circonstances permettent au pion du
joueur d'apercevoir un pion ennemi, le joueur verra le pion ennemi sur
la carte. Dans le cas contraire, il n'apparaîtra pas sur la carte du
joueur.

Off
---

Quand le mode de vision est «Off», les paramètres de gestion de la
vision sont purement et simplement ignorés. Tout est tout le temps
visible, sauf si le brouillard de guerre recouvre la zone.

Day
---

En mode «Day» (jour), les sources de lumière ne sont pas prises en
compte dans la détermination de la vue des pions. De plus, aucune partie
de la carte n'est masquée aux joueurs (ce qui signifie qu'ils voient la
carte dans son entièreté, mais pas nécessairement les pions qui se
trouvent sur la carte; ainsi ils voient toute la structure du donjon).
En fait, le mode jour estime qu'un puissant soleil éclaire tous les
points de la carte et que tout est visible sauf en cas de barrière de
vision ou de brouillard de guerre.

Night
-----

Ce mode prend en compte les sources de lumière dans la détermination de
la vue des pions, estimant qu'il fait nuit noire et que, sans source de
lumière, on n'y voit rien (cela inclut que les joueurs ne puissent pas
voir leurs propres pions). Si le brouillard de guerre est utilisé en
conjonction du mode de nuit, les sources de lumière le dissiperont
localement, à condition qu'un pion puisse apercevoir la source de
lumière et qu'il n'y a pas de barrière de vision.

.. _modes_de_vision_et_brouillard_de_guerre:

Modes de vision et brouillard de guerre
---------------------------------------

Vous pouvez utiliser le brouillard de guerre en conjonction de tous les
modes de vision.

-  Quand la vision est désactivée («Off»), le brouillard de guerre est
   dissipé jusqu'à la limite de vision du pion (défini dans la fenêtre
   de Propriétés du pion). Le brouillard de guerre ne devient pas
   semi-transparent dans ce mode, puisque les joueurs ne «voient» rien.
   Le blocage de vision fonctionne quant à lui normalement.
-  En mode de jour («Day»), le brouillard de guerre se dissipera jusqu'à
   la limite de la vision définie lors de la création de la carte (qui,
   par défaut, est de 1 000 unités). Le blocage de vision fonctionne
   normalement. Le brouillard de guerre peut être complet ou
   semi-transparent, vu que les pions «voient» par où ils passent.
-  En mode de nuit («Night»), le brouillard de guerre est dissipé
   jusqu'à la portée maximale de la source de lumière (souvenez-vous que
   : 1. le pion doit disposer de la vue; 2. doit avoir une source de
   lumière ou être dans une zone éclairée -- sans cela, un pion ne voit
   rien du tout !). Le brouillard peut devenir semi-transparent tout
   comme en mode de jour.

.. _utiliser_la_vision_et_la_lumière_en_jeu:

Utiliser la vision et la lumière en jeu
=======================================

La vision, la lumière et le brouillard intéragissent de nombreuses
façons en jeu. Pour commencer, utilisons la vision sans lumière ni
brouillard de guerre. Les exemples ci-dessous utilisent le donjon de
démonstration illustré à droite. Notez que ce donjon utilise le `blocage
de vision <Introduction_to_Vision_Blocking>`__, une fonctionnalité qui
permet à MapTool de bloquer la ligne de vue d'un pion (ce qui permet
d'indiquer l'emplacement des murs, des piliers ou d'autres objets qui
obstruent le champ de vision).

.. _portée_de_la_vision:

Portée de la vision
-------------------

.. figure:: Nofog-sight-boundary.png
   :alt: Nofog-sight-boundary.png

   Nofog-sight-boundary.png

|Nofog-sight-boundvbl.png|, la limite du champ de vision du pion suit
les VBL.]]

Si vous avez conféré la vue à un pion, lorsque vous survolez celui-ci
avec votre souris, MapTool dessinera les contours de son champ de vision
avec une ligne blanche (un cercle si la vue est circulaire, un carré ou
un cône sinon). La capture d'écran ci-contre montre un pion d'un joueur
avec la vision «Normal - Short Range». Notez bien le cercle blanc qui
indique les limites du champ de vision.

Sur la première capture, il n'y a pas de blocage de vision sur la carte,
donc le pion peut tout voir. Pour une illustration plus réaliste de la
limite du champ de vision, regardez la deuxième capture prise avec le
même pion mais avec la présence de blocage de vision le long des murs du
donjon. Si vous regardez bien, vous verrez que la limite du champ de
vision est toujours dessinée en blanc, mais au lieu d'être circulaire,
elle est bloquée par les zones de blocage de vision positionnées sur la
carte, d'où sa forme irrégulière.

.. _modes_de_vision_et_vue:

Modes de vision et vue
======================

Comme expliqué tantôt, il y a trois modes de vision : '''Offf', **Day**
et **Night**. Chaque mode modifie le comportement de MapTool.

.. _mode_de_vision_off:

Mode de vision "Off"
--------------------

.. figure:: Nofog-visionoff-gmview.png
   :alt: Nofog-visionoff-gmview.png

   Nofog-visionoff-gmview.png

.. figure:: Nofog-visionoff-plyrview.png
   :alt: Nofog-visionoff-plyrview.png

   Nofog-visionoff-plyrview.png

Quand la vision est désactivée, la vue d'un pion n'est pas prise en
compte pour déterminer le champ de vision. Le joueur peut donc tout
voir. Le blocage de vision bloquera toujours le champ de vision du pion,
mais le joueur verra tout de même l'intégralité des choses.

Les deux captures d'écran illustrent respectivement la vue du MJ et
celle du joueur. Notez que les seuls objets qui ne sont pas visibles par
le joueur sont ceux qui sont placés sur la couche cachée de la carte
(«Hidden layer») ou que le MJ a coché comme invisible pour les joueurs.

.. _mode_de_vision_day:

Mode de vision "Day"
--------------------

.. figure:: Nofog-visionday-gmview.png
   :alt: Nofog-visionday-gmview.png

   Nofog-visionday-gmview.png

.. figure:: Nofog-visionday-plyrview.png
   :alt: Nofog-visionday-plyrview.png

   Nofog-visionday-plyrview.png

En mode de vision de jour, les paramètres de vue sont pris en compte
pour savoir ce qu'un pion peut et ne peut pas voir. Les sources de
lumières *ne sont pas* prises en considération. Si un objet ou un pion
est hors du champ de vision d'un pion, il ne sera pas visible par le
joueur. De la même manière, si un objet est masqué par un blocage de
vision, il ne sera pas visible.

Les deux captures illustrent cela (MJ en haut, joueur en bas). Notez que
le joueur (l'elfe) ne voit pas le dragon ni le héros car il y a un
blocage de vision entre eux.

.. _mode_de_vision_night:

Mode de vision "Night"
----------------------

.. figure:: Nofog-visionnight-gmview.png
   :alt: Nofog-visionnight-gmview.png

   Nofog-visionnight-gmview.png

.. figure:: Nofog-visionnight-plyrview.png
   :alt: Nofog-visionnight-plyrview.png

   Nofog-visionnight-plyrview.png

.. figure:: Nofog-visionnight-plyrview-candle.png
   :alt: Nofog-visionnight-plyrview-candle.png

   Nofog-visionnight-plyrview-candle.png

En mode de vision de nuit, la source de lumière d'un pion est conjuguée
à sa capacité de vision pour définir son champ de vision. Si un pion n'a
pas de source de lumière à portée, il sera caché, sauf s'il dispose
d'une source de lumière personnelle (voir la vision dans le noir
ci-haut). Le pion ne sera donc même pas visible par le joueur !

Les captures ci-contre illustrent cela. Vue MJ; vue joueur sans lumière;
vue joueur avec la source de lumière «Candle - 5». Il y a quelques
points d'attention :

#. Le mode de vision de nuit ne crée pas d'effet visuel d'obscurité. Il
   signifie simplement qu'à défaut de source de lumière, personne ne
   verra rien.
#. Dans la première vue joueur, le pion de l'elfe n'est pas visible dans
   le coin inférieur gauche du donjon car il n'a pas de source de
   lumière, donc ne voit rien, donc le joueur non plus ne voit rien, pas
   même son pion. Il voit uniquement l'arrière-plan de la carte.
#. Dans la deuxième vue joueur, l'elfe est visible car il possède une
   source de lumière. Cette source permet au joueur de voir jusqu'à la
   limite du champ de vision de son pion.

.. raw:: mediawiki

   {{Languages|Introduction to Lights and Sights}}

{{#customtitle:Introduction aux lumières et à la vision|Introduction aux
lumières et à la vision}}

`Category:MapTool <Category:MapTool>`__
`Category:Tutorial <Category:Tutorial>`__

.. |Nofog-sight-boundvbl.png| image:: Nofog-sight-boundvbl.png
