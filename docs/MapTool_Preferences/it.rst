.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{Languages|MapTool Preferences}}

.. raw:: mediawiki

   {{note|'''Note Importanti:''' Ci sono preferenze relative alle map che consentono di preconfigurare i valori di quelle create ex-novo. Sebbene abbiate la possibilità di cambiare queste preferenze durante la creazione di una map, alcune di queste non possono più essere cambiate una volta che la mappa è stata creta. Questo è il comportamento delle versioni 1.3b56 e precendenti. Le Preferences di questo tipo saranno contrassegnate da un {{mark}}  '''N.d.T.:''' [[Dalla_versione_1.3b75_tutte_le_preferences_della_map_si_possono_modificare_in_qualsiasi_momento_e_quindi_le_affermazioni_precedenti_non_sono_più_valide.|Dalla versione 1.3b75 tutte le preferences della map si possono modificare in qualsiasi momento e quindi le affermazioni precedenti non sono più valide.]]
   <br><br>'''Nota:''' Tutti gli screenshots in questo articolo sono mostrati con i valori predefiniti, ma non sono per forza le preferenze ''raccommandate'' per voi.}}

.. raw:: mediawiki

   {{Beginner}}

__TOC__

.. _scheda_interactions:

Scheda Interactions
===================

.. figure:: prefs_tab_interactions.png
   :alt: prefs_tab_interactions.png

   prefs_tab_interactions.png

Maps
----

.. figure:: prefs_interactions_maps.jpg
   :alt: prefs_interactions_maps.jpg

   prefs_interactions_maps.jpg

-  **New maps have Fog of War**

   Determina se le nuove maps hanno la `Nebbia di
   Guerra <Fog_of_War/it>`__ abilitata alla creazione. Se siete soliti
   usarla, potrebbe sembrare ovvio avere questa ✓casella spuntata;
   tuttavia, quando create più di una map per la campaign, spesso è
   utile disabilitare questa opzione per velocizzarne la lavorazione
   poiché anche come GM non potrete vedere tutto quello che è coperto
   dalla `Nebbia di Guerra <Fog_of_War/it>`__ (N.d.T. mica vero, la
   visuale viene solo ingrigita). Una volta completata la map, sarà un
   solo passo riabilitare la `Nebbia di Guerra <Fog_of_War/it>`__.

-  **New maps visible to players**

   Determina se alla creazione di una nuova map questa deve essere
   impostata come visibile dai giocatori. Anche se ci sono eccezioni,
   tipicamente avere questa ✓ casella non spuntata risulta la scelta
   ottimale; non rischierete di lasciare involontariamente la map
   visibile ai giocatori.

-  **Default Grid Type**\ 

   -  **Square** |gridSquare.png|
   -  **Horizontal Hex** |gridHorizontalHex.png|
   -  **Vertical Hex** |gridVerticalHex.png|

   Determina il tipo di griglia alla creazione di nuove maps. Siete
   liberi di creare maps senza alcun tipo di griglia, o anche un tipo di
   griglia diverso da quelli specificati qui, ma non potete scegliere
   come valore predefinito l'assenza di un qualsiasi tipo di griglia.

-  **Default Grid Size**\ 

   Rappresenta la quantità di pixel che volete MapTool utilizzi per
   disegnare le celle di una griglia ad una risoluzione completa
   (scalatura 1:1). Il valore predefinito è pixels, risulta adeguato per
   molti computer, ma quelli di ultima generazione supportano
   tranquillamente dai ai pixels. Non ci sono limiti specifici di
   dimensioni, ma e pixels sono i valori più comunemente usati. Questa
   opzione determina anche quanto grande sia, alla depositazione su una
   map, un immagine impostata su Free-size e non ridimensionata
   manualmente.

-  **Default Units Per Cell**\ 

   Imposta l'ammontare di unità che ogni cella rappresenta. Sono
   chiamate ambiguamente "unità" perché è lasciato a noi decidere quello
   che rappresentano. Se volete che ogni cella rappresenti 5 piedi,
   allora imposterete questo campo su . Se invece volete che rappresenti
   4km imposterete . Questa opzione è usualmente chiamata *Distanza per
   Cella*.

-  **Default Vision Distance**\ 

   E' la massima distanza attraverso la quale un `PC
   Tokens <PC_Token>`__ può dissolvere la `Nebbia di
   Guerra <Fog_of_War/it>`__ dopo che le `Luci <Light/it>`__, il `Campo
   Visivo <Sight/it>`__, ed il `Livello di Blocco
   Visuale <Vision_Blocking_Layer/it>`__ siano stati considerati. E'
   importante sottolineare che questo valore è misurato in *Distanza per
   Cella*.

-  **Movement metric**

   -  **ONE_TWO_ONE**
   -  **ONE_ONE_ONE**
   -  **MANHATTAN**
   -  **NO DIAGONALS**

   Determina come viene calcolata la modalità di movimento durante lo
   spostamento diagonale di un `Token/it <Token/it>`__. Questo ha
   effetto sul valore totale della distanza percorsa mostrato sotto ad
   un `Token/it <Token/it>`__ quando lo si sposta, o quando si richiede
   la visualizzazione del suo percorso precedente (Ctrl+P); viene
   calcolato in base alla *Distanza per Cella*. **ONE_TWO_ONE**
   specifica che ogni due spostamenti diagonali il valore calcolato
   dell'ultima cella così raggiunta verrà raddoppiato. **ONE_ONE_ONE**
   specifica che i movimenti diagonali saranno calcolati nello stesso
   modo degli altri. **MANHATTAN** specifica che ogni movimento
   diagonale sarà calcolato come il doppio della *Distanza per Cella*.
   **NO DIAGONALS** specifica che i `Tokens <Token/it>`__ possano
   muoversi solo in direzioni non diagonali. L'impostazione **Movement
   metric** entrar in gioco solo quando si utilizza una griglia
   quadrata, per le esagonali il movimento in ogni direzione usa la
   *Distanza per Cella*.

Tokens
------

.. figure:: prefs_interactions_tokens.jpg
   :alt: prefs_interactions_tokens.jpg

   prefs_interactions_tokens.jpg

-  **Start Snap to Grid**

   Determines if `Tokens <Token>`__ will default to having **Snap to
   Grid** ✓checked. Having this setting ✓checked is optimal for maps
   that use a grid, but even on such maps there are cases when you might
   want to temporarily disable this setting(e.g. when placing a lot of
   "prop" `Tokens <Token>`__ on the Object layer while drawing a map).

-  **New tokens visible to players**

   Determines if new `Tokens <Token>`__ have the **Visible** option
   ✓checked upon creation. The optimal setting for this really depends
   on your play style; if you have a lot of random encounters and build
   them during play, you may find it useful to have this setting
   disabled.

-  **Duplicate Token Numbering**

   -  **Increment**
   -  **Random 2-digit**

   Will automatically append numbers to `Tokens <Token>`__ with
   duplicate names, upon creation. **Increment** will leave the first
   token unnumbered, but will number each duplicate after that, starting
   with the number (e.g. Troll, Troll 1, Troll 2). **Random 2-digit**
   will append a random two-digit number to the token name, even if
   there are no duplicates on the map yet. **Random 2-digit** might be
   considered the optimal setting, as it gives your players no
   indication of how many copies of that `Token <Token>`__ can be
   expected to exist.

-  **Show Numbering on**

   -  **Name**
   -  **GM Name**
   -  **Both**

   Specifies where the number that derived from **Duplicate Token
   Numbering** is applied. **Name** appends the number after the name
   (derived from **New Token Naming**). **GM Name** places the number
   within the *GM Name* field of the `Token <Token>`__ options. **Both**
   appends the number after the name, and places it within the *GM Name*
   field of the `Token <Token>`__ options. Due to odd behaviour that
   MapTool will display when handling tokens with the same name, it is
   recommended that you use **Name** or **Both**, but not **GM Name**.

-  **New Token Naming**

   -  **Use Filename**
   -  **Use "Creature"**

   Determines what the name will be when creating a new
   `Token <Token>`__, or what the *Name* field will be pre-filled with
   in a new `Token <Token>`__ dialog. **Use Filename** specifies that
   the name will be derived from the name of the file that was added to
   your Resource Library (e.g. if you add the file *uglytroll.jpg* to
   your Resource Library, tokens created from that image will begin with
   the name *uglytroll*). **Use "Creature"** defaults all new
   `Tokens <Token>`__ to being named "Creature" (without quotes).

-  **Start Freesize**

   If you are using a map with a grid, `Tokens <Token>`__ typically
   default to the size of one grid cell upon creation. Having this
   setting ✓checked allows you to have them default to *Freesize*, which
   is very useful for when you're placing a lot of 'prop'
   `Tokens <Token>`__ on the Object layer while creating a map.

-  **Show Dialog on New Token**

   When this setting is ✓checked, a *New Token* dialog will open when
   you drag an image onto the map, allowing you to set some options
   prior to creation. If you disable this setting, all new tokens will
   be created with the default settings derived from previous settings
   in this section.

-  **Stat Sheet Portrait Size** *(Set to 0 to disable portaits)*

   Sets the width (in pixels) of the portrait that is displayed in the
   lower left corner of the map when mousing over certain
   `Tokens <Token>`__; the image is resized proportionately. A portrait
   is displayed under a few different circumstances; if the
   `Token <Token>`__ has properties that are set to display on the stat
   sheet, and those properties have values, the portrait will display
   the token image. If the `Token <Token>`__ has a portrait image set,
   it will display with or without a stat sheet. Why might you want to
   set this to ? Besides the obvious reason of not displaying the
   portrait, you might want to use a stat sheet, but not want a portrait
   displayed with it; or perhaps you don't want to use a stat sheet or a
   portrait, but would like to have the portrait image 'slot' usable for
   other purposes, like inside a Dialog or Frame.

Chat
----

.. figure:: prefs_interactions_chat.jpg
   :alt: prefs_interactions_chat.jpg

   prefs_interactions_chat.jpg

-  **Show Avatar per line**

   The image for the impersonated token is shown next to any chat output
   it creates, when this is ✓checked. This is a client-side setting and
   does not effect any other clients connected to the same game.

-  **Insert Smilies**

   Replaces common smiley(emoticon) character sequences with graphical
   smilies when this is ✓checked. If you use a lot of macros, it is
   recommended that you turn this off, as it could cause some
   complications if any of your macro code is interpreted as a smiley.

-  **Use ToolTips for Inline Rolls**

   Sets the default display (`Display Roll
   Option <:Category:Display_Roll_Option>`__) for rolls in the chat
   panel. Will use if this is ✓checked, otherwise it will default to .

-  **Trusted Prefix Background**

   Sets a custom background for macro output that comes from a `Trusted
   Macro <Trusted_Macro>`__.

-  **Trusted Prefix Foreground**

   Sets a custom foreground (text color) for macro output that comes
   from a `Trusted Macro <Trusted_Macro>`__.

-  **Time between autosaves**

   The amount of time in minutes between the autosaving of the chat log.
   This is not functional as of 1.3b54.

-  **Autosave Chat Log Filename**

   The filename that will be used when automatically saving your chat
   log. This is not functional as of 1.3b54.

Objects
-------

.. figure:: prefs_interactions_objects.jpg
   :alt: prefs_interactions_objects.jpg

   prefs_interactions_objects.jpg

-  **Start Snap to Grid**

   Tokens created on map's Object layer will automatically be set to
   **Snap to Grid** if this is ✓checked.

-  **Start Freesize**

   Tokens created on a map's Object layer will automatically be set to
   **Freesize** if this is ✓checked.

Backgrounds
-----------

.. figure:: prefs_interactions_backgrounds.jpg
   :alt: prefs_interactions_backgrounds.jpg

   prefs_interactions_backgrounds.jpg

-  **Start Snap to Grid**

   Images dropped on a map's Background layer will automatically be set
   to **Snap to Grid**, if this is ✓checked.

-  **Start Freesize**

   Images dropped on a map's Background layer will automatically be set
   to **Freesize**, if this is ✓checked.

Facing
------

.. figure:: prefs_interactions_facing.jpg
   :alt: prefs_interactions_facing.jpg

   prefs_interactions_facing.jpg

-  **On Edges**

   A token's facing will snap to the edges when ✓checked. Edges are the
   lines that make up a grid cell.

-  **On Vertices**

   A token's facing will snap to the vertices when ✓checked. Vertices
   are the points that connect the lines that make up a grid cell.

.. _accessibility_tab:

Accessibility Tab
=================

|prefs_tab_accessibility.png| |prefs_accessibility_all.jpg|

-  **Chat Font Size**

   The default size of the font in the chat panel; measured in points.

-  **ToolTip Initial Delay**

   The time it takes for a tooltip to display when hovering the mouse
   over an element that possesses a tooltip; measured in miliseconds.

-  **ToolTip Dismiss Delay**

   The time it takes for a tooltip to disappear when hovering the mouse
   over an element that possesses a tooltip; measured in miliseconds.

.. _application_tab:

Application Tab
===============

.. figure:: prefs_tab_application.png
   :alt: prefs_tab_application.png

   prefs_tab_application.png

Save
----

.. figure:: prefs_application_save.jpg
   :alt: prefs_application_save.jpg

   prefs_application_save.jpg

-  **Save Autorecover every [ ] min**

   Saves a copy of your campaign in the interval specified. Unlike
   Autosave, this will not overwrite your campaign file, but rather
   create a new one every time it automatically saves.

-  **Save reminder on close**

   Displays a dialog when attempting to close the program with unsaved
   changes to your campaign when ✓checked.

-  **1.3b50 Compatability Mode**

   Due to some changes in how certain data is stored in the campaign
   file in versions after 1.3b50, they might not be compatible with
   version 1.3b50 and earlier. If this is ✓checked your campaign will be
   saved in the older format, allowing it to be opened in older
   versions, but losing some of the new features.

.. _map_defaults:

Map Defaults
------------

.. figure:: prefs_application_mapdefaults.jpg
   :alt: prefs_application_mapdefaults.jpg

   prefs_application_mapdefaults.jpg

-  **Halo line width**

   Controls the width of the `Halo <Halo>`__ when it is displayed on a
   `Token <Token>`__.

-  **Vision opacity**

   Areas that are no longer directly visible, but have previously had
   their `Fog of War <Fog_of_War>`__ exposed, will will be dimmed by
   layering a translucent black on top of them. This setting controls
   the opacity of the translucent black.

-  **Use halo color for vision**

   Related to **Vision opacity**, if this setting is ✓checked, the
   translucent color layered on top of previously viewed areas will be
   the `Token's <Token>`__ `Halo <Halo>`__ color as opposed to black.

-  **Autoshow Fog**

   Will automatically expose `Fog of War <Fog_of_War>`__ after moving a
   `Token <Token>`__ if ✓checked.

.. _macro_panels:

Macro Panels
------------

.. figure:: prefs_application_macropanels.jpg
   :alt: prefs_application_macropanels.jpg

   prefs_application_macropanels.jpg

-  **Default: Allow Players to Edit Macros**

   In order for a macro to be considered a `Trusted
   Macro <Trusted_Macro>`__, players must not be able to edit it. This
   setting determines if a new macro should default to allowing players
   to edit if ✓checked. Disabling this setting can be very useful if you
   intend to create a lot of macros that you intend to be trusted.

.. _sounds_tab:

Sounds Tab
==========

|prefs_tab_sounds.png| |prefs_sounds_all.jpg|

-  **Play system sounds**

   When ✓checked, MapTool will play a sound when new content is sent to
   the chat panel.

-  **Only when window not focused**

   When ✓checked, the sound that MapTool plays when new content is sent
   to the chat panel will only play if MapTool is not the application
   that has focus.

`Category:MapTool <Category:MapTool>`__

.. |gridSquare.png| image:: gridSquare.png
.. |gridHorizontalHex.png| image:: gridHorizontalHex.png
.. |gridVerticalHex.png| image:: gridVerticalHex.png
.. |prefs_tab_accessibility.png| image:: prefs_tab_accessibility.png
.. |prefs_accessibility_all.jpg| image:: prefs_accessibility_all.jpg
.. |prefs_tab_sounds.png| image:: prefs_tab_sounds.png
.. |prefs_sounds_all.jpg| image:: prefs_sounds_all.jpg
