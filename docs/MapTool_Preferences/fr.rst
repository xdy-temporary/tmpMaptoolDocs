.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{Languages|MapTool Preferences}}

{{#customtitle:Préférences de MapTool|Préférences de MapTool}} __TOC__

.. _onglet_interactions:

Onglet Interactions
===================

.. figure:: prefs_tab_interactions.png
   :alt: prefs_tab_interactions.png

   prefs_tab_interactions.png

Cartes
------

.. figure:: prefs_interactions_maps.jpg
   :alt: prefs_interactions_maps.jpg

   prefs_interactions_maps.jpg

-  **Les nouvelles cartes ont le Brouillard de Guerre** (*New maps have
   Fog of War*)

   Détermine si les nouvelles cartes doivent avoir le `Brouillard de
   Guerre <Fog_of_War>`__ activé à la création. Si vous utilisez le
   `Brouillard de Guerre <Fog_of_War>`__, cela semble évident de ✓
   l'activer ; cependant, pendant que l'on crée plusieurs cartes pour
   une nouvelle campagne, cela semble souvent utile de le désactiver
   pour faciliter la modification des cartes, étant donné que même en
   tant que MJ, vous ne verrez pas complètement une carte couverte du
   `Brouillard de Guerre <Fog_of_War>`__. Lorsque la carte est terminée,
   il est simple de réactiver le `Brouillard de Guerre <Fog_of_War>`__
   sur celle-ci.

-  **Les nouvelles cartes sont visibles par les joueurs** (*New maps
   visible to players*)

   Indique si les nouvelles cartes doivent être marquées 'Visible par
   les joueurs' (*Player Visible*) à la création. Bien qu'il y ait des
   exceptions, avoir cette option ✓ décochée est un paramétrage optimal
   ; de cette façon, vous ne laissez pas involontairement une carte
   accessible aux joueurs.

-  **Type de Grille par défaut** (*Default Grid Type*)

   -  **Cases** (*Square*) |gridSquare.png|
   -  **Hexagones horizontaux** (*Horizontal Hex*)
      |gridHorizontalHex.png|
   -  **Hexagones verticaux** (*Vertical Hex*) |gridVerticalHex.png|

   détermine le type de grille proposé par défaut lors de la création
   d'une carte. Vous êtes libre de créer des cartes sans type de grille,
   mais aussi de type différent de celui spécifié ici, mais vous ne
   pouvez pas mettre le type par défaut proposé à "Sans grille".

-  **Taille de grille par défaut** (*Default Grid Size*)

   représente le nombre de pixels que vous voulez que MapTool utilise
   pour dessiner chaque cellule de la grille, à la résolution maximum.
   Le paramétrage par défaut de pixels est idéal pour la plupart des
   ordinateurs, mais les ordinateurs haut de gamme peuvent gérer ou même
   pixels. Il n'y aucun pré requis pour utiliser des tailles
   spécifiques, mais et pixels sont utilisés couramment. Cette
   préférence déterminera aussi quelle taille prendre une image
   lorsqu'elle sera placée sur la carte ; si elle n'est pas paramétrée
   en taille libre (*Free-size*) et pas manuellement redimensionnée.

-  **Nombre d'unités par cellule par défaut** (*Default Units Per Cell*)

   indique le nombre d'unités de mesure que représente chaque cellule de
   la grille. L'ambigüe "unité" est utilisé dans ce cas parce que VOUS
   décidez ce qu'il représente. Si vous voulez que chaque cellule
   représente 5 pieds (1,5m) comme dans D&D3, ce paramètre devra être
   saisi à . Si voulez que chaque cellule représente une case comme dans
   D&D4, saisissez . Si vous voulez que chaque cellule représente 4
   kilomètres, choisissez , etc... Cette unité est souvent mentionnée
   comme la *Distance par Cellule* (*Distance Per Cell*).

-  **Distance de vision par défaut** (*Default Vision Distance*)

   La distance maximum à laquelle les `Pions de joueurs <PC_Token>`__
   peuvent dissiper le `Brouillard de guerre <Fog_of_War>`__ après que
   les `lumières <Light>`__, `vues <Sight>`__, et les `calques de
   blocage de vision (VBL) <Vision_Blocking_Layer>`__ aient été pris en
   compte. Il est important de noter que ce paramètre est mesuré en
   *Distance par Cellule* (cf. ci-dessus).

-  **Métrique de mouvement** (*Movement metric*)

   -  **Un_Deux_Un** (*ONE_TWO_ONE*)
   -  **Un_Un_Un** (*ONE_ONE_ONE*)
   -  **MANHATTAN**
   -  **Pas de diogonales** (*NO DIAGONALS*)

   détermine comment les mouvements doivent être calculés quand un
   `Pion <Token>`__ se déplace en diagonal. Cela affecte le total de
   distance parcourue affiché sous un `Pion <Token>`__ quand il est en
   train d'être déplacé ; cela est calculé en *Distance par Cellule*
   (*Distance Per Cell*). **ONE_TWO_ONE** spécifie que chaque diagonal
   fera deux fois la *Distance par Cellule*. **ONE_ONE_ONE** : chaque
   diagonale fait une *Distance par Cellule*. **MANHATTAN** spécifie que
   chaque diagonal fera deux fois la *Distance par Cellule*. **NO
   DIAGONALS** indique que les `Pions <Token>`__ ne peuvent pas se
   déplacer en diagonale. Le paramètre **Movement metric** n'a
   d'influence en jeu que sur les cartes utilisant une grille en case ;
   les cartes avec une grille hexagonale calculent les mouvements dans
   n'importe quelle direction en ''Distance par Cellule'.

Pions
-----

.. figure:: prefs_interactions_tokens.jpg
   :alt: prefs_interactions_tokens.jpg

   prefs_interactions_tokens.jpg

-  **Aligner sur la grille** (*Start Snap to Grid*)

   Détermine si les `Pions <Token>`__ seront, par défaut, alignés sur la
   grille (**Snap to Grid** ✓checked). Avoir ce paramètre ✓ coché est
   optimal pour les cartes utilisant une grille, mais même sur de telles
   cartes, vous pouvez vouloir temporairement désactiver cette propriété
   (par exemple, lorsque l'on place beaucoup de pions "d'accessoires"
   sur le calque Objet pendant que l'on dessine la carte).

-  **Les nouveaux pions sont visibles par les joueurs** (*New tokens
   visible to players*)

   Indique si les nouveaux `Pions <Token>`__ ont la propriété
   **Visible** ✓ activée à la création. Le paramétrage optimal dépend de
   votre style de jeu ; si vous avez de nombreuses rencontres aléatoires
   et les créez en cours de partie, il pourra vous être utile de
   désactiver cette option.

-  **Numérotation des pions dupliqués** (*Duplicate Token Numbering*)

   -  **Incrémenter** (*Increment*)
   -  **2 chiffres aléatoires** (*Random 2-digit*)

   va automatiquement ajouter 2 chiffres aux `Pions <Token>`__ ayant un
   nom dupliqué, lors de la création. **Incrémenter** n'ajoutera pas de
   chiffre au premier pion, mais numérotera chaque copie après cela, en
   démarrant au chiffre (ex: Troll, Troll 1, Troll 2). **2 chiffres
   aléatoires** ajoutera un nombre aléatoire à deux chiffres au nom du
   pion, même s'il n'y a pas encore de doublon sur la carte. **2
   chiffres aléatoires** pourrait être considéré le paramétrage optimal,
   car il ne donnera à vos joueurs aucune indication sur le nombre exact
   de copies d'un Pion.

-  **Affiche la numérotation sur** (*Show Numbering on*)

   -  **le Nom** (*Name*)
   -  **le Nom MJ** (*GM Name*)
   -  **les Deux** (*Both*)

   détermine comment le numéro issu du paramètre **Numérotation des
   pions dupliqués** est appliqué. **le Nom** ajoute le numéro après le
   nom (lui-même déterminé par **Nommage d'un Nouveau Pion**). **le Nom
   MJ** place le numéro dans le champ Nom MJ des options du pion. **Les
   Deux** ajoute le numéro après le nom ET place le numéro dans le champ
   Nom MJ des options du pion. Du fait d'un comportement étrange de
   MapTool lorsqu'il doit gérer deux pions avec le même nom, il est
   recommandé que vous utilisiez **Nom** ou **les Deux** mais jamais
   **le Nom MJ**.

-  **Nommage d'un nouveau pion** (*New Token Naming*)

   -  **Utiliser le nom de fichier** (*Use Filename*)
   -  **Utiliser "Créature"** (*Use "Creature"*)

   détermine quel sera le nom d'un nouveau pion créé, ou comment sera
   pré rempli le champ *Nom* du dialogue de création de nouveau pion.
   **Utiliser le nom de fichier** indique que le nom du pion sera déduit
   du nom du fichier qui a été ajouté à votre bibliothèque de ressources
   (ex : si vous avez ajouter le fichier *gobelinlaid.jpg* à votre
   bibliothèque de ressources, les pions créés à partir de cette image
   auront un nom commençant par *gobelinlaid*). **Utiliser "Créature"**
   fera que le nom de tous les nouveaux pions créés commencera par
   "Creature" (sans les guillemets).

-  **Taille réelle** (*Start Freesize*)

   Si vous utilisez une carte avec une grille, les `Pions <Token>`__
   ajoutés seront par défaut de la taille d'une cellule. En cochant ce
   paramètre ✓, les pions seront créés à la taille réelle de l'image, ce
   qui est très utile pour placer des accessoires sur le calque d'Objet
   ou des éléments de décors à l'échelle sur le calque de fond.

-  **Afficher le dialogue à la création d'un Pion** (*Show Dialog on New
   Token*)

   Quand cette préférence est ✓cochée, une fenêtre *Nouveau Pion* (*New
   Token*) s'ouvrira lorsque vous ferez glisser une image sur la carte,
   vous permettant de modifier quelques options avant la création. Si
   vous désactivez ceci, tous les nouveaux pions seront créés avec le
   paramétrage par défaut déterminé par les différentes préférences
   décrites dans cette section.

-  **Taille du portrait de la Feuille de Statistiques** ('' Stat Sheet
   Portrait Size'')

   définit la taille en pixels) du portrait qui est affiché dans le coin
   inférieur droit de la carte lorsque la souris survole certains Pions
   ; l'image est redimensionnée proportionnellement. Un portrait est
   affiché sous quelques conditions différentes : si le Pion a des
   propriétés qui sont définies pour être affichées sur la feuille de
   statistiques et que ces propriétés ont une valeur, le portrait
   affichera l'image du pion. Si le pion a une image de portrait
   définie, il l'affichera avec ou sans la feuille de stats.

-  **Mettre à zéro pour désactiver le portrait** (*Set to 0 to disable
   portaits*)

   Pourquoi voudriez-vous paramétrer ceci à ? Au-delà de l'évidence (ne
   pas afficher le portrait), vous pourriez vouloir utiliser la feuille
   de stats, mais sans qu'un portrait apparaisse avec ; ou peut-être ne
   voulez pas utiliser ni de portrait ni de feuille de stats mais voulez
   utiliser "l'emplacement" de l'image de portrait pour d'autres
   utilisations, dans un Dialog ou une Frame par exemple.

Chat
----

.. figure:: prefs_interactions_chat.jpg
   :alt: prefs_interactions_chat.jpg

   prefs_interactions_chat.jpg

-  **Afficher l'avatar à chaque ligne** (*Show Avatar per line*)

   l'image du pion personnifié (*impersonnated*) est montrée à côté de
   chaque paragraphe de chat qu'il produit, quand cette option est ✓
   cochée. Ceci est un paramétrage local du côté client et n'affecte pas
   les autres joueurs connectés à la même partie.

-  **Insérer les émoticones** (*Insert Smilies*)

   remplace les suites de caractères d'émoticones courants par leur
   version graphique quand cette option est ✓ cochée. Si vous utilisez
   de nombreuses macros, il est recommandé de désactiver cette option,
   qui peut poser problème si n'importe quelle portion de votre code de
   macro peut être interprété comme un émoticone.

-  **Utiliser l'info-bulle pour les lancer** (*Use ToolTips for Inline
   Rolls*)

   détermine quel est l'affichage par défaut (`Options d'affichage de
   lancer <:Category:Display_Roll_Option>`__) pour les lancers de dés
   dans le chat. Utilisera si cette option est cochée ✓ cochée, sinon
   par défaut utilisera .

-  **Couleur de fond du préfixe pour les macros de confiance** (*Trusted
   Prefix Background*)

   détermine une couleur de fond personnalisée pour l'affichage des
   textes issu de `Macro de Confiance <Trusted_Macro>`__.

-  **Couleur de texte du préfixe pour les macros de confiance**
   (*Trusted Prefix Foreground*)

   détermine une couleur de texte personnalisée pour l'affichage des
   textes issu de `Macro de Confiance <Trusted_Macro>`__.

-  **Délai entre les sauvegardes automatiques** (*Time between
   autosaves*)

   Nombre de minutes entre deux sauvegardes automatiques de l'historique
   du chat. Cette fonction n'est pas active en 1.3b54.

-  **Fichier de sauvegarde automatique du chat** (*Autosave Chat Log
   Filename*)

   Nom du fichier qui sera utilisé pour sauvegarder automatiquement
   l'historique du chat. Cette fonction n'est pas active en 1.3b54.

Objets
------

.. figure:: prefs_interactions_objects.jpg
   :alt: prefs_interactions_objects.jpg

   prefs_interactions_objects.jpg

-  **Aligner sur la griller** (*Start Snap to Grid*)

   Détermine si les Pions créés sur le calque "object" seront, par
   défaut, alignés sur la grille (Snap to Grid ✓).

-  **Taille réelle** (*Start Freesize*)

   Si vous utilisez une carte avec une grille, les Pions ajoutés sur le
   calque "object" seront par défaut de la taille d'une cellule. En
   cochant ce paramètre ✓, les pions seront créés à la taille réelle de
   l'image.

Backgrounds
-----------

.. figure:: prefs_interactions_backgrounds.jpg
   :alt: prefs_interactions_backgrounds.jpg

   prefs_interactions_backgrounds.jpg

-  **Aligner sur la griller** (*Start Snap to Grid*)

   Détermine si les Pions créés sur le calque "Background" seront, par
   défaut, alignés sur la grille (Snap to Grid ✓).

-  **Taille réelle** (*Start Freesize*)

   Si vous utilisez une carte avec une grille, les Pions ajoutés sur le
   calque "Background" seront par défaut de la taille d'une cellule. En
   cochant ce paramètre ✓, les pions seront créés à la taille réelle de
   l'image.

.. _orientation_facing:

Orientation (Facing)
--------------------

.. figure:: prefs_interactions_facing.jpg
   :alt: prefs_interactions_facing.jpg

   prefs_interactions_facing.jpg

-  **Sur les lignes** (*On Edges*)

   L'orientation (*facing*) d'un Pion s'alignera sur les côtés des
   cellules quand ce paramètre est coché ✓.

-  **Sur les angles** (*On Vertices*)

   L'orientation (*facing*) d'un Pion s'alignera sur les angles d'une
   cellule quand ce paramètre est coché ✓.

.. _onglet_accessibilité_accessibility:

Onglet Accessibilité (Accessibility)
====================================

|prefs_tab_accessibility.png| |prefs_accessibility_all.jpg|

-  **Taille de la police** (*Chat Font Size*)

   Taille par défaut de la police dans le panneau de chat, mesurée en
   points.

-  **Délai initial des Infos-bulles** (*ToolTip Initial Delay*)

   Temps nécessaire pour afficher une info-bulle lorsque la souris
   survole un élément possédant une info-bulle, mesurée en millièmes de
   seconde.

-  **Délai de disparition des Info-bulles** (*ToolTip Dismiss Delay*)

   Temps nécessaire pour cacher une info-bulle lorsque la souris ne
   survole plus un élément possédant une info-bulle, mesurée en
   millièmes de seconde.

.. _application_tab:

Application Tab
===============

.. figure:: prefs_tab_application.png
   :alt: prefs_tab_application.png

   prefs_tab_application.png

.. _sauvegarde_save:

Sauvegarde (Save)
-----------------

.. figure:: prefs_application_save.jpg
   :alt: prefs_application_save.jpg

   prefs_application_save.jpg

-  **Sauvegarder une récupération automatique toutes les [ ] minutes**
   (*Save Autorecover every [ ] min*)

   Sauvegarde une copie de votre campagne dans l'intervalle spécifié.
   Contrairement à la sauvegarde automatique, cela n'écrira pas par
   dessus votre fichier de campagne, mais créera plutôt un nouveau
   fichier à chaque fois.

-  **Rappel de sauvegarde à la fermeture** (*Save reminder on close*)

   Affiche un dialogue lorsque l'on tente de fermer MapTool et que des
   modifications non enregistrées ont été faites à la campagne, si cette
   option est cochée ✓.

-  **Compatibilité 1.3b50** (*1.3b50 Compatability Mode*)

   du fait de certains changements dans la façon d'enregistrer certaines
   données au sein des fichiers de campagne, ces fichiers peuvent ne pas
   être compatibles avec des versions 1.3b50 et antérieures. Si ce
   paramètre est coché ✓, votre campagne sera enregistrée dans l'ancien
   format, compatible avec d'anciennes versions de MapTool mais perdant
   quelques nouvelles fonctionnalités.

.. _valeurs_par_défaut_de_la_carte_map_defaults:

Valeurs par défaut de la Carte (Map Defaults)
---------------------------------------------

.. figure:: prefs_application_mapdefaults.jpg
   :alt: prefs_application_mapdefaults.jpg

   prefs_application_mapdefaults.jpg

-  **Épaisseur de la ligne de Halo** (*Halo line width*)

   contrôle l'épaisseur du `Halo <Halo>`__ lorsqu'il est affiché sur un
   `Pion <Token>`__.

-  **Opacité de la Vision** (*Vision opacity*)

   les zones qui ne sont pas directement visibles, mais qui n'ont plus
   de brouillard de guerre, seront obscurcies en les recouvrant d'un
   calque noir semi-translucide. Ce paramètre contrôle l'opacité de ce
   noir translucide.

-  **Utiliser la couleur du halo pour la vision** (*Use halo color for
   vision*)

   lié à **Opacité de la Vision**. Si ce paramètre est coché ✓, le
   calque translucide au-dessus des zones déjà vues sera de la couleur
   du `Halo <Halo>`__ du `Pion <Token>`__, plutôt que noir.

-  **Découvrir automatiquement le BdG** (*Autoshow Fog*)

   découvrira automatiquement le `Brouillard de Guerre <Fog_of_War>`__
   après le déplacement d'un `Pion <Token>`__ si ✓ coché.

.. _panneaux_de_macro:

Panneaux de Macro
-----------------

.. figure:: prefs_application_macropanels.jpg
   :alt: prefs_application_macropanels.jpg

   prefs_application_macropanels.jpg

-  **Par défaut : autoriser les joueurs à modifier les macros**
   (*Default: Allow Players to Edit Macros*)

   Pour qu'une macro soit considérée comme une `Macro de
   Confiance <Trusted_Macro>`__ (*Trusted Macro*), les joueurs ne
   doivent pas pouvoir la modifier. Ce paramètre détermine si une
   nouvelle macro sera par défaut éditable par les joueurs ou non.
   Désactiver ce paramètre peut être très utile si vous avez l'intention
   de créer de nombreuses macros de confiance.

.. _onglet_sons:

Onglet Sons
===========

|prefs_tab_sounds.png| |prefs_sounds_all.jpg|

-  **Jouer les sons système** (*Play system sounds*)

   Quand ce paramètre est ✓ coché, MapTool émettra un son lorsque du
   nouveau contenu est envoyé au panneau de chat.

-  **Seulement quand la fenêtre est active** (*Only when window not
   focused*)

   Si ✓ coché, lorsque du nouveau contenu est envoyé au panneau de chat,
   MapTool ne produira du son que si le fenêtre MapTool est active (a le
   focus).

`Category:MapTool <Category:MapTool>`__

.. |gridSquare.png| image:: gridSquare.png
.. |gridHorizontalHex.png| image:: gridHorizontalHex.png
.. |gridVerticalHex.png| image:: gridVerticalHex.png
.. |prefs_tab_accessibility.png| image:: prefs_tab_accessibility.png
.. |prefs_accessibility_all.jpg| image:: prefs_accessibility_all.jpg
.. |prefs_tab_sounds.png| image:: prefs_tab_sounds.png
.. |prefs_sounds_all.jpg| image:: prefs_sounds_all.jpg
