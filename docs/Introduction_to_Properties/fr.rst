.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{Languages|Introduction to Properties}}

.. _propriétés_de_campagne:

Propriétés de Campagne
======================

Un des aspects les plus utiles dans MapTool est la capacité des
`Pions <Introduction_to_Tokens/fr>`__ à emporter avec eux tout un jeu de
**Propriétés**, attachée à ce Pion, et qui peuvent être manipulées à
travers des Macros ou utilisées pour créer des aperçus rapides de
certaines informations. En d'autres termes, ces jeux de propriétés
ressemblent à des feuilles de personnage intégrées.

Toutefois, puisqu'ils sont si utiles, les développeurs de MapTool ont
créé différents moyens pour les utiliser et les manipuler. Ce guide
traitera donc de la création d'un Jeu de Propriétés de Campagne, des
valeurs par défaut à saisir pour les différents paramètres et comment
les utiliser pour manipuler la feuille de personnage.

.. _un_exemple_de_règles_mtrpg:

Un exemple de règles : MTRPG
============================

De manière à pouvoir disposer d'exemples concrets alors même que ce
tutoriel était en cours d'écriture, de nombreux utilisateurs et
contributeurs de MapTool ont développé `les règles de MTRPG (MapTool
Role Playing Game) <Sample_Ruleset>`__ -- un système de jeu simple
développé spécifiquement pour illustrer les différentes parties de
MapTool. Pour ce guide, nous créerons un nouveau fichier de campagne
puis nous construirons quelques **propriétés de campagne** (*campaign
properties*) qui correspondent aux spécificités de MTRPG

.. _la_fenêtre_propriétés_de_la_campagne_campaign_properties:

La fenêtre Propriétés de la Campagne (Campaign Properties)
==========================================================

.. figure:: Edit-campaign-props.png
   :alt: Edit-campaign-props.png

   Edit-campaign-props.png

Pour intervenir sur les propriétés de la campagne, vous devez aller dans
**Edit > Campaign Properties...**, qui ouvrira la fenêtre Propriétés de
la campagne (*Campaign Properties*). Dans cette fenêtre, vous verrez de
nombreux onglets et une foule d'informations.

Quand vous ouvrez la fenêtre **Propriétés de la campagne** (*Campaign
Properties*), six onglets apparaissent et concernent :

-  **Token Properties (Propriétés du Pion)**: cet onglet héberge toutes
   les jeux de propriétés qu'un Pion peut avoir.
-  **Repositories**: dans cet onglet, vous pouvez définir un site
   distant pour accueillir vos fichiers de campagne, et plus
   particulièrement les images, de manière à améliorer vos temps de
   chargement et votre vitesse lors des parties sur Internet.
-  **Sight (Vision)**: cet onglet est dédié au réglage et à la
   configuration de la vision.
-  **Light (Lumière)**: cet onglet est consacré a la configuration des
   sources de lumière et des auras .
-  **States (États)**: cet onglet sert à la configuration des `État des
   Pions <Token:state>`__.
-  **Bars (Barres)**: ici vous pouvez régler les différentes `barres de
   Pion <bar.name>`__.

Les informations affichées concernent uniquement la campagne en cours.

Ce guide est uniquement consacré au premier onglet **Propriétés du
Pion** (*Token Properties*).

.. _longlet_propriétés_du_pion_token_properties:

L'onglet Propriétés du Pion (Token Properties)
==============================================

.. figure:: Camp-props.png
   :alt: Camp-props.png

   Camp-props.png

Le premier onglet visible est l'onglet **Propriétés du Pion** (*Token
Properties*). cela parait relativement simple, mais il abrite quelques
possibilités vraiment formidables. Il y a trois zones de texte dans cet
onglet :

-  Nom (*Name*): Il s'agit du nom de l'ensemble de propriétés que vous
   êtes en train de consulter. Quand vous ouvrez la fenêtre, aucun
   ensemble de propriétés n'est sélectionné.
-  Type: cette colonne sur le coté gauche n'est pas éditable, mais
   fournit une liste de tous les ensembles de propriétés de la campagne
   courante. Si vous n'avez chargé aucune campagne, la seule entrée est
   **Basic**.
-  Une large zone de texte dans laquelle vous pouvez saisir les
   propriétés de la campagne courante. Vide à l'ouverture de la fenêtre,
   vous obtenez le nom et la valeur par défaut de toutes les propriétés
   associées à chaque ensemble lorsque vous les sélectionnez dans la
   partie **Type de Pion** (*Token Type*).

Type
----

Dans ce champ, vous obtenez les noms des différents types de propriétés
(que vous pouvez considérer comme des *ensembles* de propriétés) qui ont
été configurés dans la campagne en cours. Si vous n'avez chargé aucune
campagne, l'ensemble de propriétés par défaut affiché sera **Basic**. Le
champ *type* n'est pas modifiable directement par l'utilisateur.

.. _nom_name:

Nom (*Name*)
------------

Dans ce champ, vous pouvez saisir le nom que vous souhaitez à un
ensemble de propriétés. Ce nom apparaîtra dans la liste *Token Type*,
lorsque vous cliquerez sur le bouton **update** (mettre à jour). Vous
pouvez mettre n'importe quels noms; certains utilisateurs appellent des
ensembles "PNJ" lorsque les caractéristiques et les traits des PNJ
diffèrent de ceux des PJ, par exemple.

Propriétés
----------

C'est à partir d'ici que ça devient intéressant. Dans cette zone de
texte, vous pouvez créer tout et n'importe quoi pour refléter tous les
nombres et caractéristiques qu'un personnage de jeux de rôle peut avoir
(ainsi que toutes celles qu'il n'a pas -- de nombreux utilisateurs
créent des propriétés qui leurs sont utiles pour l'écriture de leur
Macros mais qui n'apparaissent pas dans la feuille de personnage !).

.. _créer_un_ensemble_de_propriétés:

Créer un ensemble de Propriétés
===============================

.. _propriétés_sans_valeur_par_défaut:

Propriétés sans valeur par défaut
---------------------------------

.. figure:: Basic-default-props.png
   :alt: Basic-default-props.png

   Basic-default-props.png

Si vous jetez un oeil aux `Attributs principaux de
MTRPG <Sample_Ruleset#Primary_Attribute>`__, vous verrez qu'il existe
quatre attributs de base pour un personnage : *Force*, *Dextérité*,
*Intelligence* et *Endurance*. Nous allons nous débarrasser des
propriétés par défaut et les remplacer par ces nouvelles
caractéristiques.

1. Allez dans **Edit > Campaign Properties**. Vous verrez sur le coté
gauche, en dessous de *Token Type*, que la seule entrée est "Basic".
Nous allons donc créer un nouvel ensemble de propriétés.

2. Dans la liste **Token Type** sur la gauche, sélectionnez *Basic*. Ce
faisant, vous apercevez tout un tas de propriétés avec plein de symboles
tels que @ ou #.

3. Dans la zone de texte contenant toutes les propriétés, utilisez la
souris pour toutes les sélectionner, puis appuyer sur la touche Effacer
(*Delete*) de votre clavier. Allez-y, ne soyez pas timide !

4. Ne touchez pas au champ **Name** - MapTools doit toujours avoir un
ensemble de propriétés *Basic*, en conséquence, vous ne pouvez pas
changer ce nom.

.. figure:: Default-props-replaced.png
   :alt: Default-props-replaced.png

   Default-props-replaced.png

5. Dans la zone de texte sous le champ **Name**, saisissez le nom de
chaque attributs de MTRPG, pour obtenir ceci:

   | ``Force``
   | ``Dextérité``
   | ``Intelligence``
   | ``Endurance``

Une fois remplie, la fenêtre de propriétés devrait ressembler à la
capture d'écran sur la droite.

6. Une fois que vous aurez saisi les propriétés souhaitées, cliquez sur
le bouton **Update** (*Mettre à jour*). Ne vous inquiétez pas de voir
les propriétés disparaître, vous devrez sélectionner *Basic* dans la
liste à gauche pour les voir ré-apparaître dans la zone de texte
principale.

7. Cliquez sur **OK** pour confirmer vos changements et fermez la
fenêtre **Campaign Properties** (*Propriétés de Campagne*).

8. Allez dans **File > Save Campaign As** et sauvegardez votre campagne
sous **MTRPG.cmpgn**. Vous avez maintenant créé un nouveau fichier de
campagne accompagné d'un nouvel ensemble de propriétés.

Quand vous créez des propriétés de cette façon -- en listant les valeurs
les unes après les autres -- et que vous ouvrez un Pion, vous
remarquerez que ces propriétés n'ont pas de valeurs. Cela ne signifie
pas qu'elles sont égales à zéro ou qu'elles sont remplies avec des
espaces blancs - cela veut littéralement dire qu'elles n'ont pas de
valeurs. Cela ne signifie pas grand chose dans la plupart des cas, mais
il s'agit d'une distinction importante en terme d'écriture de Macros (en
programmation, il y une grande différence entre une ligne de blanc et
une variable laissée vide !).

Une fois les propriétés mises à jour, tous les Pions sur la carte ainsi
que ceux à venir hériteront des nouvelles propriétés que vous avez
définies.

**NOTE**: Les noms des proprietes ne peuvent pas contenir d'espaces -
ainsi si vous avez besoin d'une propriété *Points de Vie*, vous devrez
la saisir comme *PointdeVie*.

.. _créer_des_propriétés_ayant_des_valeurs_par_défaut:

Créer des propriétés ayant des valeurs par défaut
-------------------------------------------------

.. figure:: Newprops-defvalues.png
   :alt: Newprops-defvalues.png

   Newprops-defvalues.png

Dans MTRPG, la valeur minimum qu'un attribut peut avoir est 1. Dans ces
conditions, il parait sensé de régler la *valeur par défaut* de ses
propriétés à 1 (ainsi, tous les Pions auront au moins la valeur minimum
qu'un attribut peut avoir). Pour faire cela :

1. Ouvrez la fenêtre des *propriétés de la campagne*.

2. Sélectionnez l'ensemble de propriétés *Basic*.

3. Dans la zone de texte principale, éditez les propriétés de manière à
obtenir :

   | ``Force:1``
   | ``Dexterité:1``
   | ``Intelligence:1``
   | ``Endurance:1``

4. Cliquez sur **Update**.

En plaçant deux points puis 1 à la fin du nom de chaque attribut, vous
demandez à MapTool d'affecter 1 à la valeur par défaut pour ces
propriétés (en d'autres termes, n'importe quelle valeur placée après les
deux points devient la *valeur par défaut* de la propriété en question).
Vous remarquerez qu'au bas de la zone de texte principale, se trouve une
légende décrivant les différentes options que vous pouvez affecter à une
propriété.

Maintenant, si vous déposer un nouveau Pion sur la carte et que vous
regardez ses propriétés (double-cliquez sur le Pion et sélectionnez
l'onglet Propriétés dans la fenêtre de dialogue *Edit Token*), vous
verrez que les propriétés du Pion ont les valeurs par défaut.

Ne vous inquiétez pas à propos des Pions dont vous avez déjà modifié les
valeurs des propriétés - régler ou modifier les valeurs par défaut ne
change en rien des propriétés déjà saisies. MapTool est assez
intelligent pour gérer ça.

.. _afficher_les_propriétés_dans_la_feuille_de_caractéristiques:

Afficher les Propriétés dans la feuille de caractéristiques
-----------------------------------------------------------

.. figure:: Statsheet-props.png
   :alt: Statsheet-props.png

   Statsheet-props.png

MapTool dispose d'une fonctionnalité sympathique appelée **Statsheet**
(feuille de caractéristiques), laquelle est mentionnée brièvement dans
la section `Introduction à la gestion des
Pions <Introduction_to_Tokens/fr>`__ - Il s'agit simplement d'une
info-bulle qui apparaît dans le coin inférieur gauche de la carte, quand
vous passez au dessus du Pion avec la souris.

Peut-être êtes vous en train de vous dire : "Attendez... quand je passe
au-dessus de ma figurine, il n'y a aucune feuille de caractéristiques !
Où est-elle?" La raison pour laquelle vous ne voyez rien apparaître pour
l'instant est que la feuille de caractéristiques est gérée par les
propriétés de la campagne - elles affichent les propriétés du Pion
(accompagnant une version plus grande de l'image de ce dernier) - mais
*seulement* lorsqu'un certains nombre de pré-requis sont satisfaits :

-  Les propriétés ont été réglées pour être affichées sur la feuille de
   caractéristiques.
-  Les propriétés devant être affichées ont une valeur.

.. _réglages_permettant_laffichage_des_propriétés:

Réglages permettant l'affichage des Propriétés
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. figure:: Newprops-visible.png
   :alt: Newprops-visible.png

   Newprops-visible.png

Au bas de l'onglet **Token Properties** (Propriété du Pion) de la
fenêtre **Campaign Properties**, une légende explique comment régler
l'affichage d'une propriété dans la feuille de caractéristiques. Trois
options d'affichage sont alors disponibles, chacune d'elles est
sélectionnée en la plaçant en face de la propriété a afficher :

#. **\***: un astérisque signifie "afficher cette propriété dans la
   feuille de caractéristiques"
#. **@**: signifie "afficher cette propriété seulement pour le
   propriétaire du Pion (et pour le MJ)"
#. **#**: signifie "afficher cette propriété seulement pour le MJ (même
   le propriétaire du Pion ne la verra pas)"

L'astérisque est **requis** pour n'importe quelle statistique à afficher
- si vous n'avez pas un astérisque en premier, rien ne s'affichera
quoique vous ayez pu saisir dessus. Les symboles @ et # sont de leur
coté optionnels.

Donc pour notre nouveau jeu, nous allons régler les propriétés pour
qu'elles soient visibles de tout le monde (en utilisant simplement un
astérisque). Pour ce faire, ouvrez les propriétés de votre campagne et
éditez les de la façon suivante :

   | ``*Force:1``
   | `` *Dextérité:1``
   | `` *Intelligence:1``
   | `` *Endurance:1``
   | 

Maintenant quand vous passez votre souris au-dessus d'un Pion, vous
pouvez voir la feuille de caractéristiques apparaître (voir la copie
d'écran ci-dessus) avec les valeurs par défaut en Force, Dextérité,
Intelligence et Endurance. De cette manière, même un tout nouveau Pion
aura des valeurs par défaut et la feuille de caractéristiques apparaîtra
pour tous les Pions.

Abréviations
~~~~~~~~~~~~

.. figure:: Newprops-shortnames.png
   :alt: Newprops-shortnames.png

   Newprops-shortnames.png

Quelquefois, les noms de propriétés sont trop longs (ou n'ont pas une
apparence agréable - pas d'espace...). MapTool vous permet de mettre une
*Abréviation* pour chaque propriété. Pour cela, il suffit de mettre
entre parenthèses l'abréviation, juste après le nom de la propriété,
comme ceci :

   | ``*Force(FOR):1``
   | `` *Dextérité(DEX):1``
   | `` *Intelligence(INT):1``
   | `` *Endurance(END):1``
   | 

Ces abréviations sont affichées dans la feuille de caractéristiques au
lieu du nom complet de la propriété.

**Les Abréviations sont utilisées uniquement pour l'affichage - lorsque
vous référencez une propriété dans une Macro, vous devez utiliser son
nom complet.**

.. _créer_des_propriétés_dérivées:

Créer des Propriétés dérivées
-----------------------------

.. figure:: Newprops-derived.png
   :alt: Newprops-derived.png

   Newprops-derived.png

.. figure:: Statsheet-with-allnewprops.png
   :alt: Statsheet-with-allnewprops.png

   Statsheet-with-allnewprops.png

Essayons maintenant de faire quelque chose de plus sympa. Dan la plupart
des jeux de rôles, certains attributs des personnages sont en fait
calculées à partir d'autres - par exemple, dans l'appel de Chtulhu, la
santé mentale est calculée en multipliant le pouvoir par 5. Il en est de
même dans Donjons et Dragons où le score de constitution intervient dans
le calcul des points de vie.

Maintenant, vous pourriez créer ces attributs dérivés en ajoutant une
ligne et en saisissant manuellement les valeurs lorsque vous créez un
nouveau Pion - mais pourquoi ne pas permettre à MapTool de calculer ces
valeurs dérivées? En effet, les propriétés de campagne de MapTool
peuvent être des nombres ou du texte, mais également des calculs et des
équations basés sur d'autres propriétés du Pion.

Dans MTRPG, Il existe trois attributs *dérivés* : Les Points de Vie,
L'Armure et la Vitesse. Ces attributs ont pour abréviations "PV" "AR"
"VT". Pour cet exemple, nous allons définir les *Points de Vie* et la
*Vitesse* pour qu'ils soient calculés à partir de propriétés existantes.
Nous ne définirons pas tout de suite l'Armure (le calcul est un peu plus
complexe, et nous voulons avancer progressivement).

Premièrement, nous devons ajouter des propriétés pour ces trois
attributs dérivés :

1. Ouvrez la fenêtre avec l'ensemble de propriétés Basic.

2. En dessous de *Endurance*, ajoutez :

   | ``*PointsdeVie(PV)``
   | `` *Armure(AR)``
   | `` *Vitesse(VT)``
   | 

Vous remarquerez que jusque là, nous n'avons défini aucune valeur par
défaut. N'appuyez pas tout de suite sur le bouton **Update** - attendez
d'avoir entré quelques linges de code de Macros pour créer une valeur
dérivée.

Nous pouvons voir dans l'exemple de règles `MTRPG <Sample_Ruleset>`__
que les *Points de Vie* sont égaux à la valeur de *l'Endurance*
multipliee par 6. Reproduire ce calcul dans les proprietes de la
campagne est tres facile. éditez la propriété *PointsdeVie* de la façon
suivante :

   ``*PointsdeVie(PV):{Endurance * 6}``\ 

Ce que nous avons fait ici revient à saisir une valeur par défaut pour
la propriété (rappel : les valeurs par défaut viennent après les deux
points), et à utiliser un peu de `code de
Macros <Introduction_to_Macro_Writing>`__ pour expliquer à MapTool
comment réaliser une opération afin de trouver la valeur d'une
propriété. Deux choses ont été faites dans ce but :

#. Nous avons inclus le calcul entre { }, ce qui avertit MapTool que le
   texte contenu entre les crochets doit être considéré comme une Macro
   et pas simplement comme du texte.
#. Ce que nous avons écrit à l'intérieur des crochets signifie : "trouve
   la valeur de la propriété *Endurance*, multiplie-la par 6, et affecte
   le résultat à la valeur de la propriété *PointsdeVie*"

Maintenant, pour gérer l'attribut *Vitesse*, notre travail sera encore
plus simple : nous devons indiquer à MapTool qu'il doit prendre la
valeur de la propriété *Dextérité*, et l'affecter à la propriété
*Vitesse*. Pour cela, éditez la propriété *Vitesse* de la manière
suivante :

   ``*Vitesse(VT):{Dextérité}``\ 

Quand vous aurez fini, l'ensemble de propriétés devrait ressembler à
cela :

   | ``*Force(FOR):1``
   | `` *Dextérité(DEX):1``
   | `` *Intelligence(INT):1``
   | `` *Endurance(END):1``
   | `` *PointsdeVie(PV):{Endurance * 6}``
   | `` *Armure(AR)``
   | `` *Vitesse(VT):{Dextérité}``
   | 

Maintenant, lorsque vous passez la souris au dessus d'un Pion, la
feuille de caractéristiques devrait ressembler à la copie d'écran sur la
droite. Souvenez-vous que même si nous avons décidé de faire apparaître
l'Armure sur la feuille de caractéristiques, celle-ci n'affichera que
les propriétés contenant une valeur - *Armure* est toujours vide, donc
elle ne s'affichera donc pas tant que vous ne lui aurez pas donné de
valeur.

.. _quelques_détails_techniques:

Quelques Détails techniques
===========================

Dans ce guide et dans certains autres, nous avons parlé de propriétés
visible dans la campagne ou de propriétés établies pour une campagne. Il
y a une raison à cela.

Prenez un Pion - si vous le coupez et examinez son fonctionnement
interne - est en fait un fichier XML contenant une tonne d'informations
(image, taille, vision, éclairage, forme et - bien sûr - ses
propriétés). Ce qui est important de comprendre ici, c'est que le Pion
se souviendra non seulement des propriétés se rapportant à MTRPG, mais
aussi de toutes celles qui ont un jour été sauvegardées en tant que
fichier **.rptok** ou apportées depuis un autre fichier de campagne,
campagne dont il se souviendra des propriétés également. même si elles
ne sont pas visible, elles sont conservées à l'intérieur du Pion
lui-même.

Ainsi, en réalité, un ensemble de propriétés de campagne indique les
propriétés que :

-  Vous pouvez voir si vous ouvrez le Pion en double-cliquant dessus.
-  Vous pouvez éditer en cliquant sur la cellule à côté.

Ceci pourrait provoquer des catastrophes - qu'arrivera-il si vous
modifiez une propriété déjà existante mais cachée ? Heureusement,
MapTool ne tentera pas d'accéder à une propriété cachée à l'aide d'une
Macro, à moins que vous ne lui ayez demandé de le faire au travers de
deux fonctions de Macros spéciales. Donc soyez rassuré, vous ne pouvez
donc pas modifier accidentellement une propriété qui n'a pas été mise au
point dans les propriétés de la campagne.

.. _pour_aller_un_peu_plus_loin_...:

Pour aller un peu plus loin ...
===============================

MapTool supporte des propriétés et des propriétés dérivées très
élaborées, avec de nombreuses fonctions et opérations mathématiques.
Parmi les plus utilisées, vous trouverez :

-  **Opérations mathématiques de base**: addition (+), soustraction (-),
   multiplication (*), et division (/)

   -  **Exemple**: ``PointsdeVie: {Endurance * 6}``

-  **Approximation**: il existe quelques *fonctions* qui vous permettent
   d'arrondir des nombres (après une division par exemple).

   -  **Plancher**: la fonction floor() arrondit *à l'inférieur*.
      **Exemple**: ``PointsdeVie:{floor(Constitution/2)}`` divisera la
      constitution par deux et arrondira à l'inférieur
   -  **Plafond**: la fonction ceil() marche comme floor(), mais
      arrondit *au supérieur*. **Exemple**:
      ``PointsdeVie:{ceil(Constitution/2)}``

{{#customtitle:Introduction aux Propriétés|Introduction aux Propriétés}}

`Category:MapTool <Category:MapTool>`__
