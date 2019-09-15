.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{Languages|Introduction to Campaign Repositories}}

.. _qué_es_un_repositorio:

¿Qué es un repositorio?
=======================

Un repositorio es un pack de archivo (en su mayoría imagenes) que son
usadas en una campaña. Almacenandolo en algún lugar que no sea el
ordenador del master se puede ayudar mejorar la velocidad de descarga de
los jugadores haciedo que el juego valla mejor en general.

Debes tener algún lugar de almacenamiento externo para poder usar el
repositorio. Algunas cmopañias de las que te dan internet te dejan
espacio que puedes usar para este tipo de proposito. Si tu compañía no
te da esta posibilidad puedes buscar por ahí y encontrar algún lugar de
almacenamiento barato (o incluso gratis).

A no ser que se ejecute el MapTool desde un buen ordenador con buena
connección, tienes casi garantizado que los jugadores podrán descargar
los archivos de cualquier web de almacenamiento con mayor velocidad que
si lo hacen desde el ordenador del master. Este es uno de los beneficios
de los repositorios.

.. _creando_un_repositorio:

Creando un repositorio
======================

Para crear un archivo de repositorio, abre la campaña en el MapTool y ve
a Archivo -> Exportar -> Archivo Depósito de Campaña. Esto creará un
achivo comprimido (.zip) con la información del repositorio.

Descomprime el archivo. (¡Esto es muy importante! ¡El MapTool no puede
usar el repositorio si no lo descmprimes!) Dentrod debe haber una
carpeta llamada "assets" y un archivo llamado "index.gz". Sube al
servidor ambas, la carpeta "assets" y el archivo "index.gz". Asegurate
de que estén en el mismo directorio. (No pongas el archivo"index.gz"
*dentro* de la carpeta "assets", deben de estar al mismo nivel).

Apunta la URL del archivo "index.gz". Puedes probar la URL escriiendola
o pegandola en la barra de direcciones de tu navegador. Si tienes la
dirección correcta deberías ver una pçagina llena de números y letras
que seguramenteno tendrán mucho setido para ti.

En el MapTool, Ve a Editar -> Propiedades de campaña y luego ve al
apartado de los repositorios. Borra cualquier enlace que ya esté ahí y
coloca la URL de tu archivo "index.gz".

Guarda la campaña. Ahora cuando los jugadores se coneccten al servidor
del master conseguirán los archivos de la campaña del repositoro en la
red en vez de del ordenador de este.

Si realizas cambios en la campaña deberás volver a exportar el archivo
del repositorio y subirlo otra vez siguiendo los mismos pasos. No
necesitarás volver a cambiar la URL a no ser que cambies el lugar donde
los guardabas en la red

.. raw:: mediawiki

   {{Languages|Introduction to Campaign Repositories}}

{{#customtitle:Inroducción a los repositorios de campaña|Inroducción a
los repositorios de campaña}}

`Category:MapTool <Category:MapTool>`__
`Category:Tutorial <Category:Tutorial>`__
