\]

## Introducion

### Primero lo Primero: ¿Qué es MapTool?

A pesar de que probablemente tengas una idea de que es y que hace
MapTool, quiero tomarme un momento para reforzar el objetivo principal
de MapTool:

**MapTool es un programa que te ayuda a compartir una "Mesa Virtual" con
tus amigos, permitiendoles jugar sobre ella.**

Esto es lo que MapTool hace, y sus caracteristicas estan orientadas a
proveer gran cantidad de opciones, de lo simple a lo complejo, para
alcanzar ese objetivo.

En la discusion sobre macros, propiedades, tablas y creacion de scripts
que se desarrollara en esta y otras guias, no pierdas de vista la razon
por la que revisas MapTool: es una manera de jugar y compartir con tus
amigos.

### Acerca de esta guía

El propósito de esta guía es no profundizar mucho en las entrañas del
sistema de script de MapTool, iluminación, propiedades, o cualquier cosa
compleja. El lugar de eso, esta guía debe iniciarte en el uso de MapTool
como un *Programa de Creación de Mapas* para juegos de rol. Otras guías
abordan temas como [hosting an online
game](Introduction_to_Game_Hosting "wikilink"), [working with
tokens](Introduction_to_Tokens "wikilink"), [setting up vision and
light](Introduction_to_Lights_and_Sights "wikilink"), e [writing
macros](Introduction_to_Macro_Writing "wikilink").

Las siguientes instrucciones deben ponerte al día con el uso de MapTool
como una herramienta para crear mapas de batalla y mapas generales. Esto
asume algunas cosas:

1.  Usted sabe como crear u obtener algunas imágenes de mapas. Existen
    terabytes (exabytes\! yottabytes\!) de imágenes de mapas en la Web.
    Revise [RPTools Gallery](http://gallery.rptools.net) o
    [RPGMapShare](http://www.rpgmapshare.com) y encontrara montones de
    excelentes imágenes.
2.  Usted puede ejecutar MapTool en su ordenador. MapTool requiere Java
    1.5 para poder ser instalado en su pc; queda de su parte encargarse
    de ello.

Así que aquí vamos. Para comenzar lo menos complicado:

1.  Obtenga MapTool de <http://rptools.net>. La ultima versión compilada
    de MapTool puede obtenerse siempre al principio de [this
    list](http://www.rptools.net/index.php?page=downloads#MapTool).Actualmente
    la última compilación es 1.3.b56. **NOTA**: Usted también puede
    ejecutar el [Java
    WebStart](http://www.rptools.net/index.php?page=launch) para
    ejecutar MapTool sin necesidad de descargar y descomprimir el
    archivo.
2.  Si usted descarga el archivo comprimido de MapTool, descomprímalo en
    algún lugar de su ordenador y asegúrese de que puede ser ejecutado.
    Los archivos .bat incluidos asignan algunos parámetros cuando los
    ejecuta, como locación de memoria y cosas similares. El programa se
    ejecutara si hace dobleclick sobre el archivo .jar, pero le dará
    algunas advertencias. Si utiliza Windows™, puede utilizar el
    Lanzador de Windows™, el cual permite alterar las configuraciones de
    manera muy conveniente.

Ahora, creemos algún mapa útil.

## Colocar Imágenes en su Librería de Recursos de MapTool

La **Librería de Recursos** de MapTool es una colección de "punteros" o
"enlaces" a carpetas en su ordenador las cuales contienen las imágenes
que usted desea utilizar con MapTool. MapTool viene con un conjunto de
imágenes predeterminadas, pero usted puede agregar cualquier cantidad de
imágenes que desee - Usted esta en control de la cantidad de imágenes
disponibles para MapTool.
![Mt-f-addtoreslib.jpg‎](Mt-f-addtoreslib.jpg‎ "Mt-f-addtoreslib.jpg‎")

![File-dialog.jpg](File-dialog.jpg "File-dialog.jpg")

1\. Obtenga algunas imágenes (mapas, por ejemplo) de algun lugar: estas
pueden ser descargadas de la web, o creadas por usted. Coloquelas en un
directorio que recuerde con facilidad - este directorio es importante
para el paso 3.

2\. Abra MapTool.

3\. Seleccione **Archivo -\> agregar a la Librería de Recursos**
(mostrado abajo, izquierda). Eso abrira un dialogo llamado **Cargar
Directorio de Recursos** (click en las imágenes para verlas a tamaño
completo a la derecha).

4\. En el dialogo, diríjase a la carpeta en la que almaceno las imágenes
de mapa que desea agregar y haca click en **Abrir**. MapTool procesara
las imágenes en el directorio, y agregara una nueva carpeta en el árbol
de la Librería de Recursos.

**NOTA**: El nombre de el directorio en la Libreria de Recursos de
MapTool sera el mismo del directorio que eligio en el paso 3.


![Mtreslib.jpg](Mtreslib.jpg "Mtreslib.jpg")

5\. Luego de esto, si selecciona una de las carpetas en su libreria de
recursos(como se ve en la imagen inferior), vera vistas previas de las
imagenes dentro de esa carpeta. **NOTA**: Si su carpeta tiene
subcarpetas, presione **+** para expandir el contenido de la misma.
Tampoco es necesario agregar nuevamente ese directorio, MapTools
recordara sus selecciones previas.

**NOTA**: Debido a que las carpetas que aparecen en la Librería de
Recursos son en realidad punteros a las carpetas en su disco duro, no
debe preocuparse de que MapTool vaya a duplicar cada archivo -- la
Librería de Recursos es solo una manera para que MapTools sepa donde
encontrar las imágenes .



## Creando un mapa

![Map-newmap.jpg](Map-newmap.jpg "Map-newmap.jpg")

![Map-new-dialog.jpg](Map-new-dialog.jpg "Map-new-dialog.jpg")

1\. Ve a **Mapa -\> Nuevo Mapa**. Esto te abrirá la ventana de
propiedades del mapa.

2\. A la izquierda de esta ventana verás multiples opciones para
configurar el mapa.

  - **Name**: Este es el nombre del mapa- Ten en cuenta que si
    seleccionas una imagen para el mapa, el nombre de este cambiará
    automaticamente al de la imagen.Lo mejor es dejar este apartado para
    el final así podrás ponerle el nombre que quieras en lugar de
    Map_001.jpg o como sea que se llamase.
  - **Cell Type**: Casillas hexagonales (dos sentidos), cuadradas o sin
    ninguna.
  - **Distance Per Cell**: Unidades de movimiento por casilla, como en
    D\&D4 el movimiento va por casillas, puedes dejarlo directamente en
    1.
  - **Pixels per cell**: Este es el tamaño el pixels de cada casilla.
  - **Vision Distance**: Distancia por defecto a la que el PJ verá el
    mapa.


![Background-dialog.jpg](Background-dialog.jpg "Background-dialog.jpg")

3\. Haz click en el boton **Background**. Saldrá nua ventana con varias
opciones. La textura y/o el color son infinitamente ampliables en todas
direcciones.

  - **Swatch**: Te permite usar un color uniforme como fondo del mapa.
      - <font color="red">**Cuidado:** En la versión 1.3.b53, si
        seleccionas la parte superior izquierda de Swatch (la parte
        blanca), MapTool genera un error. El error no hará que el
        Maptool se cierre ni nada parecido pero no seleccionará el color
        blanco. Con un poco mas de trabajo, puedes colocar el fondo
        blaco usando el camino del Hue o el RGB.</font>
  - **Hue/RGB**: Te permite especificar colores y determinar el color
    Swatch.
  - **Texture** (el más común): Te da acceso a la librería de donde
    puedes seleccionar una textura para el fondo.


![Map-mapbutton.jpg](Map-mapbutton.jpg "Map-mapbutton.jpg")

4\. Si tienes una imagen en mente (una descargada o que retocada con el
Gimp o algún programa semejante), haz click en **Map**. Se abrirá una
ventana con la librería. Selecciona la imagen que quieras usar. Est
imagen se colocará sobre el fondo escogido.


![Map-create-done.jpg](Map-create-done.jpg "Map-create-done.jpg")

5\. Cuando estés a gusto con el mapa y el fondo – podrás ver un recuadro
con las vista previa, como en la imagen - pon un título y haz click en
**OK**. El mapa se cargarña en la ventana de MapTool.



### Creando multiples mapas para una campaña

MapTool te permite crear varios mapas, todos dentro de una misma
campaña. El proseso es muy simple: solo repite los pasos de [Creando un
mapa](Introduction_to_Mapping/es#Creando_un_mapa "wikilink") para cada
uno nuevo, seleccionando una nueva imagen, fondo (color/textura), y
título.

Cada mapa nuevo que crees será automaticamente dentro de la campaña en
la que estás trabajando (crear un mapa no guarda automaticamente los
cambios, asegurate de [guardar tu
trabajo](Introduction_to_Mapping/es#Guardando_tu_trabajo "wikilink") al
terminar).

Puedes también añadir nuevos mapas a una campaña que ya tuvieses creada
- solo abre el archivo de la campaña (llendo a **Archivo -\> Abrir
campaña**) y sigue los pasos para crear un mapa.

## Ventana principal de MapTool

### Capas de MapTool

![Layer-window.png](Layer-window.png "Layer-window.png")

Teniendo un mapa cargado, verás una ventanita en el mapa titulada
*Layer*. MapTool tiene cuatro capas:

  - **Background**: Es una capa para imagenes, fondos para mapas, cosas
    que no se vallan mover.
  - **Hidden**: Para juegos online, esta es una capa solo la puede ver
    el Master.
  - **Object**: Esta es una capa objetos, cosas que se moverán, o que el
    jugador ha de ser capaz de mover (lamparas, mesas, etc.).
  - **Token**: En esta capa van los *tokens*. Asegurate de tener la capa
    seleccionada al añadir personajes o enemigos al juego.

Piensa en las capas del MapTool como cuatro hojas de papel, una sobre la
otra. La del fondo, - la capa **Background** - es donde se dibujan las
partes básicas del mapa: Muros, suelo, árboles, etc. En la sigueinte, -
la capa **Objects** - dibujas las *cosas* que el personaje puede usar,
interactuar, romper: puertas, baúles, mesas, silals, etc. En la capa
superior - la capa **Hidden** - pones las cosas que solo el Master puede
ver (¡Qué serán objetos o personajes ocultos\!). Finalmente, en la capa
superior - la capa **Token** -, pones las miniaturas - los mounstruos,
personajes, y NPCs de este mundo.

Los tokens pueden ser puestos en cualquier capa de MapTool. Para hacerlo
solo haz click-derecho en la imagen del token, y selecciona **Change To
\>**. En el menú, selecciona la capa a la que lo quieras mover y será
movido.

### Seleccionando mapas

![Blueglobe.jpg](Blueglobe.jpg "Blueglobe.jpg")

![Maplist.jpg](Maplist.jpg "Maplist.jpg")

Si creas solo un mapa en tu campaña, será cargado por defecto y será el
único mapa que puedas ver.

Si [creas varios
mapas](Introduction_to_Mapping/es#Creando_multiples_mapas_para_una_campaña "wikilink")
o tienes una campaña con varios mapass pueden escoger entre elos
haciendo click en el icono del globo terráqueo arriba a la derecha de la
ventana de MapTool – esto abrirá una ventana con los posibles mapas.
Fijate que si solo tienes un mapa, al hacer click se mostrará el nombre
del mapa.



### Haciendo zoom y moviendose

Para hacer zoom en el mapa, puedes usar la rueda del ratón (si tienes),
o puedes usar el símbolo de igual para ampliar y el de la resta para
alejar.

Presionando la decla de suma vuelve a 1:1.

Para mover el mapa, hacerclick derecho con el ratón y arrastrar. Esto
deslizará el mapa en cualquier dirección.

## Lo básico de los Tokens

[Tokens de MapTool](Token:token "wikilink") (o solo "Tokens") son
pequeñas fichas usadas para representar diferentes cosas en el mapa de
MapTool. Lo más común es a los personajes jugadores y no jugadores.

Los Tokens, com todo lo demás, empiezan como una imagen en tu [Libreria
de recursos](Macros:Glossary#R "wikilink"). MapTool trae algunos (y
cuenta con un programa llamado
[TokenTool](http://www.rptools.net/index.php?page=tokentool) que te
permite crear tokens), o puedes también buscarte tu ptopia manera de
hacerlos.

Esta sección de la guía de creacción de mapas cuenta con solo algunas
cosas básicas con las que tendrás que tratar al usar los tokens de
MapTool. Hay *algunas* características o trucos al trabajar con los
tokens que podrían necesitar una guía para ellos solos.

### Situando tokens en el mapa

![Default-library.jpg](Default-library.jpg "Default-library.jpg")

1\. Para ver los tokens básicos antes mencionados, ir a la carpeta
Default en tu *biblioteca de recursos* hacer click sobre el **+** para
ampliarla.


![Default-tokens.jpg](Default-tokens.jpg "Default-tokens.jpg")

2\. Selecciona la carpeta de tokens.


![Token-drag-to-map.jpg](Token-drag-to-map.jpg "Token-drag-to-map.jpg")

![Token-on-map.jpg](Token-on-map.jpg "Token-on-map.jpg")

3\. En la ventana inferior (donde aparece el recuadro), usa el ratón
para arrastrar un token al mapa. El cursos cambiara a una mano, y solo
necesitarás mantener el botón pulsado y soltarlo sobre cualquier lado
del mapa.

Al soltar el botón, el token aparecerá en el mapa, com se ve en la
imagen.



### Moviendo tokens

Una vez que el token está en el mapa, pude moverse usando el ratón, o
seleccionandolo (haciendo click en él) y utilizando las flechas para
desplazarlo y pulsando la letra **D** o click izquierdo al finalizar el
movimiento.

Si quieres hacer un camino complejo, puedes apretar la barra espaciadora
y creará un punto por el que deberá pasar en el movimiento.

### Cambiando del nombre del token, nombre del master (GM), y etiquta (label)

![Token-default-name.jpg](Token-default-name.jpg
"Token-default-name.jpg")

![Edit-token.jpg](Edit-token.jpg "Edit-token.jpg")

Los tokens tienen tres posibles nombres que le puedes asigar, cuando es
puesto en el mapa se le asigna un nombre base (normalmente, el mimso que
el archivo del token). por ejemplo, el token de la imagen muestra el
nombre de cuando fue arrastrado al mapa y este es "Hero."

Los tres posibles nombres son:

  - **Token Name**: El nombre del token que aparece para todos los
    usuarios. Es obligatorio.
      - <font color="red">**NOTA**: \!Asegurate de que cada token tiene
        un nombre único\! De otro modo, MapTool actuará de un modo
        impredecible.</font>
  - **GM Name**: Solo visible por el master.
  - **Label**: Aparece bajo el nombre del token, y es visible para todas
    las personas conectadas.

To change a token's name, GM name, and/or label:

1\. Hacer doble click sobre la imagen del token en el mapa. Esto abrirá
la ventana **Edit Token** como se muestra.


![Edit-token-changednames.jpg](Edit-token-changednames.jpg
"Edit-token-changednames.jpg")

![New-token-names.jpg](New-token-names.jpg "New-token-names.jpg")

2\. En el hueco **Name** pon el nombre que quieras. Por ejeplo, para
este caso yo puse "Bork the Brave"

3\. En el hueco **GM Name** pon un nombre. Por ejeplo, para este caso yo
puse "Cork the Cowardly"

4\. En el hueco **Label** pon una etiqueta. Por ejeplo, para este caso
yo puse "Human Warrior".

5\. Haz click en **OK** para guardar los cambios.

Tras hacerlo verás que el token ha cambiado:

Y podrás realizar este proceso con cualquier token que esté en el mapa.



### Cambiando la imagen del token

Algunas veces, cuando creas un token nuevo, puedes querer cambiar la
imagen de la cara del token. Por ejemplos, si encuentras una imagen
mejor para el token que la que ya estaba puesta ¿pero no querrás borrar
todo el token solo para cambiar la imagen verdad? Seria cansino. En ese
caso, soo cambia la imagen siguiendo los siguientes pasos:

![Edit-token.jpg](Edit-token.jpg "Edit-token.jpg")

1\. Aseurate de que tienes una nueva imagen en formato .jpg o .png
usable en la librería de recursos de MaTool. Si mras la sección [Colocar
Imágenes en su Librería de Recursos de
MapTool](Introduction_to_Mapping/es#Colocar_Imágenes_en_su_Librería_de_Recursos_de_MapTool "wikilink")
habla sobre como colocar imagenes ahí: bueno, imagenes de tokens (en
realidad, *cualquier* imagen) puede ser añadda a la biblioteca del mismo
modo.

2\. Hacer doble click sobre la imagen del token. Esto abrirá la ventana
**Edit Token**.


![Edit-token-changeimage.jpg](Edit-token-changeimage.jpg
"Edit-token-changeimage.jpg")

3\. Arriba a la izquiera, hacer click en el signo verde de suma.


![New-image-picked.jpg](New-image-picked.jpg "New-image-picked.jpg")

4\. En la ventana **Choose Image** selecciona la carpeta *Resource
Library* selecciona la imagen y haz click en **OK**.


![Token-image-changed.jpg](Token-image-changed.jpg
"Token-image-changed.jpg")

5\. Al hacer click en **OK**, vuelves a la ventana **Edit Token**, y
verás que la imagen ha cambiado por la que has seleccionado.



### Cambiando el tamaño de los tokens

![Token-rightclick.jpg](Token-rightclick.jpg "Token-rightclick.jpg")

Los tokens apareceran por de mase al tamaño de los recuadros (el tamaño
base de los recuadros de MapTool es 50x50 pixels). Si hacel
click-derecho sobre un token, verás un menú con muchas opcionesde las
cuales una es **Size** (tamaño). COn eso puedes variar el tamaño de los
tokens para tener así criaturas enormes o del tamaño que sea. En la
imagen inferior se puede ver el menu que se despliega.

**NOTA**: Los tamaños son (grande, enorme, gigantesco etc.) solo
aplicables a mapas que tengan rejilla (recuerda que al crear un mapa
puede hacerlo sin esta). Si usas un mapa sin rejilla, el tamaño irá por
valores.


\==Guardando tu trabajo==

MapTool's default "save" format is called a *Campaign File*. El archivo
de campaña (en el formato *.cmpgn*) contiene los mapas y tokens que has
colocado. Si estas interesado en esta clase de cosas, el archivo de
campaña es un archivo comprimido en formato XML.

Para guardar tu trabajo en otro lugar, selecciona **Archivo -\> Guardar
campaña**, give your campaign a name, and that’s all there is to it.

Cuando guardes la campaña, MapTool guarda la posisión de los tokens en
todos los mapas, así podrás continuar justo donde lo dejaste.

## Exportando imagenes de mapas

MapTool puede exportar las imagenes de tus mapas a una imagen (en
formato PNG). Para exportar una imagen a un lugar de tu elección sigue
los siguientes pasos:

1\. Ve a **Archivo -\> Exportar** y selecciona **Pantalla como**.

2\. En la ventana que aparece selecciona un tipo de vista (entre la
visión del master, donde lo puedes ver todo, o la del jugador, donde
solo se ve lo que el jugador puede ver...)

3\. Selecciona un destino para alojar la imagen apretando el botón
*Brouse...* (o envíalo a un servidor FTP)

4\. Haz click en **Exportar**.

## Sigueintes pasos

Ahora crea un nuevo mapa y pon algunos token en él, el siguiente paso es
conectarte con algunos amigos por internet(o cara a cara) y usa lo
aprendido para una sesión de jeugo.

Este tema está incluido en [Introduction to Game
Hosting](Introduction_to_Game_Hosting "wikilink").

{{\#customtitle:Inroducción a la creacion de mapas|Inroducción a la
creacion de mapas}}

[Category:MapTool](Category:MapTool "wikilink")
[Category:Tutorial](Category:Tutorial "wikilink")