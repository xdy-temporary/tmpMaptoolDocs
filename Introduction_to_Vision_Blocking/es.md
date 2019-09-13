### La traducción está en proceso

Bloqueo de visión
-----------------

En el MapTool, los [tokens](Token:token "wikilink") pueden recibisIn MapTool, [visión](Introduction_to_Lights_and_Sights "wikilink"), lo que permite al [token](Token:token "wikilink") ver a otros [tokens](Token:token "wikilink") o áreas del mapa. También se le puede dar [iluminación](Introduction_to_Lights_and_Sights "wikilink") - por lo que solo se podría ver la parte iluminada (o las fuentes de luz cercanas) - La función del bloqueo de visión es permitir al master poner límites al rango de visión de los personajes a través de los cuales no pueden ver, con esto se pueden indicar las paredes de un dungeon para que solo vea lo que está a su alcance, por ejemplo.

En este documento se hará un breve repaso de las herramientas de bloqueo, y como usarlas para crear una madmorra como la del ejemplo. Recuerda, el bloqueo de visión está muy unido a la **luz**, la **visión** y la **niebla de guerra** (características del MapTool, por lo tanto una vez que hayas leído este tutorial, ve a ver [Introduction to Lights and Sights/es](Introduction_to_Lights_and_Sights/es "wikilink") y mira como funciona todo junto.

### Primero que nada, Hacer un mapa

![](samp-dungeon.png "samp-dungeon.png")

Para empezar, necesitaremos un mapa de una madmorra. Algún lugar oscuro y húmedo, llego de pequeños pasajes, ¿Te haces a la idea, no?

Los mapas de ejemplo han sido creados con el MapTool usando este [tileset](http://forums.rptools.net/viewtopic.php?f=34&t=7418) muy bueno creado por Jonathan Roberts (Torstan en el [RPTools Foros](http://forums.rptools.net)), el mapa que se muestra a la derecha se utilizará para los ejemplos de este tutorial introductorio.

Activando las herramientas de bloqueo de visión
-----------------------------------------------

![](Vbl-toolbar-btn.png "Vbl-toolbar-btn.png")

![](Vbl-tools.png "Vbl-tools.png")

Para activar las herramientas de bloqueo de visión, haz click en el icono del “ojo” en la barra de herramientas del MapTool (mira la imagen). al hacerlo, nuevos iconos aparecerán, estos son los iconos de de edición, que te permiten cambiar el modo de pintar las líneas. Si pones el ratón sobre ellos un recuadro expliativo te dirá que hace cada uno. De izquierda a derecha, estos son los que hay.

-   **Dibujar una CBV rectangular**: crea un área rectangular sólida que bloquea la visión (suelen conocerse como vapas de bloqueo de visión, o “CBV” para abreviar). . Los toens que estén fuera de este área no podrán ver lo que está adentro; los que estén dentro no verán nada de nada (es solido y opaco).
-   **Dibujar una CBV rectangular vacía**: semejante al de arriba pero los tokens de adentro podrán ver lo que está dentro del área rectangular pero no a través de los límites.
-   **Dibujar una CBV obalada**: Como la rectangular pero con forma obalada.
-   **Dibujar una CBV obalada vacía**: misma comparación que entre los dos tipos de rectangunlares.
-   **Dibujar una CBV de polígono cerrado**: esto te permite dibujar un polígono usando líneas, y al terminar cerrarlo uniendo con otro segmento, al cerrarlo cerá un polígono sólido de CBV. Para empezar haz click con el boton izquierdo sobre el mapa, y dibuja un primer segmento. para unir el sigueinte, haz *click derecho* y mueve el ratón para crearlo. Al terminar otra vez *click izquierdo* para cerrarlo.
-   **Dibujar una CBV de línea poligonal**: as above, but creates a hollow polygon

### Mejores utilidades

Vision blocking and vision processing is processor-intensive, and overuse of (or overly-complex) VBL can cause serious performance issues with MapTool - slowdowns, inability to navigate a map, and so forth. Some rules of thumb:

1.  **Use square VBL wherever possible** - and minimize the use of circular or highly irregular VBL
2.  **Use solid VBL wherever possible** - this prevents gaps between polylines, which can be performance hogs. Instead, cover the map with VBL, and cut out the areas that the tokens should be able to see.
3.  **Use as little VBL as necessary to get the effect you seek** - make it efficient!
4.  It is frequently a good idea to set up a vision boundary at the edges of the play area on your map - maps in MapTool are theoretically infinitely sized, but if your tokens are going to be only in the dungeon area, there's no reason for MapTool to have to be calculating what they see all the way out to the edge of the universe.

These will help keep performance from bogging down. You *can* use the other kinds of VBL, but simply be aware of how complex your vision blocking setup is getting.

Putting VBL on the Sample Map
-----------------------------

Now, to add some vision blocking to the map. We will use a recommended technique, which is to cover the entire map with a solid block of VBL, and then “cut out” of that block the areas that the players will see.

### Cover the Entire Dungeon with Solid VBL

![](Vbl-map-zoomed-extents.png "Vbl-map-zoomed-extents.png")

![](Vbl-createsolidvbl.png "Vbl-createsolidvbl.png")

1.  Zoom the map so you can see the whole thing.
2.  Select the Draw a Rectangular VBL button.
3.  Left-Click to place the upper-left corner of the solid VBL. Do not hold down the left-mouse button.
4.  Drag the mouse to define the size of the VBL. You'll see it traced out in a transparent red color as you drag.
5.  Click the left mouse button again to place the lower-right corner of the VBL. The VBL will turn blue (if you go to the toolbar and select one of the other tools on the left side - switching off the VBL tools - the blue VBL indicators will disappear. They are only visible when the VBL tools are active).

![](Vbl-complete-cover.png "Vbl-complete-cover.png")

You've now covered the entire map with VBL. If a token was placed outside that area, and had a “sight” setting active, it would not be able to see into that area.

### Cut out the Visible Areas from the Solid VBL

![](Vbl-erasingvbl.png "Vbl-erasingvbl.png")

Now, we cut out the rooms. This process is a bit trickier - to keep the VBL efficient, make sure you get the edges lined up as best you can and you don't leave any narrow gaps or thin lines of VBL between rooms (a trick to doing this is in the instructions below). For this part, I will be clearing all VBL, out to the outer walls. We will work on the interior walls later.

1.  Zoom the map until you are comfortable with the zoom level.
2.  Select the Draw a Rectangular VBL tool.
3.  Hold down the Shift key, and left-click to mark the upper-left corner of the area of VBL you want to erase. A white, transparent box will follow the mouse cursor (if it's not white, you forgot to hold shift!)
4.  Drag the mouse until you've reached where you want the lower-right corner of the cleared area to be, and left-click. The blue VBL will disappear. You have now erased the VBL for that area, and tokens in that area would be able to see (their vision would be blocked, of course, once it reached any VBL!).
5.  Repeat this process for the rest of the rooms, tunnels, and so forth.

![](Vbl-erased.png "Vbl-erased.png")

Afterwards, you'll have a large blue area, with the dungeon “cut out” inside it.

**TIP**: if you hold down Ctrl while you trace your VBL, it will snap to the gridlines of the map. This is very useful for aligning VBL. I used this technique to erase the VBL on the sample map, because it makes the VBL align easily and squarely on the dungeon walls.

### Interior VBL

![](Vbl-polyline-wall.png "Vbl-polyline-wall.png")

Finally, we will put VBL on the interior walls. This will make it so that the walls *inside* the dungeon block vision too.

1.  Zoom the map to focus on a particular wall.
2.  Select the “Draw Polyline VBL” tool.
3.  Hold down Ctrl, and left-click on the map to place the beginning of the line segment. I recommend starting the line somewhere in the solid VBL, so that there are no gaps at the edges of the walls.
4.  Drag the mouse to draw the line segment. (in the screenshot, the line segment is the thin red line inside the yellow circle; the yellow circle was drawn on the screenshot to show you where the polyline is - it's not part of the VBL process)
5.  Left-click to place the end of the line segment. The red line will turn blue, indicating that there is VBL now on that wall.
6.  Repeat the process for the other walls, until you are satisfied.

### VBL and Objects

There are lots of objects in a dungeon that can block vision - doors, pillars, piles of rubble, chests...you name it. It is possible to draw VBL anywhere on a map - however, at this time, VBL is not linked to particular objects. This means that you can't, for instance, put VBL on a door and have it “open” with the door when your players open it. You can simulate this by deleting the VBL that crossed the doorway, but you can't have the VBL automatically move with an object.

You'll have to experiment with the VBL for the objects in your dungeon, but here are some tips:

-   **Doors**: for doors, if they are closed, simply draw the VBL along the wall in which the door sits. When (if) the door is ever opened, you can rotate the door object, and use Solid Rectangular VBL to erase the vision blocking layer that covered the doorway (remember, hold down Shift to erase VBL). Make sure to use *solid* VBL - if you use a hollow rectangle, it will only erase where the hollow rectangle's boundary intersects the other VBL.

![](Vbl-drawx.png "Vbl-drawx.png")

-   **Pillars, statues, and standing objects**: remember that, when you use VBL, the tokens cannot see into or through it at all (and, because of this, the *players* won't see anything covered by or hidden inside VBL on their screens). If you want the players to be able to see some of an object - like a large pillar - one of the recommended tricks is to draw an “X” on the pillar using poly line VBL (instead of covering the whole pillar with a circular or rectangular solid VBL. Using an X means that the players can see some of the pillar, depending on where their tokens are. It makes for a much nicer look. If you look at the screenshot, you'll see an “X” drawn using VBL on top of one of the barrels.

VBL Limitations
---------------

The Vision Blocking Layer in MapTool is a tool for helping to simulate what a character can see during a game. However, it does have limitations, and doesn't “completely simulate vision” or anything like that. We touched on one limitation earlier, the fact that VBL cannot be attached to specific objects, and so if you open a door that is covered by VBL - the door object might move, but the VBL stays put. Here are a couple other limitations of the current (as of MapTool 1.3.b56) Vision Blocking Tools.

-   **Vision Blocking is Binary**: VBL in MapTool is on or off. There is no “partially transparent” or “one way” VBL in the current version of MapTool.
-   **Vision Blocking is Total**: Related to the above, VBL blocks all forms of vision. There are no vision types currently that can see through VBL.
-   **Vision Blocking has no Elevation**: VBL cannot at this point be given a particular height - it stretches to infinity, up and down, and so there's no way to set up VBL so a tall character can see “over” it

{{\#customtitle:Inroducción al bloqueo de visión(inacabado)|Inroducción al bloqueo de visión(inacabado)}}

<Category:MapTool> <Category:Tutorial>