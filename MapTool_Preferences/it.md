__TOC__

## Scheda Interactions

![prefs_tab_interactions.png](prefs_tab_interactions.png
"prefs_tab_interactions.png")

### Maps

![prefs_interactions_maps.jpg](prefs_interactions_maps.jpg
"prefs_interactions_maps.jpg")

  - **New maps have Fog of War**

<!-- end list -->

  -
    Determina se le nuove maps hanno la [Nebbia di
    Guerra](Fog_of_War/it "wikilink") abilitata alla creazione. Se siete
    soliti usarla, potrebbe sembrare ovvio avere questa
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>casella
    spuntata; tuttavia, quando create più di una map per la campaign,
    spesso è utile disabilitare questa opzione per velocizzarne la
    lavorazione poiché anche come GM non potrete vedere tutto quello che
    è coperto dalla [Nebbia di Guerra](Fog_of_War/it "wikilink") (N.d.T.
    mica vero, la visuale viene solo ingrigita). Una volta completata la
    map, sarà un solo passo riabilitare la [Nebbia di
    Guerra](Fog_of_War/it "wikilink").

<!-- end list -->

  - **New maps visible to players**

<!-- end list -->

  -
    Determina se alla creazione di una nuova map questa deve essere
    impostata come visibile dai giocatori. Anche se ci sono eccezioni,
    tipicamente avere questa
    <span style="font-size: 24px; line-height: 1px; color: red; font-weight: bold; vertical-align: sub;">✓</span>
    casella non spuntata risulta la scelta ottimale; non rischierete di
    lasciare involontariamente la map visibile ai giocatori.

<!-- end list -->

  - **Default Grid Type**
      - **Square** ![gridSquare.png](gridSquare.png "gridSquare.png")
      - **Horizontal Hex**
        ![gridHorizontalHex.png](gridHorizontalHex.png
        "gridHorizontalHex.png")
      - **Vertical Hex** ![gridVerticalHex.png](gridVerticalHex.png
        "gridVerticalHex.png")

<!-- end list -->

  -
    Determina il tipo di griglia alla creazione di nuove maps. Siete
    liberi di creare maps senza alcun tipo di griglia, o anche un tipo
    di griglia diverso da quelli specificati qui, ma non potete
    scegliere come valore predefinito l'assenza di un qualsiasi tipo di
    griglia.

<!-- end list -->

  - **Default Grid Size**

<!-- end list -->

  -
    Rappresenta la quantità di pixel che volete MapTool utilizzi per
    disegnare le celle di una griglia ad una risoluzione completa
    (scalatura 1:1). Il valore predefinito è  pixels, risulta adeguato
    per molti computer, ma quelli di ultima generazione supportano
    tranquillamente dai  ai  pixels. Non ci sono limiti specifici di
    dimensioni, ma  e  pixels sono i valori più comunemente usati.
    Questa opzione determina anche quanto grande sia, alla depositazione
    su una map, un immagine impostata su Free-size e non ridimensionata
    manualmente.

<!-- end list -->

  - **Default Units Per Cell**

<!-- end list -->

  -
    Imposta l'ammontare di unità che ogni cella rappresenta. Sono
    chiamate ambiguamente "unità" perché è lasciato a noi decidere
    quello che rappresentano. Se volete che ogni cella rappresenti 5
    piedi, allora imposterete questo campo su . Se invece volete che
    rappresenti 4km imposterete . Questa opzione è usualmente chiamata
    *Distanza per Cella*.

<!-- end list -->

  - **Default Vision Distance**

<!-- end list -->

  -
    E' la massima distanza attraverso la quale un [PC
    Tokens](PC_Token "wikilink") può dissolvere la [Nebbia di
    Guerra](Fog_of_War/it "wikilink") dopo che le
    [Luci](Light/it "wikilink"), il [Campo Visivo](Sight/it "wikilink"),
    ed il [Livello di Blocco
    Visuale](Vision_Blocking_Layer/it "wikilink") siano stati
    considerati. E' importante sottolineare che questo valore è misurato
    in *Distanza per Cella*.

<!-- end list -->

  - **Movement metric**
      - **ONE_TWO_ONE**
      - **ONE_ONE_ONE**
      - **MANHATTAN**
      - **NO DIAGONALS**

<!-- end list -->

  -
    Determina come viene calcolata la modalità di movimento durante lo
    spostamento diagonale di un [Token/it](Token/it "wikilink"). Questo
    ha effetto sul valore totale della distanza percorsa mostrato sotto
    ad un [Token/it](Token/it "wikilink") quando lo si sposta, o quando
    si richiede la visualizzazione del suo percorso precedente (Ctrl+P);
    viene calcolato in base alla *Distanza per Cella*. **ONE_TWO_ONE**
    specifica che ogni due spostamenti diagonali il valore calcolato
    dell'ultima cella così raggiunta verrà raddoppiato.
    **ONE_ONE_ONE** specifica che i movimenti diagonali saranno
    calcolati nello stesso modo degli altri. **MANHATTAN** specifica che
    ogni movimento diagonale sarà calcolato come il doppio della
    *Distanza per Cella*. **NO DIAGONALS** specifica che i
    [Tokens](Token/it "wikilink") possano muoversi solo in direzioni non
    diagonali. L'impostazione **Movement metric** entrar in gioco solo
    quando si utilizza una griglia quadrata, per le esagonali il
    movimento in ogni direzione usa la *Distanza per Cella*.

### Tokens

![prefs_interactions_tokens.jpg](prefs_interactions_tokens.jpg
"prefs_interactions_tokens.jpg")

  - **Start Snap to Grid**

<!-- end list -->

  -
    Determines if [Tokens](Token "wikilink") will default to having
    **Snap to Grid**
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>checked.
    Having this setting
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>checked
    is optimal for maps that use a grid, but even on such maps there are
    cases when you might want to temporarily disable this setting(e.g.
    when placing a lot of "prop" [Tokens](Token "wikilink") on the
    Object layer while drawing a map).

<!-- end list -->

  - **New tokens visible to players**

<!-- end list -->

  -
    Determines if new [Tokens](Token "wikilink") have the **Visible**
    option
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>checked
    upon creation. The optimal setting for this really depends on your
    play style; if you have a lot of random encounters and build them
    during play, you may find it useful to have this setting disabled.

<!-- end list -->

  - **Duplicate Token Numbering**
      - **Increment**
      - **Random 2-digit**

<!-- end list -->

  -
    Will automatically append numbers to [Tokens](Token "wikilink") with
    duplicate names, upon creation. **Increment** will leave the first
    token unnumbered, but will number each duplicate after that,
    starting with the number  (e.g. Troll, Troll 1, Troll 2). **Random
    2-digit** will append a random two-digit number to the token name,
    even if there are no duplicates on the map yet. **Random 2-digit**
    might be considered the optimal setting, as it gives your players no
    indication of how many copies of that [Token](Token "wikilink") can
    be expected to exist.

<!-- end list -->

  - **Show Numbering on**
      - **Name**
      - **GM Name**
      - **Both**

<!-- end list -->

  -
    Specifies where the number that derived from **Duplicate Token
    Numbering** is applied. **Name** appends the number after the name
    (derived from **New Token Naming**). **GM Name** places the number
    within the *GM Name* field of the [Token](Token "wikilink") options.
    **Both** appends the number after the name, and places it within the
    *GM Name* field of the [Token](Token "wikilink") options. Due to odd
    behaviour that MapTool will display when handling tokens with the
    same name, it is recommended that you use **Name** or **Both**, but
    not **GM Name**.

<!-- end list -->

  - **New Token Naming**
      - **Use Filename**
      - **Use "Creature"**

<!-- end list -->

  -
    Determines what the name will be when creating a new
    [Token](Token "wikilink"), or what the *Name* field will be
    pre-filled with in a new [Token](Token "wikilink") dialog. **Use
    Filename** specifies that the name will be derived from the name of
    the file that was added to your Resource Library (e.g. if you add
    the file *uglytroll.jpg* to your Resource Library, tokens created
    from that image will begin with the name *uglytroll*). **Use
    "Creature"** defaults all new [Tokens](Token "wikilink") to being
    named "Creature" (without quotes).

<!-- end list -->

  - **Start Freesize**

<!-- end list -->

  -
    If you are using a map with a grid, [Tokens](Token "wikilink")
    typically default to the size of one grid cell upon creation. Having
    this setting
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>checked
    allows you to have them default to *Freesize*, which is very useful
    for when you're placing a lot of 'prop' [Tokens](Token "wikilink")
    on the Object layer while creating a map.

<!-- end list -->

  - **Show Dialog on New Token**

<!-- end list -->

  -
    When this setting is
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>checked,
    a *New Token* dialog will open when you drag an image onto the map,
    allowing you to set some options prior to creation. If you disable
    this setting, all new tokens will be created with the default
    settings derived from previous settings in this section.

<!-- end list -->

  - **Stat Sheet Portrait Size** *(Set to 0 to disable portaits)*

<!-- end list -->

  -
    Sets the width (in pixels) of the portrait that is displayed in the
    lower left corner of the map when mousing over certain
    [Tokens](Token "wikilink"); the image is resized proportionately. A
    portrait is displayed under a few different circumstances; if the
    [Token](Token "wikilink") has properties that are set to display on
    the stat sheet, and those properties have values, the portrait will
    display the token image. If the [Token](Token "wikilink") has a
    portrait image set, it will display with or without a stat sheet.
    Why might you want to set this to ? Besides the obvious reason of
    not displaying the portrait, you might want to use a stat sheet, but
    not want a portrait displayed with it; or perhaps you don't want to
    use a stat sheet or a portrait, but would like to have the portrait
    image 'slot' usable for other purposes, like inside a Dialog or
    Frame.

### Chat

![prefs_interactions_chat.jpg](prefs_interactions_chat.jpg
"prefs_interactions_chat.jpg")

  - **Show Avatar per line**

<!-- end list -->

  -
    The image for the impersonated token is shown next to any chat
    output it creates, when this is
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>checked.
    This is a client-side setting and does not effect any other clients
    connected to the same game.

<!-- end list -->

  - **Insert Smilies**

<!-- end list -->

  -
    Replaces common smiley(emoticon) character sequences with graphical
    smilies when this is
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>checked.
    If you use a lot of macros, it is recommended that you turn this
    off, as it could cause some complications if any of your macro code
    is interpreted as a smiley.

<!-- end list -->

  - **Use ToolTips for Inline Rolls**

<!-- end list -->

  -
    Sets the default display ([Display Roll
    Option](:Category:Display_Roll_Option "wikilink")) for rolls in the
    chat panel. Will use  if this is
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>checked,
    otherwise it will default to .

<!-- end list -->

  - **Trusted Prefix Background**

<!-- end list -->

  -
    Sets a custom background for macro output that comes from a [Trusted
    Macro](Trusted_Macro "wikilink").

<!-- end list -->

  - **Trusted Prefix Foreground**

<!-- end list -->

  -
    Sets a custom foreground (text color) for macro output that comes
    from a [Trusted Macro](Trusted_Macro "wikilink").

<!-- end list -->

  - **Time between autosaves**

<!-- end list -->

  -
    The amount of time in minutes between the autosaving of the chat
    log. This is not functional as of 1.3b54.

<!-- end list -->

  - **Autosave Chat Log Filename**

<!-- end list -->

  -
    The filename that will be used when automatically saving your chat
    log. This is not functional as of 1.3b54.

### Objects

![prefs_interactions_objects.jpg](prefs_interactions_objects.jpg
"prefs_interactions_objects.jpg")

  - **Start Snap to Grid**

<!-- end list -->

  -
    Tokens created on map's Object layer will automatically be set to
    **Snap to Grid** if this is
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>checked.

<!-- end list -->

  - **Start Freesize**

<!-- end list -->

  -
    Tokens created on a map's Object layer will automatically be set to
    **Freesize** if this is
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>checked.

### Backgrounds

![prefs_interactions_backgrounds.jpg](prefs_interactions_backgrounds.jpg
"prefs_interactions_backgrounds.jpg")

  - **Start Snap to Grid**

<!-- end list -->

  -
    Images dropped on a map's Background layer will automatically be set
    to **Snap to Grid**, if this is
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>checked.

<!-- end list -->

  - **Start Freesize**

<!-- end list -->

  -
    Images dropped on a map's Background layer will automatically be set
    to **Freesize**, if this is
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>checked.

### Facing

![prefs_interactions_facing.jpg](prefs_interactions_facing.jpg
"prefs_interactions_facing.jpg")

  - **On Edges**

<!-- end list -->

  -
    A token's facing will snap to the edges when
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>checked.
    Edges are the lines that make up a grid cell.

<!-- end list -->

  - **On Vertices**

<!-- end list -->

  -
    A token's facing will snap to the vertices when
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>checked.
    Vertices are the points that connect the lines that make up a grid
    cell.

## Accessibility Tab

![prefs_tab_accessibility.png](prefs_tab_accessibility.png
"prefs_tab_accessibility.png")
![prefs_accessibility_all.jpg](prefs_accessibility_all.jpg
"prefs_accessibility_all.jpg")

  - **Chat Font Size**

<!-- end list -->

  -
    The default size of the font in the chat panel; measured in points.

<!-- end list -->

  - **ToolTip Initial Delay**

<!-- end list -->

  -
    The time it takes for a tooltip to display when hovering the mouse
    over an element that possesses a tooltip; measured in miliseconds.

<!-- end list -->

  - **ToolTip Dismiss Delay**

<!-- end list -->

  -
    The time it takes for a tooltip to disappear when hovering the mouse
    over an element that possesses a tooltip; measured in miliseconds.

## Application Tab

![prefs_tab_application.png](prefs_tab_application.png
"prefs_tab_application.png")

### Save

![prefs_application_save.jpg](prefs_application_save.jpg
"prefs_application_save.jpg")

  - **Save Autorecover every \[ \] min**

<!-- end list -->

  -
    Saves a copy of your campaign in the interval specified. Unlike
    Autosave, this will not overwrite your campaign file, but rather
    create a new one every time it automatically saves.

<!-- end list -->

  - **Save reminder on close**

<!-- end list -->

  -
    Displays a dialog when attempting to close the program with unsaved
    changes to your campaign when
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>checked.

<!-- end list -->

  - **1.3b50 Compatability Mode**

<!-- end list -->

  -
    Due to some changes in how certain data is stored in the campaign
    file in versions after 1.3b50, they might not be compatible with
    version 1.3b50 and earlier. If this is
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>checked
    your campaign will be saved in the older format, allowing it to be
    opened in older versions, but losing some of the new features.

### Map Defaults

![prefs_application_mapdefaults.jpg](prefs_application_mapdefaults.jpg
"prefs_application_mapdefaults.jpg")

  - **Halo line width**

<!-- end list -->

  -
    Controls the width of the [Halo](Halo "wikilink") when it is
    displayed on a [Token](Token "wikilink").

<!-- end list -->

  - **Vision opacity**

<!-- end list -->

  -
    Areas that are no longer directly visible, but have previously had
    their [Fog of War](Fog_of_War "wikilink") exposed, will will be
    dimmed by layering a translucent black on top of them. This setting
    controls the opacity of the translucent black.

<!-- end list -->

  - **Use halo color for vision**

<!-- end list -->

  -
    Related to **Vision opacity**, if this setting is
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>checked,
    the translucent color layered on top of previously viewed areas will
    be the [Token's](Token "wikilink") [Halo](Halo "wikilink") color as
    opposed to black.

<!-- end list -->

  - **Autoshow Fog**

<!-- end list -->

  -
    Will automatically expose [Fog of War](Fog_of_War "wikilink") after
    moving a [Token](Token "wikilink") if
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>checked.

### Macro Panels

![prefs_application_macropanels.jpg](prefs_application_macropanels.jpg
"prefs_application_macropanels.jpg")

  - **Default: Allow Players to Edit Macros**

<!-- end list -->

  -
    In order for a macro to be considered a [Trusted
    Macro](Trusted_Macro "wikilink"), players must not be able to edit
    it. This setting determines if a new macro should default to
    allowing players to edit if
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>checked.
    Disabling this setting can be very useful if you intend to create a
    lot of macros that you intend to be trusted.

## Sounds Tab

![prefs_tab_sounds.png](prefs_tab_sounds.png "prefs_tab_sounds.png")
![prefs_sounds_all.jpg](prefs_sounds_all.jpg "prefs_sounds_all.jpg")

  - **Play system sounds**

<!-- end list -->

  -
    When
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>checked,
    MapTool will play a sound when new content is sent to the chat
    panel.

<!-- end list -->

  - **Only when window not focused**

<!-- end list -->

  -
    When
    <span style="font-size: 24px; line-height: 1px; color: green; font-weight: bold; vertical-align: sub;">✓</span>checked,
    the sound that MapTool plays when new content is sent to the chat
    panel will only play if MapTool is not the application that has
    focus.

[Category:MapTool](Category:MapTool "wikilink")