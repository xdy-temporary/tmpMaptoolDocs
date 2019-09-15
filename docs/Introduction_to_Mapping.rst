.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{Languages|Introduction to Mapping}}

__TOC__

Introduction
============

.. _first_things_first_what_is_maptool:

First Things First: What is MapTool?
------------------------------------

Although you probably have an idea what MapTool is and does, I just want
to take a moment to reinforce the main goal of MapTool:

**MapTool is a program that helps you share a "virtual tabletop" with
your friends, so you can play games on it.**

That is what MapTool does, and its features are aimed at providing a
continuum of options, from the simple to the complex, to achieve that
goal.

In all the talk of macros and properties and tables and scripting that
will follow in this and other guides, don't lose sight of the reason
you're checking MapTool out anyway: it's a way to play games with
friends.

.. _about_this_guide:

About this Guide
----------------

The purpose of this guide is not to delve into the seamy underbelly of
MapTool's macro scripting system, lighting, properties, or any of that
complex stuff. Instead, this guide should get you started on the path of
using MapTool as a *mapping* program for role-playing games. Other
guides address topics like `hosting an online
game <Introduction_to_Game_Hosting>`__, `working with
tokens <Introduction_to_Tokens>`__, `setting up vision and
light <Introduction_to_Lights_and_Sights>`__, and `writing
macros <Introduction_to_Macro_Writing>`__.

The following instructions should get you up and running with MapTool to
use as a battle mapping/general mapping tool. This assumes a few things:

#. You know how to create or get some map images. There are terabytes
   (exabytes! yottabytes!) of map images out there on the web. Check out
   the `RPTools Gallery <http://gallery.rptools.net>`__ or
   `RPGMapShare <http://www.rpgmapshare.com>`__ for tons of way cool
   images.
#. You can run MapTool on your computer. MapTool requires Java 1.5 to be
   installed on your machine; it's up to you to go find and handle that
   business.

So here we go. To begin with, the no-brainers:

#. Get MapTool from http://rptools.net. The latest "build" version of
   MapTool can always be found at the top of `this
   list <http://www.rptools.net/index.php?page=downloads#MapTool>`__.
   Currently, the latest build is 1.3.b88 (b88 is broken, however, and
   b87 should be used). **NOTE**: You can also run the `Java
   WebStart <http://www.rptools.net/index.php?page=launch>`__ to run
   MapTool without downloading and unzipping the file.
#. If you download the zip file of MapTool, unzip it somewhere on your
   computer and make sure it runs. The built in .bat files set some
   parameters when you run, like allocated memory and so forth. It will
   run if you double-click on the .jar file, but it will give you
   warnings. If you use Windows, you can use the Windows Launcher as
   well, which makes altering the settings very convenient.

Now, let's get some useful mapping going.

.. _getting_images_into_your_maptool_resource_library:

Getting Images into your MapTool Resource Library
=================================================

| MapTool's **Resource Library** is actually a collection of "pointers"
  or "links" to folders on your computer containing images you want to
  use with MapTool. MapTool comes with a default set of images, but you
  can add any images you wish - you are in control of what images are
  available to MapTool.
| |Mt-f-addtoreslib.jpg‎|

.. figure:: Add-asset-dialog.jpg
   :alt: Add-asset-dialog.jpg

   Add-asset-dialog.jpg

1. Obtain some images (maps, for instance) from somewhere: these can be
downloaded off the web, or created by you. Put them in a directory where
you'll remember them - this directory is important for step 3.

2. Open MapTool.

3. Select **File -> Add Resource to Library** (shown below, left). This
will open a dialog (click on the thumbnails to see the full images to
the right - note that the thumbnails are from an older version of
MapTool; the current menus may differ somewhat but the general options
remain).

4. The dialog offers three tabs - the default one is **Local
Directory**. To add images from a local directory, click the button next
to the path text field and select the directory containing the images
you wish to add. The second tab lets you designate a URL to download
resources from, and the third tab allows you to install some image packs
that are made available by various artists specifically for MapTool.

5. Once you've made your selection, click *Install>>* to have MapTool
add the images to your resource library.

**NOTE**: The name of the directory in MapTool's Resource Library will
be the same as the name of the directory you picked in step 3.

| 
| |Mtreslib.jpg|

5. Afterwards, if you select one of the folders in your resource library
(as seen in the image below), you'll see thumbnails of the images inside
that folder. NOTE: if your folder has subfolders, hit the **+** to
expand that folder tree. Also, you won't need to add that directory
again - MapTool remembers what you picked.

**NOTE**: Because the folders that appear in the Resource Library are in
reality pointers to folders on your hard drive, you don't need to worry
that MapTool is duplicating every file -- the Resource Library is just a
way for MapTool to know where the images are.

| 

.. _creating_a_map:

Creating a Map
==============

.. figure:: Map-newmap.jpg
   :alt: Map-newmap.jpg

   Map-newmap.jpg

.. figure:: Map-new-dialog.jpg
   :alt: Map-new-dialog.jpg

   Map-new-dialog.jpg

1. Go to **Map -> New Map**. This will bring up the *Map Properties*
dialog.

2. On the left hand side of the *Map Properties* dialog, you’ll see
several options and text fields.

-  **Name**: this is the map’s title. Note that if you select a map
   image, the title resets itself to the filename of the image. Best bet
   is to title the map *last*, so you can call it something you like,
   instead of xqmap2.jpg or whatever it was originally called.
-  **Cell Type**: hex or square map, or no grid at all.
-  **Distance Per Cell**: this is how many arbitrary units each cell
   covers (*e.g.*, for Dungeons & Dragons 4th Edition, since everything
   is counted in squares, you can just set this to 1)
-  **Pixels per cell**: this is how many pixels each cell should cover –
   the default is 50. This is most important for scaling to map images
   you downloaded.
-  **Vision Distance**: MapTool has vision, fog-of-war, and other
   functions, so this indicates how far, by default, a character can see
   on the map.

| 
| |Background-dialog.jpg|

3. Click the **Background** button. You’ll get a pop-up dialog offering
several options. The background texture and/or color are infinitely
tiled in all directions.

-  **Swatch**: lets you use a uniform color as the map background.

   -  \ **Warning:** In versions prior to 1.5.1, if you select the
      top-leftmost swatch (the "white" swatch), MapTool will generate an
      error. The error will not cause MapTool to crash or anything, but
      it will not set the background to white. Simply select a different
      color first and then select white.

-  **Hue/RGB**: lets you specify colors instead of selecting a color
   swatch
-  **Texture** (what I use most often): gives you access to your
   resource library, where you can select a texture to serve as the
   background.

| 
| |Map-mapbutton.jpg|

4. If you have a map image in mind (like a downloaded one, or one you
created in Photoshop or something like that), click the **Map** button.
You’ll be taken to a dialog that shows your Resource Library. Select the
image you want to use. This image will be layered above the background
you already selected.

| 
| |Map-create-done.jpg|

5. When you’re satisfied with the background and map – you’ll be given a
preview thumbnail to double check, as shown below - give it a title, and
click **OK**. The map will now be loaded into the main window of
MapTool.

| 

.. _creating_multiple_maps_in_one_campaign:

Creating Multiple Maps in One Campaign
--------------------------------------

MapTool lets you create multiple maps, all of which will be in one
campaign. The process is very simple: you simply repeat the `Creating a
Map <Introduction_to_Mapping#Creating_a_Map>`__ steps for each new map,
selecting a new image, background color/texture, and title for each new
map.

Each new map you create will automatically be created within the
campaign you are currently working on (creating a new map does not
automatically save your campaign, so make sure to `save your
work <Introduction_to_Mapping#Saving_Your_Work>`__ when you're
finished).

You can also add new maps to a campaign you've already saved - just open
the campaign file (by going to **File > Open Campaign**) and follow the
steps to create a new map.

.. _maptool_main_window:

MapTool Main Window
===================

.. _maptool_layers:

MapTool Layers
--------------

.. figure:: Layer-window.png
   :alt: Layer-window.png

   Layer-window.png

Once you have a map loaded, you’ll see a small box in the map window
titled *Layer*. MapTool maps have four layers:

-  **Background**: this is the layer for images, background maps, and
   anything that isn’t going to move.
-  **Hidden**: for online games, this is a layer only the GM can see.
-  **Object**: this is a layer for token-like objects, things that might
   move, or that players might be able to move (lamps, tables, etc.).
-  **Token**: this layer is the layer that tokens go on (tokens are
   small images that represent characters or NPCs). Make sure you have
   the Token layer selected when you’re adding characters and enemies to
   the map.

Think of the MapTool Layers as four different sheets of acetate or
tracing paper, one on top of the other. The bottom one - the
**Background** - is where you draw the basic parts of the map: walls,
floors, trees, etc. On the next sheet of tracing paper, the one called
**Objects** you draw the *things* that your characters might use, mess
with, or break: doors, chests, tables, chairs, and so forth. On the next
one up - the **Hidden** layer - you put things only the GM can see
(which might be objects *or* hidden characters!). Finally, on the very
top layer - the **Token** layer, you put your miniatures - the monsters,
characters, and NPCs of the game world.

Tokens can be put on any of the 4 layers in MapTool. To do so, just
right-click on the token image, and select **Change To >**. In the menu,
select the layer you want to change the token to, and it will be moved.

.. _selecting_maps:

Selecting Maps
--------------

.. figure:: Blueglobe.jpg
   :alt: Blueglobe.jpg

   Blueglobe.jpg

.. figure:: Maplist.jpg
   :alt: Maplist.jpg

   Maplist.jpg

If you create only one map in your campaign, it will be loaded by
default and will be the only map you can see.

If you `create multiple
maps <Introduction_to_Mapping#Creating_Multiple_Maps_in_One_Campaign>`__
or have a campaign with multiple maps, you can choose between them by
clicking the blue globe icon in the upper right hand side of the MapTool
window – this will present a list of possible maps. Note that if you
have only one map, clicking on the blue globe will show that map's name.

| 

.. _zooming_and_moving:

Zooming and Moving
------------------

To zoom the map, you can use the mouse scroll wheel (if you have one),
or you can use the equals sign to zoom in, and the hyphen to zoom out.

Hitting the plus sign will zoom to 1:1.

To move the map, right click on it and move the mouse. This will pan the
map in any direction.

.. _token_basics:

Token Basics
============

`MapTool Tokens <Token:token>`__ (or just "Tokens") are small images
that act as visual representations of many things in a MapTool map. The
most common use for tokens is to represent player and non-player
characters - in other words, tokens take the place of miniatures on the
virtual map.

Tokens, like everything else, start as image files that are stored in
your `Resource Library <Macros:Glossary#R>`__. MapTool comes with some
default tokens (and they have a great, separate program called
`TokenTool <http://www.rptools.net/index.php?page=tokentool>`__ that
lets you make tokens), or you can supply your own from wherever you find
them.

This section of the Introduction to Mapping guide deals with only a few
of the most basic, common things you might want to do with MapTool
Tokens. There are *many* features, tricks, and cool functions available
when working with tokens - so many that they deserve a guide all to
themselves.

.. _placing_tokens_on_the_map:

Placing Tokens on the Map
-------------------------

.. figure:: Default-library.jpg
   :alt: Default-library.jpg

   Default-library.jpg

1. To see the default tokens mentioned above, go to the Default folder
in your *Resource Library*, and click the **+** to expand it.

| 
| |Default-tokens.jpg|

2. Select the Tokens folder.

| 
| |Token-drag-to-map.jpg|

.. figure:: Token-on-map.jpg
   :alt: Token-on-map.jpg

   Token-on-map.jpg

3. In the window below (where the thumbnails appear), use the mouse to
drag a token onto the map. The cursor will change to a hand, and you
just need to hold the token over the map somewhere and release the
button.

When you release the mouse button, the token will appear on the map, as
shown in the thumbnail.

| 

.. _moving_tokens:

Moving Tokens
-------------

Once a token is on the map, it can be dragged around using the mouse, or
moved by selecting the token (clicking on it) and using the arrow keys
to move the token, and pressing the **D** key to complete the move.

If you want to create a complex path, you can hit the space bar to make
a waypoint in your path.

.. _changing_a_tokens_name_gm_name_and_label:

Changing a Token's Name, GM Name, and Label
-------------------------------------------

.. figure:: Token-default-name.jpg
   :alt: Token-default-name.jpg

   Token-default-name.jpg

.. figure:: Edit-token.jpg
   :alt: Edit-token.jpg

   Edit-token.jpg

Tokens have three possible "names" you can assign to them. When a token
is first dragged onto the map, it is given a default name (typically,
the same as the token's *filename* on your computer, with the extension
trimmed off). For example, the token shown in the image below was
dragged from MapTool's default token set, and its default name is
"Hero."

The three possible names a token can have are:

-  **Token Name**: The name of the token that will appear to all users.
   This is not optional.

   -  \ **NOTE**: Make sure each token has a unique name! Otherwise,
      MapTool macros may behave unpredictably.

-  **GM Name**: This name appears only to the person(s) currently
   connected to MapTool in the role of "GM."
-  **Label**: This text appears below the Token Name, and is visible to
   all connected individuals.

To change a token's name, GM name, and/or label:

1. Double-click on the token image on the map. This will open the **Edit
Token** dialog, as shown below.

| 
| |Edit-token-changednames.jpg|

.. figure:: New-token-names.jpg
   :alt: New-token-names.jpg

   New-token-names.jpg

2. In the **Name** field, enter the name you'd like. For this example,
I've entered "Bork the Brave"

3. In the **GM Name** field, enter a name. For this example, I've
entered "Cork the Cowardly"

4. In the **Label** field, enter a Label. For this example, I've entered
"Human Warrior".

5. Click **OK** to save your changes.

Once you've clicked okay, you'll see that the token has changed:

You can do this name changing process with any token you drop on the
map.

| 

.. _changing_a_tokens_image:

Changing a Token's Image
------------------------

Sometimes, when you create a new token, you will want to change the
image on the token's face. Say, for instance, you find a cool new
picture that you just *have* to use for your evil overlord, but you
already have a token made up for him - you don't want to delete the
whole token just to change the image, right? That's overkill. Instead,
just change the token image using the following steps:

.. figure:: Edit-token.jpg
   :alt: Edit-token.jpg

   Edit-token.jpg

1. Make sure you have a new token image in PNG or JPG format, already
available in your MapTool Resource Library. If you look at `Getting
Images Into your MapTool Resource
Library <Introduction_to_Mapping#Getting_Images_into_your_MapTool_Resource_Library>`__
section, above, it talks about how to get map images into your Resource
Library: well, token images (in fact, *any* image) can be added to your
resource library in exactly the same way.

2. Double-click on the token to open the **Edit Token** dialog.

| 
| |Edit-token-changeimage.jpg|

3. In the upper-left of that dialog, click the small green plus sign.

| 
| |New-image-picked.jpg|

4. In the **Choose Image** dialog, select the Resource Library folder
that has the new token image in it (a red-and-white border will indicate
the image you've selected), and click **OK**.

| 
| |Token-image-changed.jpg|

5. Once you hit **OK**, you are taken back to the Edit Token dialog, and
you will see that the token image has been changed to the one you
selected.

| 

.. _changing_token_size:

Changing Token Size
-------------------

.. figure:: Token-rightclick.jpg
   :alt: Token-rightclick.jpg

   Token-rightclick.jpg

Tokens will default to the size of one grid square (note that by
default, MapTool’s grid is 50x50 pixels). If you right-click on a token,
the menu has a lot of options – one of which is **Size**. You can then
set it using the size values there, so you can make large or huge or
gargantuan creatures, and so forth. The image below illustrates the
right-click menu for a token.

NOTE: these size values (large, huge, gargantuan, etc.) only apply to
maps that have a grid (remember, when you create a map, you have the
option to make a map with no grid). If you use a gridless map, the size
values are more fine-grained.

| 
| ==Saving Your Work==

MapTool's default "save" format is called a *Campaign File*. The
Campaign File (which has the extension *.cmpgn*) contains the maps and
tokens that you've set up. If you're interested in this sort of thing,
the campaign file is actually a zipped XML file.

To save your work so far, choose **File -> Save Campaign**, give your
campaign a name, and that’s all there is to it.

When you save a campaign, MapTool saves the locations of the tokens on
all of the maps, so you can pick up right where you left off!

.. _exporting_map_images:

Exporting Map Images
====================

MapTool can export your map images to an image file (PNG format). To
export an image to a location of your choice:

1. Go to **File->Export** and select **Screenshot As**.

2. In the dialog that comes up, select a "View" (either GM view, where
you can see everything, or Player View, where the only things visible
are what *players* can see...I told you MapTool had some cool vision
capabilities!)

3. Select the destination for your file using the Browse button (or,
alternatively, send it to an FTP server)

4. Click **Export**.

.. _next_steps:

Next Steps
==========

Now that you can create a basic map and put some tokens on it, the next
step is connecting up with some friends over the Internet (or face to
face) and using it for a game session! This topic is covered in the
`Introduction to Game Hosting <Introduction_to_Game_Hosting>`__.

`Category:MapTool <Category:MapTool>`__
`Category:Tutorial <Category:Tutorial>`__

.. |Mt-f-addtoreslib.jpg‎| image:: Mt-f-addtoreslib.jpg‎
.. |Mtreslib.jpg| image:: Mtreslib.jpg
.. |Background-dialog.jpg| image:: Background-dialog.jpg
.. |Map-mapbutton.jpg| image:: Map-mapbutton.jpg
.. |Map-create-done.jpg| image:: Map-create-done.jpg
.. |Default-tokens.jpg| image:: Default-tokens.jpg
.. |Token-drag-to-map.jpg| image:: Token-drag-to-map.jpg
.. |Edit-token-changednames.jpg| image:: Edit-token-changednames.jpg
.. |Edit-token-changeimage.jpg| image:: Edit-token-changeimage.jpg
.. |New-image-picked.jpg| image:: New-image-picked.jpg
.. |Token-image-changed.jpg| image:: Token-image-changed.jpg
