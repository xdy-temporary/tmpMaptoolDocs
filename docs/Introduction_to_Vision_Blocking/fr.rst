.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{Languages|Introduction to Vision Blocking}}

.. raw:: mediawiki

   {{Translation}}

**Note de traduction** : *Le blocage de vision, ou obstruction,
s'exprime en anglais Vision Blocking Layer, d'où l'acronyme VBL qui est
utilisé. Vous pourrez croiser la traduction «calque de blocage de
vision» (CBL). Toutefois, comme les forums sont majoritairement en
anglais, l'acroynme VBL est utilisé dans cet article.*

.. _blocage_de_vision:

Blocage de vision
=================

Dans MapTool, les `pions <Token:token>`__ peuvent disposer de la
`vue <Introduction_to_Lights_and_Sights>`__, ce qui laisse le soin au
logiciel de modéliser l'éclairement et la vision durant la partie. En
d'autres mots, quand vous configurez la vision d'un pion, il peut «voir»
les autres pions qui se trouvent sur la carte. De plus, MapTool gère
l'\ `éclairage <Introduction_to_Lights_and_Sights>`__, ce qui permet de
restreindre la portée de la vue d'un pion, et le blocage de vision qui
permet de définir des obstructions (afin de matérialiser les murs d'un
donjon, par exemple).

Ce tutoriel expliquera l'essentiel du système de blocage de vision de
MapTool et comment utiliser ses outils (quelques fois appelés *outils de
topologie*) dans le cadre d'un donjon type. Rappelez vous que
l'obstruction de vision est intimement liée à la **vue**,
**l'éclairage** et au **brouillard de guerre**, donc n'hésitez pas à
vous référer à l'\ `introduction aux lumières et à la
vision <Introduction_to_Lights_and_Sights>`__ pour voir comment tout
cela intéragit !

.. _avant_tout_munissez_vous_dune_carte:

Avant tout, munissez-vous d'une carte
-------------------------------------

.. figure:: samp-dungeon.png
   :alt: samp-dungeon.png

   samp-dungeon.png

Pour commencer, nous avons besoin de la carte d'un donjon, de préférence
sombre et humide, plein de recoins et tout le reste.

Enfin, on ne va pas se prendre la tête avec un vrai dédale. Conçue à
l'aide d'un `remarquable ensemble de
textures <http://forums.rptools.net/viewtopic.php?f=34&t=7418>`__ créé
par Jonathan Roberts (Torstan sur les `forums
RPTools <http://forums.rptools.net>`__), la carte située à droite sera
utilisée pour nos exemples.

.. _activer_les_outils_de_blocage_de_vision_vbl:

Activer les outils de blocage de vision (VBL)
=============================================

.. figure:: Vbl-toolbar-btn.png
   :alt: Vbl-toolbar-btn.png

   Vbl-toolbar-btn.png

.. figure:: Vbl-tools.png
   :alt: Vbl-tools.png

   Vbl-tools.png

Pour accéder aux outils de blocage de vision (VBL), cliquez sur l'icone
en forme «d'œil» dans la barre d'outils de MapTool (cf. capture d'écran
de l'œil). C'est alors qu'un nouvel ensemble de boutons va apparaître :
ce sont les outils de blocage de vision que vous pouvez utiliser. Si
vous laissez votre pointeur de souris au-dessus, une légende apparaîtra.
De gauche à droite, vous trouvez :

-  **Dessiner une VBL en rectangle plein**: cela crée une zone
   rectangulaire pleine qui bloque la vision. Les pions qui se trouvent
   à l'extérieur de la zone ne peuvent pas voir ce qui se trouve dedans,
   ni à travers; les pions qui se trouvent dedans ne voient rien du tout
   : c'est solide et opaque.
-  **Dessiner une VBL en rectangle creux**: cela crée un rectangle
   creux. Si un pion se trouve *à l'intérieur*, ils verront tout ce qui
   se trouve à l'intérieur, mais ne pourront pas voir *au-delà* des
   bordures. Un pion qui se trouve à l'extérieur ne peut pas voir ce qui
   se trouve à l'intérieur du rectangle.
-  **Dessiner une VBL en ovale plein**: identique au rectangle, sauf que
   c'est un cercle (en réalité, c'est un polygone qui se rapproche d'une
   cercle, car un véritable cercle requiert trop de ressources).
-  **Dessiner une VBL en ovale creux**: identique au rectangle, sauf que
   c'est... un cercle creux.
-  **Dessiner une VBL en polygone fermé plein**: cela vous permet de
   dessiner un polygone face par face et le rempli quand vous avez fini;
   bien sûr en créant un VBL. Pour débuter le polygone, cliquez gauche
   sur la carte et tracer la première face. Pour y attacher une autre
   face, *cliquez droit* et bougez votre souris. Pour finaliser la
   forme, cliquez gauche.
-  **Dessiner une VBL en polygone fermé creux**: identique au polygone
   plein, sauf qu'il est creux.

.. _bonnes_pratiques:

Bonnes pratiques
----------------

Les processus de blocage de vision et de détermination de la vision
requierent une utilisation intensive du processeur. Aussi, une
surutilisation de ce système ou de formes particulièrement complexes
peuvent causer de très mauvaises performances de MapTool
(ralentissement, impossibilité de parcourir la carte, etc.). Quelques
règles de base :

#. **Utilisez des rectangle autant que faire ce peut** - et évitez les
   zone circulaires et polygonales.
#. **Utilisez les formes pleines autant que possible** - cela évite les
   interstices entre les faces de polygones, qui peuvent être de
   véritables fléaux en terme de performance. Couvrez plutôt la carte
   avec un grand rectangle VBL et puis découpez à l'intérieur les zones
   que les pions peuvent observer.
#. **Utilisez-en le moins possible pour obtenir l'effet désiré** -
   optimisez, soyez efficients !
#. Il est aussi avisé de définir une frontière de vision sur les bords
   de la carte sur laquelle vous jouez, car les cartes dans MapTool sont
   potentiellement inifinies et il serait inutile que MapTool calcule
   les paramètres de vision en-dehors de l'espace où vous jouez.

Cela évitera d'écrouler les performances. Bien sûr, vous *pouvez*
utiliser les autres types de VBL, mais soyez conscients de la complexité
que vous introduisez.

.. _ajouter_les_vbl_sur_la_carte:

Ajouter les VBL sur la carte
============================

Nous pouvons maintenant ajouter le blocage de vision sur notre carte.
Nous allons utiliser la technique recommandée, c'est-à-dire couvrir
l'ensemble de la zone par un rectangle plein puis «percer» les zones
visibles par les joueurs.

.. _recouvrir_lensemble_du_donjon_avec_les_vbl:

Recouvrir l'ensemble du donjon avec les VBL
-------------------------------------------

.. figure:: Vbl-map-zoomed-extents.png
   :alt: Vbl-map-zoomed-extents.png

   Vbl-map-zoomed-extents.png

.. figure:: Vbl-createsolidvbl.png
   :alt: Vbl-createsolidvbl.png

   Vbl-createsolidvbl.png

#. Dézoomez pour voir l'ensemble de la carte.
#. Cliquez sur «Dessiner une VBL en rectangle plein».
#. Cliquez gauche pour positionner le coin supérieur gauche de la zone
   VBL. Ne maintenez pas le bouton enfoncé.
#. Bougez la souris pour définir la taille de la zone VBL. Vous la
   verrez se dessiner en rouge translucide en même temps que vous
   bougez.
#. Cliquez gauche à nouveau pour définir le coin inférieur droit de la
   zone VBL. La zone va devenir bleue. Si vous changez de barre d'outil
   de dessin, la zone bleue va disparaître : elle n'est visible qu'avec
   la barre d'outil VBL active.

.. figure:: Vbl-complete-cover.png
   :alt: Vbl-complete-cover.png

   Vbl-complete-cover.png

Vous venez de couvrir toute la carte en VBL. Si un pion est placé
en-dehors de la zone, et dispose de la vue, il ne sera pas capable de
voir l'intérieur de la zone que vous venez de tracer.

.. _percer_le_donjon_avec_les_zones_visibles:

Percer le donjon avec les zones visibles
----------------------------------------

.. figure:: Vbl-erasingvbl.png
   :alt: Vbl-erasingvbl.png

   Vbl-erasingvbl.png

Nous allons «percer» les salles. Ce procédé est un peu retors et pour
conserver l'efficience des VBL, assurez-vous de tracer des lignes
droites et ne laissez pas de jour ou de petits bouts de VBL trainer (une
astuce est donnée plus loin). Tout d'abord, nous allons tout percer, à
l'exception des murs extérieurs dont nous nous occuperons ensuite.

#. Zommez jusqu'à être à l'aise.
#. Cliquez sur «Dessiner une VBL en rectangle plein».
#. Maintenez la touche Maj (Shift) enfoncée et cliquez gauche pour
   déterminer le coin supérieur gauche de la zone que vous voulez
   percer. Quand vous bougerez la souris, la zone sera dessinée en blanc
   translucide (si ce n'est pas le cas, maintenez Maj enfoncée).
#. Allez jusqu'au coin inférieur droit et cliquez gauche. La zone bleue
   disparaît alors; vous avez ôté le VBL sur cette zone. Les pions qui
   s'y trouveraient verraient normalement (jusqu'à croiser du bleu à
   nouveau, bien sûr !).
#. Répétez ce procédé pour les autres pièces, tunnels, etc.

.. figure:: Vbl-erased.png
   :alt: Vbl-erased.png

   Vbl-erased.png

À la fin, vous devriez avoir le donjon en bleu, avec des trous pour
chacune de ses salles.

**Astuce** : si vous maintenez la touche Ctrl enfoncée pendant votre
tracé, vous allez vous coller à la grille. C'est très utile pour aligner
les VBL. Cette technique a été utilisée sur la carte pour facilement
aligner les zones.

Cloisons
--------

.. figure:: Vbl-polyline-wall.png
   :alt: Vbl-polyline-wall.png

   Vbl-polyline-wall.png

Il ne reste plus qu'à tracer les cloisons intérieures du donjon. De
cette manière, les murs *intérieurs* du donjon bloqueront la vue des
pions.

#. Zommez sur un mur.
#. Sélectionnez l'outil Dessiner une VBL en polygone fermé plein.
#. Maintenez la touche Ctrl enfoncée et cliquez gauche pour placer
   l'origine de la ligne. Vous devriez commencer la ligne dans un bloc
   de VBL pour éviter d'introduire des interstices.
#. Bougez la souris pour tracer votre ligne. Sur la capture d'écran, la
   ligne est le fin trait rouge dans le cercle jaune; ce dernier a été
   ajouté à la capture d'écran pour vous aider à repérer facilement
   l'endroit à regarder, et n'apparaîtra pas sur votre écran).
#. Cliquez gauche pour déterminer l'extrémité de la droite. La ligne
   rouge va devenir bleue, indiquant ainsi qu'il y a un VBL sur le mur.
#. Recommencez l'opération pour tous les murs que vous voulez couvrir.

.. _blocage_de_vision_et_objets:

Blocage de vision et objets
---------------------------

Bon nombre d'objets peuvent obstruer la vision dans un donjon : les
portes, les piliers, les gravats, les coffres, etc. Il est possible de
placer des VBL n'importe où sur la carte. Toutefois, les VBL ne sont pas
liés aux objets. Vous ne pouvez donc pas placer un VBL sur une porte et
«l'ouvrir» quand vos joueurs ouvrent la porte. Vous pouvez simuler ce
comportement en effaçant la VBL qui couvre la porte. De la même manière,
il n'est pas possible de mouvoir un VBL en même temps qu'un objet.

Avec l'expérience, vous verrez ce qui vous satisfait le plus dans la
gestion des objets avec les VBL, mais voici quelques astuces :

-  **Les portes** : si elles sont fermées, tracez une ligne de VBL entre
   les deux murs qui l'encadre. Quand la porte est ouverte (si elle
   l'est jamais), vous pouvez tourner l'objet porte pour simuler son
   ouverture, et effacer la VBL à l'aide de l'outil Dessiner une VBL en
   rectangle plein (souvenez-vous : il faut maintenir la touche Maj
   (Shift) enfoncée pour effacer une VBL). N'utilisez pas les outils
   creux, car vous n'effaceriez que les contours de la forme tracée.

.. figure:: Vbl-drawx.png
   :alt: Vbl-drawx.png

   Vbl-drawx.png

-  **Piliers, statues et autres objets verticaux** : souvenez-vous que
   quand vous utilisez un VBL, les pions ne peuvent pas voir à travers
   du tout (subséquemment, les joueurs ne verront rien qui soit couvert
   par un VBL). Si vous voulez que les joueurs puissent observer une
   partie de l'objet, l'astuce consiste à tracer un «X» sur le pilier à
   l'aide de l'outil de polygone (plutôt que de couvrir tout le pilier
   avec une zone circulaire ou rectangulaire). Un «X» permet aux joueurs
   de voir des parties du pilier selon où leur pion se trouve. Cela rend
   beaucoup mieux ! Si vous regardez la capture d'écran, vous verrez
   qu'un «X» a été placé sur un des barils.

.. _limites_des_vbl:

Limites des VBL
===============

Le système d'obstruction de vision de MapTool permet de simuler ce qu'un
personnage peut voir pendant une partie. Cependant, il a ses limites et
ne simule pas une vision «complète». Nous avons souligné une limitation
précédemment : l'impossibilité de lier un VBL à un objet. Voici d'autres
limites (valables pour la version 1.3.b56 de MapTool) :

-  **L'obstruction est binaire** : On peut tout voir ou ne rien voir du
   tout. Il n'y a pas de transparence partielle, ou dans un sens
   uniquement dans MapTool.
-  **L'obstruction est totale** : Le VBL obstrue toutes les formes de
   vision, il n'y a aucun type de vision qui permet de passer au
   travers.
-  **L'obstruction n'a pas d'altitude**: On ne peut pas spécifier de
   hauteur à un VBL : on ne voit rien du plus profond des enfers
   jusqu'au plus haut des cieux ! Il n'y a donc aucun moyen de permettre
   à des personnages de voir par-delà parce qu'ils sont sufissament
   grands.

.. raw:: mediawiki

   {{Languages|Introduction to Vision Blocking}}

{{#customtitle:Introduction au blocage de vision|Introduction au blocage
de vision}}

`Category:MapTool <Category:MapTool>`__
`Category:Tutorial <Category:Tutorial>`__
