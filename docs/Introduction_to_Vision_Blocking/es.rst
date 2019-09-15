.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{Languages|Introduction to Vision Blocking}}

.. raw:: mediawiki

   {{Beginner}}

.. _la_traducción_está_en_proceso:

La traducción está en proceso
=============================

.. _bloqueo_de_visión:

Bloqueo de visión
=================

En el MapTool, los `tokens <Token:token>`__ pueden recibisIn MapTool,
`visión <Introduction_to_Lights_and_Sights>`__, lo que permite al
`token <Token:token>`__ ver a otros `tokens <Token:token>`__ o áreas del
mapa. También se le puede dar
`iluminación <Introduction_to_Lights_and_Sights>`__ - por lo que solo se
podría ver la parte iluminada (o las fuentes de luz cercanas) - La
función del bloqueo de visión es permitir al master poner límites al
rango de visión de los personajes a través de los cuales no pueden ver,
con esto se pueden indicar las paredes de un dungeon para que solo vea
lo que está a su alcance, por ejemplo.

En este documento se hará un breve repaso de las herramientas de
bloqueo, y como usarlas para crear una madmorra como la del ejemplo.
Recuerda, el bloqueo de visión está muy unido a la **luz**, la
**visión** y la **niebla de guerra** (características del MapTool, por
lo tanto una vez que hayas leído este tutorial, ve a ver `Introduction
to Lights and Sights/es <Introduction_to_Lights_and_Sights/es>`__ y mira
como funciona todo junto.

.. _primero_que_nada_hacer_un_mapa:

Primero que nada, Hacer un mapa
-------------------------------

.. figure:: samp-dungeon.png
   :alt: samp-dungeon.png

   samp-dungeon.png

Para empezar, necesitaremos un mapa de una madmorra. Algún lugar oscuro
y húmedo, llego de pequeños pasajes, ¿Te haces a la idea, no?

Los mapas de ejemplo han sido creados con el MapTool usando este
`tileset <http://forums.rptools.net/viewtopic.php?f=34&t=7418>`__ muy
bueno creado por Jonathan Roberts (Torstan en el `RPTools
Foros <http://forums.rptools.net>`__), el mapa que se muestra a la
derecha se utilizará para los ejemplos de este tutorial introductorio.

.. _activando_las_herramientas_de_bloqueo_de_visión:

Activando las herramientas de bloqueo de visión
===============================================

.. figure:: Vbl-toolbar-btn.png
   :alt: Vbl-toolbar-btn.png

   Vbl-toolbar-btn.png

.. figure:: Vbl-tools.png
   :alt: Vbl-tools.png

   Vbl-tools.png

Para activar las herramientas de bloqueo de visión, haz click en el
icono del "ojo" en la barra de herramientas del MapTool (mira la
imagen). al hacerlo, nuevos iconos aparecerán, estos son los iconos de
de edición, que te permiten cambiar el modo de pintar las líneas. Si
pones el ratón sobre ellos un recuadro expliativo te dirá que hace cada
uno. De izquierda a derecha, estos son los que hay.

-  **Dibujar una CBV rectangular**: crea un área rectangular sólida que
   bloquea la visión (suelen conocerse como vapas de bloqueo de visión,
   o "CBV" para abreviar). . Los toens que estén fuera de este área no
   podrán ver lo que está adentro; los que estén dentro no verán nada de
   nada (es solido y opaco).
-  **Dibujar una CBV rectangular vacía**: semejante al de arriba pero
   los tokens de adentro podrán ver lo que está dentro del área
   rectangular pero no a través de los límites.
-  **Dibujar una CBV obalada**: Como la rectangular pero con forma
   obalada.
-  **Dibujar una CBV obalada vacía**: misma comparación que entre los
   dos tipos de rectangunlares.
-  **Dibujar una CBV de polígono cerrado**: esto te permite dibujar un
   polígono usando líneas, y al terminar cerrarlo uniendo con otro
   segmento, al cerrarlo cerá un polígono sólido de CBV. Para empezar
   haz click con el boton izquierdo sobre el mapa, y dibuja un primer
   segmento. para unir el sigueinte, haz *click derecho* y mueve el
   ratón para crearlo. Al terminar otra vez *click izquierdo* para
   cerrarlo.
-  **Dibujar una CBV de línea poligonal**: as above, but creates a
   hollow polygon

.. _mejores_utilidades:

Mejores utilidades
------------------

Vision blocking and vision processing is processor-intensive, and
overuse of (or overly-complex) VBL can cause serious performance issues
with MapTool - slowdowns, inability to navigate a map, and so forth.
Some rules of thumb:

#. **Use square VBL wherever possible** - and minimize the use of
   circular or highly irregular VBL
#. **Use solid VBL wherever possible** - this prevents gaps between
   polylines, which can be performance hogs. Instead, cover the map with
   VBL, and cut out the areas that the tokens should be able to see.
#. **Use as little VBL as necessary to get the effect you seek** - make
   it efficient!
#. It is frequently a good idea to set up a vision boundary at the edges
   of the play area on your map - maps in MapTool are theoretically
   infinitely sized, but if your tokens are going to be only in the
   dungeon area, there's no reason for MapTool to have to be calculating
   what they see all the way out to the edge of the universe.

These will help keep performance from bogging down. You *can* use the
other kinds of VBL, but simply be aware of how complex your vision
blocking setup is getting.

.. _putting_vbl_on_the_sample_map:

Putting VBL on the Sample Map
=============================

Now, to add some vision blocking to the map. We will use a recommended
technique, which is to cover the entire map with a solid block of VBL,
and then "cut out" of that block the areas that the players will see.

.. _cover_the_entire_dungeon_with_solid_vbl:

Cover the Entire Dungeon with Solid VBL
---------------------------------------

.. figure:: Vbl-map-zoomed-extents.png
   :alt: Vbl-map-zoomed-extents.png

   Vbl-map-zoomed-extents.png

.. figure:: Vbl-createsolidvbl.png
   :alt: Vbl-createsolidvbl.png

   Vbl-createsolidvbl.png

#. Zoom the map so you can see the whole thing.
#. Select the Draw a Rectangular VBL button.
#. Left-Click to place the upper-left corner of the solid VBL. Do not
   hold down the left-mouse button.
#. Drag the mouse to define the size of the VBL. You'll see it traced
   out in a transparent red color as you drag.
#. Click the left mouse button again to place the lower-right corner of
   the VBL. The VBL will turn blue (if you go to the toolbar and select
   one of the other tools on the left side - switching off the VBL tools
   - the blue VBL indicators will disappear. They are only visible when
   the VBL tools are active).

.. figure:: Vbl-complete-cover.png
   :alt: Vbl-complete-cover.png

   Vbl-complete-cover.png

You've now covered the entire map with VBL. If a token was placed
outside that area, and had a "sight" setting active, it would not be
able to see into that area.

.. _cut_out_the_visible_areas_from_the_solid_vbl:

Cut out the Visible Areas from the Solid VBL
--------------------------------------------

.. figure:: Vbl-erasingvbl.png
   :alt: Vbl-erasingvbl.png

   Vbl-erasingvbl.png

Now, we cut out the rooms. This process is a bit trickier - to keep the
VBL efficient, make sure you get the edges lined up as best you can and
you don't leave any narrow gaps or thin lines of VBL between rooms (a
trick to doing this is in the instructions below). For this part, I will
be clearing all VBL, out to the outer walls. We will work on the
interior walls later.

#. Zoom the map until you are comfortable with the zoom level.
#. Select the Draw a Rectangular VBL tool.
#. Hold down the Shift key, and left-click to mark the upper-left corner
   of the area of VBL you want to erase. A white, transparent box will
   follow the mouse cursor (if it's not white, you forgot to hold
   shift!)
#. Drag the mouse until you've reached where you want the lower-right
   corner of the cleared area to be, and left-click. The blue VBL will
   disappear. You have now erased the VBL for that area, and tokens in
   that area would be able to see (their vision would be blocked, of
   course, once it reached any VBL!).
#. Repeat this process for the rest of the rooms, tunnels, and so forth.

.. figure:: Vbl-erased.png
   :alt: Vbl-erased.png

   Vbl-erased.png

Afterwards, you'll have a large blue area, with the dungeon "cut out"
inside it.

**TIP**: if you hold down Ctrl while you trace your VBL, it will snap to
the gridlines of the map. This is very useful for aligning VBL. I used
this technique to erase the VBL on the sample map, because it makes the
VBL align easily and squarely on the dungeon walls.

.. _interior_vbl:

Interior VBL
------------

.. figure:: Vbl-polyline-wall.png
   :alt: Vbl-polyline-wall.png

   Vbl-polyline-wall.png

Finally, we will put VBL on the interior walls. This will make it so
that the walls *inside* the dungeon block vision too.

#. Zoom the map to focus on a particular wall.
#. Select the "Draw Polyline VBL" tool.
#. Hold down Ctrl, and left-click on the map to place the beginning of
   the line segment. I recommend starting the line somewhere in the
   solid VBL, so that there are no gaps at the edges of the walls.
#. Drag the mouse to draw the line segment. (in the screenshot, the line
   segment is the thin red line inside the yellow circle; the yellow
   circle was drawn on the screenshot to show you where the polyline is
   - it's not part of the VBL process)
#. Left-click to place the end of the line segment. The red line will
   turn blue, indicating that there is VBL now on that wall.
#. Repeat the process for the other walls, until you are satisfied.

.. _vbl_and_objects:

VBL and Objects
---------------

There are lots of objects in a dungeon that can block vision - doors,
pillars, piles of rubble, chests...you name it. It is possible to draw
VBL anywhere on a map - however, at this time, VBL is not linked to
particular objects. This means that you can't, for instance, put VBL on
a door and have it "open" with the door when your players open it. You
can simulate this by deleting the VBL that crossed the doorway, but you
can't have the VBL automatically move with an object.

You'll have to experiment with the VBL for the objects in your dungeon,
but here are some tips:

-  **Doors**: for doors, if they are closed, simply draw the VBL along
   the wall in which the door sits. When (if) the door is ever opened,
   you can rotate the door object, and use Solid Rectangular VBL to
   erase the vision blocking layer that covered the doorway (remember,
   hold down Shift to erase VBL). Make sure to use *solid* VBL - if you
   use a hollow rectangle, it will only erase where the hollow
   rectangle's boundary intersects the other VBL.

.. figure:: Vbl-drawx.png
   :alt: Vbl-drawx.png

   Vbl-drawx.png

-  **Pillars, statues, and standing objects**: remember that, when you
   use VBL, the tokens cannot see into or through it at all (and,
   because of this, the *players* won't see anything covered by or
   hidden inside VBL on their screens). If you want the players to be
   able to see some of an object - like a large pillar - one of the
   recommended tricks is to draw an "X" on the pillar using poly line
   VBL (instead of covering the whole pillar with a circular or
   rectangular solid VBL. Using an X means that the players can see some
   of the pillar, depending on where their tokens are. It makes for a
   much nicer look. If you look at the screenshot, you'll see an "X"
   drawn using VBL on top of one of the barrels.

.. _vbl_limitations:

VBL Limitations
===============

The Vision Blocking Layer in MapTool is a tool for helping to simulate
what a character can see during a game. However, it does have
limitations, and doesn't "completely simulate vision" or anything like
that. We touched on one limitation earlier, the fact that VBL cannot be
attached to specific objects, and so if you open a door that is covered
by VBL - the door object might move, but the VBL stays put. Here are a
couple other limitations of the current (as of MapTool 1.3.b56) Vision
Blocking Tools.

-  **Vision Blocking is Binary**: VBL in MapTool is on or off. There is
   no "partially transparent" or "one way" VBL in the current version of
   MapTool.
-  **Vision Blocking is Total**: Related to the above, VBL blocks all
   forms of vision. There are no vision types currently that can see
   through VBL.
-  **Vision Blocking has no Elevation**: VBL cannot at this point be
   given a particular height - it stretches to infinity, up and down,
   and so there's no way to set up VBL so a tall character can see
   "over" it

.. raw:: mediawiki

   {{Languages|Introduction to Vision Blocking}}

{{#customtitle:Inroducción al bloqueo de visión(inacabado)|Inroducción
al bloqueo de visión(inacabado)}}

`Category:MapTool <Category:MapTool>`__
`Category:Tutorial <Category:Tutorial>`__
