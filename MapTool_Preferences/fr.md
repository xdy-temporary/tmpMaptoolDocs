{{\#customtitle:Préférences de MapTool|Préférences de MapTool}}
__TOC__

## Onglet Interactions

![prefs_tab_interactions.png](prefs_tab_interactions.png
"prefs_tab_interactions.png")

### Cartes

![prefs_interactions_maps.jpg](prefs_interactions_maps.jpg
"prefs_interactions_maps.jpg")

  - **Les nouvelles cartes ont le Brouillard de Guerre** (*New maps have
    Fog of War*)

<!-- end list -->

  -
    Détermine si les nouvelles cartes doivent avoir le [Brouillard de
    Guerre](Fog_of_War "wikilink") activé à la création. Si vous
    utilisez le [Brouillard de Guerre](Fog_of_War "wikilink"), cela
    semble évident de
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>
    l'activer ; cependant, pendant que l'on crée plusieurs cartes pour
    une nouvelle campagne, cela semble souvent utile de le désactiver
    pour faciliter la modification des cartes, étant donné que même en
    tant que MJ, vous ne verrez pas complètement une carte couverte du
    [Brouillard de Guerre](Fog_of_War "wikilink"). Lorsque la carte est
    terminée, il est simple de réactiver le [Brouillard de
    Guerre](Fog_of_War "wikilink") sur celle-ci.

<!-- end list -->

  - **Les nouvelles cartes sont visibles par les joueurs** (*New maps
    visible to players*)

<!-- end list -->

  -
    Indique si les nouvelles cartes doivent être marquées 'Visible par
    les joueurs' (*Player Visible*) à la création. Bien qu'il y ait des
    exceptions, avoir cette option
    <span style="font-size: 24px; line-height: 1px; color: red; font-weight: bold; vertical-align: sub;">✓</span>
    décochée est un paramétrage optimal ; de cette façon, vous ne
    laissez pas involontairement une carte accessible aux joueurs.

<!-- end list -->

  - **Type de Grille par défaut** (*Default Grid Type*)
      - **Cases** (*Square*) ![gridSquare.png](gridSquare.png
        "gridSquare.png")
      - **Hexagones horizontaux** (*Horizontal Hex*)
        ![gridHorizontalHex.png](gridHorizontalHex.png
        "gridHorizontalHex.png")
      - **Hexagones verticaux** (*Vertical Hex*)
        ![gridVerticalHex.png](gridVerticalHex.png
        "gridVerticalHex.png")

<!-- end list -->

  -
    détermine le type de grille proposé par défaut lors de la création
    d'une carte. Vous êtes libre de créer des cartes sans type de
    grille, mais aussi de type différent de celui spécifié ici, mais
    vous ne pouvez pas mettre le type par défaut proposé à "Sans
    grille".

<!-- end list -->

  - **Taille de grille par défaut** (*Default Grid Size*)

<!-- end list -->

  -
    représente le nombre de pixels que vous voulez que MapTool utilise
    pour dessiner chaque cellule de la grille, à la résolution maximum.
    Le paramétrage par défaut de  pixels est idéal pour la plupart des
    ordinateurs, mais les ordinateurs haut de gamme peuvent gérer  ou
    même  pixels. Il n'y aucun pré requis pour utiliser des tailles
    spécifiques, mais  et  pixels sont utilisés couramment. Cette
    préférence déterminera aussi quelle taille prendre une image
    lorsqu'elle sera placée sur la carte ; si elle n'est pas paramétrée
    en taille libre (*Free-size*) et pas manuellement redimensionnée.

<!-- end list -->

  - **Nombre d'unités par cellule par défaut** (*Default Units Per
    Cell*)

<!-- end list -->

  -
    indique le nombre d'unités de mesure que représente chaque cellule
    de la grille. L'ambigüe "unité" est utilisé dans ce cas parce que
    VOUS décidez ce qu'il représente. Si vous voulez que chaque cellule
    représente 5 pieds (1,5m) comme dans D\&D3, ce paramètre devra être
    saisi à . Si voulez que chaque cellule représente une case comme
    dans D\&D4, saisissez . Si vous voulez que chaque cellule représente
    4 kilomètres, choisissez , etc... Cette unité est souvent mentionnée
    comme la *Distance par Cellule* (*Distance Per Cell*).

<!-- end list -->

  - **Distance de vision par défaut** (*Default Vision Distance*)

<!-- end list -->

  -
    La distance maximum à laquelle les [Pions de
    joueurs](PC_Token "wikilink") peuvent dissiper le [Brouillard de
    guerre](Fog_of_War "wikilink") après que les
    [lumières](Light "wikilink"), [vues](Sight "wikilink"), et les
    [calques de blocage de vision
    (VBL)](Vision_Blocking_Layer "wikilink") aient été pris en compte.
    Il est important de noter que ce paramètre est mesuré en *Distance
    par Cellule* (cf. ci-dessus).

<!-- end list -->

  - **Métrique de mouvement** (*Movement metric*)
      - **Un_Deux_Un** (*ONE_TWO_ONE*)
      - **Un_Un_Un** (*ONE_ONE_ONE*)
      - **MANHATTAN**
      - **Pas de diogonales** (*NO DIAGONALS*)

<!-- end list -->

  -
    détermine comment les mouvements doivent être calculés quand un
    [Pion](Token "wikilink") se déplace en diagonal. Cela affecte le
    total de distance parcourue affiché sous un [Pion](Token "wikilink")
    quand il est en train d'être déplacé ; cela est calculé en *Distance
    par Cellule* (*Distance Per Cell*). **ONE_TWO_ONE** spécifie que
    chaque diagonal fera deux fois la *Distance par Cellule*.
    **ONE_ONE_ONE** : chaque diagonale fait une *Distance par
    Cellule*. **MANHATTAN** spécifie que chaque diagonal fera deux fois
    la *Distance par Cellule*. **NO DIAGONALS** indique que les
    [Pions](Token "wikilink") ne peuvent pas se déplacer en diagonale.
    Le paramètre **Movement metric** n'a d'influence en jeu que sur les
    cartes utilisant une grille en case ; les cartes avec une grille
    hexagonale calculent les mouvements dans n'importe quelle direction
    en ''Distance par Cellule'.

### Pions

![prefs_interactions_tokens.jpg](prefs_interactions_tokens.jpg
"prefs_interactions_tokens.jpg")

  - **Aligner sur la grille** (*Start Snap to Grid*)

<!-- end list -->

  -
    Détermine si les [Pions](Token "wikilink") seront, par défaut,
    alignés sur la grille (**Snap to Grid**
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>checked).
    Avoir ce paramètre
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>
    coché est optimal pour les cartes utilisant une grille, mais même
    sur de telles cartes, vous pouvez vouloir temporairement désactiver
    cette propriété (par exemple, lorsque l'on place beaucoup de pions
    "d'accessoires" sur le calque Objet pendant que l'on dessine la
    carte).

<!-- end list -->

  - **Les nouveaux pions sont visibles par les joueurs** (*New tokens
    visible to players*)

<!-- end list -->

  -
    Indique si les nouveaux [Pions](Token "wikilink") ont la propriété
    **Visible**
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>
    activée à la création. Le paramétrage optimal dépend de votre style
    de jeu ; si vous avez de nombreuses rencontres aléatoires et les
    créez en cours de partie, il pourra vous être utile de désactiver
    cette option.

<!-- end list -->

  - **Numérotation des pions dupliqués** (*Duplicate Token Numbering*)
      - **Incrémenter** (*Increment*)
      - **2 chiffres aléatoires** (*Random 2-digit*)

<!-- end list -->

  -
    va automatiquement ajouter 2 chiffres aux [Pions](Token "wikilink")
    ayant un nom dupliqué, lors de la création. **Incrémenter**
    n'ajoutera pas de chiffre au premier pion, mais numérotera chaque
    copie après cela, en démarrant au chiffre  (ex: Troll, Troll 1,
    Troll 2). **2 chiffres aléatoires** ajoutera un nombre aléatoire à
    deux chiffres au nom du pion, même s'il n'y a pas encore de doublon
    sur la carte. **2 chiffres aléatoires** pourrait être considéré le
    paramétrage optimal, car il ne donnera à vos joueurs aucune
    indication sur le nombre exact de copies d'un Pion.

<!-- end list -->

  - **Affiche la numérotation sur** (*Show Numbering on*)
      - **le Nom** (*Name*)
      - **le Nom MJ** (*GM Name*)
      - **les Deux** (*Both*)

<!-- end list -->

  -
    détermine comment le numéro issu du paramètre **Numérotation des
    pions dupliqués** est appliqué. **le Nom** ajoute le numéro après le
    nom (lui-même déterminé par **Nommage d'un Nouveau Pion**). **le Nom
    MJ** place le numéro dans le champ Nom MJ des options du pion. **Les
    Deux** ajoute le numéro après le nom ET place le numéro dans le
    champ Nom MJ des options du pion. Du fait d'un comportement étrange
    de MapTool lorsqu'il doit gérer deux pions avec le même nom, il est
    recommandé que vous utilisiez **Nom** ou **les Deux** mais jamais
    **le Nom MJ**.

<!-- end list -->

  - **Nommage d'un nouveau pion** (*New Token Naming*)
      - **Utiliser le nom de fichier** (*Use Filename*)
      - **Utiliser "Créature"** (*Use "Creature"*)

<!-- end list -->

  -
    détermine quel sera le nom d'un nouveau pion créé, ou comment sera
    pré rempli le champ *Nom* du dialogue de création de nouveau pion.
    **Utiliser le nom de fichier** indique que le nom du pion sera
    déduit du nom du fichier qui a été ajouté à votre bibliothèque de
    ressources (ex : si vous avez ajouter le fichier *gobelinlaid.jpg* à
    votre bibliothèque de ressources, les pions créés à partir de cette
    image auront un nom commençant par *gobelinlaid*). **Utiliser
    "Créature"** fera que le nom de tous les nouveaux pions créés
    commencera par "Creature" (sans les guillemets).

<!-- end list -->

  - **Taille réelle** (*Start Freesize*)

<!-- end list -->

  -
    Si vous utilisez une carte avec une grille, les
    [Pions](Token "wikilink") ajoutés seront par défaut de la taille
    d'une cellule. En cochant ce paramètre
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>,
    les pions seront créés à la taille réelle de l'image, ce qui est
    très utile pour placer des accessoires sur le calque d'Objet ou des
    éléments de décors à l'échelle sur le calque de fond.

<!-- end list -->

  - **Afficher le dialogue à la création d'un Pion** (*Show Dialog on
    New Token*)

<!-- end list -->

  -
    Quand cette préférence est
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>cochée,
    une fenêtre *Nouveau Pion* (*New Token*) s'ouvrira lorsque vous
    ferez glisser une image sur la carte, vous permettant de modifier
    quelques options avant la création. Si vous désactivez ceci, tous
    les nouveaux pions seront créés avec le paramétrage par défaut
    déterminé par les différentes préférences décrites dans cette
    section.

<!-- end list -->

  - **Taille du portrait de la Feuille de Statistiques** ('' Stat Sheet
    Portrait Size'')

<!-- end list -->

  -
    définit la taille en pixels) du portrait qui est affiché dans le
    coin inférieur droit de la carte lorsque la souris survole certains
    Pions ; l'image est redimensionnée proportionnellement. Un portrait
    est affiché sous quelques conditions différentes : si le Pion a des
    propriétés qui sont définies pour être affichées sur la feuille de
    statistiques et que ces propriétés ont une valeur, le portrait
    affichera l'image du pion. Si le pion a une image de portrait
    définie, il l'affichera avec ou sans la feuille de stats.

<!-- end list -->

  - **Mettre à zéro pour désactiver le portrait** (*Set to 0 to disable
    portaits*)

<!-- end list -->

  -
    Pourquoi voudriez-vous paramétrer ceci à  ? Au-delà de l'évidence
    (ne pas afficher le portrait), vous pourriez vouloir utiliser la
    feuille de stats, mais sans qu'un portrait apparaisse avec ; ou
    peut-être ne voulez pas utiliser ni de portrait ni de feuille de
    stats mais voulez utiliser "l'emplacement" de l'image de portrait
    pour d'autres utilisations, dans un Dialog ou une Frame par exemple.

### Chat

![prefs_interactions_chat.jpg](prefs_interactions_chat.jpg
"prefs_interactions_chat.jpg")

  - **Afficher l'avatar à chaque ligne** (*Show Avatar per line*)

<!-- end list -->

  -
    l'image du pion personnifié (*impersonnated*) est montrée à côté de
    chaque paragraphe de chat qu'il produit, quand cette option est
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>
    cochée. Ceci est un paramétrage local du côté client et n'affecte
    pas les autres joueurs connectés à la même partie.

<!-- end list -->

  - **Insérer les émoticones** (*Insert Smilies*)

<!-- end list -->

  -
    remplace les suites de caractères d'émoticones courants par leur
    version graphique quand cette option est
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>
    cochée. Si vous utilisez de nombreuses macros, il est recommandé de
    désactiver cette option, qui peut poser problème si n'importe quelle
    portion de votre code de macro peut être interprété comme un
    émoticone.

<!-- end list -->

  - **Utiliser l'info-bulle pour les lancer** (*Use ToolTips for Inline
    Rolls*)

<!-- end list -->

  -
    détermine quel est l'affichage par défaut ([Options d'affichage de
    lancer](:Category:Display_Roll_Option "wikilink")) pour les lancers
    de dés dans le chat. Utilisera  si cette option est cochée
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>
    cochée, sinon par défaut utilisera .

<!-- end list -->

  - **Couleur de fond du préfixe pour les macros de confiance**
    (*Trusted Prefix Background*)

<!-- end list -->

  -
    détermine une couleur de fond personnalisée pour l'affichage des
    textes issu de [Macro de Confiance](Trusted_Macro "wikilink").

<!-- end list -->

  - **Couleur de texte du préfixe pour les macros de confiance**
    (*Trusted Prefix Foreground*)

<!-- end list -->

  -
    détermine une couleur de texte personnalisée pour l'affichage des
    textes issu de [Macro de Confiance](Trusted_Macro "wikilink").

<!-- end list -->

  - **Délai entre les sauvegardes automatiques** (*Time between
    autosaves*)

<!-- end list -->

  -
    Nombre de minutes entre deux sauvegardes automatiques de
    l'historique du chat. Cette fonction n'est pas active en 1.3b54.

<!-- end list -->

  - **Fichier de sauvegarde automatique du chat** (*Autosave Chat Log
    Filename*)

<!-- end list -->

  -
    Nom du fichier qui sera utilisé pour sauvegarder automatiquement
    l'historique du chat. Cette fonction n'est pas active en 1.3b54.

### Objets

![prefs_interactions_objects.jpg](prefs_interactions_objects.jpg
"prefs_interactions_objects.jpg")

  - **Aligner sur la griller** (*Start Snap to Grid*)

<!-- end list -->

  -
    Détermine si les Pions créés sur le calque "object" seront, par
    défaut, alignés sur la grille (Snap to Grid
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>).

<!-- end list -->

  - **Taille réelle** (*Start Freesize*)

<!-- end list -->

  -
    Si vous utilisez une carte avec une grille, les Pions ajoutés sur le
    calque "object" seront par défaut de la taille d'une cellule. En
    cochant ce paramètre
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>,
    les pions seront créés à la taille réelle de l'image.

### Backgrounds

![prefs_interactions_backgrounds.jpg](prefs_interactions_backgrounds.jpg
"prefs_interactions_backgrounds.jpg")

  - **Aligner sur la griller** (*Start Snap to Grid*)

<!-- end list -->

  -
    Détermine si les Pions créés sur le calque "Background" seront, par
    défaut, alignés sur la grille (Snap to Grid
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>).

<!-- end list -->

  - **Taille réelle** (*Start Freesize*)

<!-- end list -->

  -
    Si vous utilisez une carte avec une grille, les Pions ajoutés sur le
    calque "Background" seront par défaut de la taille d'une cellule. En
    cochant ce paramètre
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>,
    les pions seront créés à la taille réelle de l'image.

### Orientation (Facing)

![prefs_interactions_facing.jpg](prefs_interactions_facing.jpg
"prefs_interactions_facing.jpg")

  - **Sur les lignes** (*On Edges*)

<!-- end list -->

  -
    L'orientation (*facing*) d'un Pion s'alignera sur les côtés des
    cellules quand ce paramètre est coché
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>.

<!-- end list -->

  - **Sur les angles** (*On Vertices*)

<!-- end list -->

  -
    L'orientation (*facing*) d'un Pion s'alignera sur les angles d'une
    cellule quand ce paramètre est coché
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>.

## Onglet Accessibilité (Accessibility)

![prefs_tab_accessibility.png](prefs_tab_accessibility.png
"prefs_tab_accessibility.png")
![prefs_accessibility_all.jpg](prefs_accessibility_all.jpg
"prefs_accessibility_all.jpg")

  - **Taille de la police** (*Chat Font Size*)

<!-- end list -->

  -
    Taille par défaut de la police dans le panneau de chat, mesurée en
    points.

<!-- end list -->

  - **Délai initial des Infos-bulles** (*ToolTip Initial Delay*)

<!-- end list -->

  -
    Temps nécessaire pour afficher une info-bulle lorsque la souris
    survole un élément possédant une info-bulle, mesurée en millièmes de
    seconde.

<!-- end list -->

  - **Délai de disparition des Info-bulles** (*ToolTip Dismiss Delay*)

<!-- end list -->

  -
    Temps nécessaire pour cacher une info-bulle lorsque la souris ne
    survole plus un élément possédant une info-bulle, mesurée en
    millièmes de seconde.

## Application Tab

![prefs_tab_application.png](prefs_tab_application.png
"prefs_tab_application.png")

### Sauvegarde (Save)

![prefs_application_save.jpg](prefs_application_save.jpg
"prefs_application_save.jpg")

  - **Sauvegarder une récupération automatique toutes les \[ \]
    minutes** (*Save Autorecover every \[ \] min*)

<!-- end list -->

  -
    Sauvegarde une copie de votre campagne dans l'intervalle spécifié.
    Contrairement à la sauvegarde automatique, cela n'écrira pas par
    dessus votre fichier de campagne, mais créera plutôt un nouveau
    fichier à chaque fois.

<!-- end list -->

  - **Rappel de sauvegarde à la fermeture** (*Save reminder on close*)

<!-- end list -->

  -
    Affiche un dialogue lorsque l'on tente de fermer MapTool et que des
    modifications non enregistrées ont été faites à la campagne, si
    cette option est cochée
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>.

<!-- end list -->

  - **Compatibilité 1.3b50** (*1.3b50 Compatability Mode*)

<!-- end list -->

  -
    du fait de certains changements dans la façon d'enregistrer
    certaines données au sein des fichiers de campagne, ces fichiers
    peuvent ne pas être compatibles avec des versions 1.3b50 et
    antérieures. Si ce paramètre est coché
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>,
    votre campagne sera enregistrée dans l'ancien format, compatible
    avec d'anciennes versions de MapTool mais perdant quelques nouvelles
    fonctionnalités.

### Valeurs par défaut de la Carte (Map Defaults)

![prefs_application_mapdefaults.jpg](prefs_application_mapdefaults.jpg
"prefs_application_mapdefaults.jpg")

  - **Épaisseur de la ligne de Halo** (*Halo line width*)

<!-- end list -->

  -
    contrôle l'épaisseur du [Halo](Halo "wikilink") lorsqu'il est
    affiché sur un [Pion](Token "wikilink").

<!-- end list -->

  - **Opacité de la Vision** (*Vision opacity*)

<!-- end list -->

  -
    les zones qui ne sont pas directement visibles, mais qui n'ont plus
    de brouillard de guerre, seront obscurcies en les recouvrant d'un
    calque noir semi-translucide. Ce paramètre contrôle l'opacité de ce
    noir translucide.

<!-- end list -->

  - **Utiliser la couleur du halo pour la vision** (*Use halo color for
    vision*)

<!-- end list -->

  -
    lié à **Opacité de la Vision**. Si ce paramètre est coché
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>,
    le calque translucide au-dessus des zones déjà vues sera de la
    couleur du [Halo](Halo "wikilink") du [Pion](Token "wikilink"),
    plutôt que noir.

<!-- end list -->

  - **Découvrir automatiquement le BdG** (*Autoshow Fog*)

<!-- end list -->

  -
    découvrira automatiquement le [Brouillard de
    Guerre](Fog_of_War "wikilink") après le déplacement d'un
    [Pion](Token "wikilink") si
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>
    coché.

### Panneaux de Macro

![prefs_application_macropanels.jpg](prefs_application_macropanels.jpg
"prefs_application_macropanels.jpg")

  - **Par défaut : autoriser les joueurs à modifier les macros**
    (*Default: Allow Players to Edit Macros*)

<!-- end list -->

  -
    Pour qu'une macro soit considérée comme une [Macro de
    Confiance](Trusted_Macro "wikilink") (*Trusted Macro*), les joueurs
    ne doivent pas pouvoir la modifier. Ce paramètre détermine si une
    nouvelle macro sera par défaut éditable par les joueurs ou non.
    Désactiver ce paramètre peut être très utile si vous avez
    l'intention de créer de nombreuses macros de confiance.

## Onglet Sons

![prefs_tab_sounds.png](prefs_tab_sounds.png "prefs_tab_sounds.png")
![prefs_sounds_all.jpg](prefs_sounds_all.jpg "prefs_sounds_all.jpg")

  - **Jouer les sons système** (*Play system sounds*)

<!-- end list -->

  -
    Quand ce paramètre est
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>
    coché, MapTool émettra un son lorsque du nouveau contenu est envoyé
    au panneau de chat.

<!-- end list -->

  - **Seulement quand la fenêtre est active** (*Only when window not
    focused*)

<!-- end list -->

  -
    Si
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>
    coché, lorsque du nouveau contenu est envoyé au panneau de chat,
    MapTool ne produira du son que si le fenêtre MapTool est active (a
    le focus).

[Category:MapTool](Category:MapTool "wikilink")