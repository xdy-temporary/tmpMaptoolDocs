====================================
Introduction to Mapping - MapToolDoc
====================================

.. contents::
   :depth: 3
..

.. container:: noprint
   :name: mw-page-base

.. container:: noprint
   :name: mw-head-base

.. container:: mw-body
   :name: content

   .. container:: mw-indicators

   .. rubric:: Introduction to Mapping
      :name: firstHeading
      :class: firstHeading

   .. container:: mw-body-content
      :name: bodyContent

      .. container::
         :name: siteSub

         From MapToolDoc

      .. container::
         :name: contentSub

      .. container:: mw-jump
         :name: jump-to-nav

         Jump to: `navigation <#mw-head>`__, `search <#p-search>`__

      .. container:: mw-content-ltr
         :name: mw-content-text

         .. container:: template_languages

            Languages:  English
             • \ `Deutsch </rptools/wiki/Introduction_to_Mapping/de>`__\ 
             • \ `español </rptools/wiki/Introduction_to_Mapping/es>`__\  • \ `français </rptools/wiki/Introduction_to_Mapping/fr>`__\  • \ `italiano </rptools/wiki/Introduction_to_Mapping/it>`__\  • \ `日本語 </rptools/wiki/Introduction_to_Mapping/ja>`__\ 

         .. container:: template_beginner

            | BEGINNER
            | THIS IS A BEGINNER ARTICLE

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 Introduction <#Introduction>`__

               -  `1.1 First Things First: What is
                  MapTool? <#First_Things_First:_What_is_MapTool.3F>`__
               -  `1.2 About this Guide <#About_this_Guide>`__

            -  `2 Getting Images into your MapTool Resource
               Library <#Getting_Images_into_your_MapTool_Resource_Library>`__
            -  `3 Creating a Map <#Creating_a_Map>`__

               -  `3.1 Creating Multiple Maps in One
                  Campaign <#Creating_Multiple_Maps_in_One_Campaign>`__

            -  `4 MapTool Main Window <#MapTool_Main_Window>`__

               -  `4.1 MapTool Layers <#MapTool_Layers>`__
               -  `4.2 Selecting Maps <#Selecting_Maps>`__
               -  `4.3 Zooming and Moving <#Zooming_and_Moving>`__

            -  `5 Token Basics <#Token_Basics>`__

               -  `5.1 Placing Tokens on the
                  Map <#Placing_Tokens_on_the_Map>`__
               -  `5.2 Moving Tokens <#Moving_Tokens>`__
               -  `5.3 Changing a Token's Name, GM Name, and
                  Label <#Changing_a_Token.27s_Name.2C_GM_Name.2C_and_Label>`__
               -  `5.4 Changing a Token's
                  Image <#Changing_a_Token.27s_Image>`__
               -  `5.5 Changing Token Size <#Changing_Token_Size>`__

            -  `6 Saving Your Work <#Saving_Your_Work>`__
            -  `7 Exporting Map Images <#Exporting_Map_Images>`__
            -  `8 Next Steps <#Next_Steps>`__

         .. rubric:: Introduction
            :name: introduction

         .. rubric:: First Things First: What is MapTool?
            :name: first-things-first-what-is-maptool

         Although you probably have an idea what MapTool is and does, I
         just want to take a moment to reinforce the main goal of
         MapTool:

         **MapTool is a program that helps you share a "virtual
         tabletop" with your friends, so you can play games on it.**

         That is what MapTool does, and its features are aimed at
         providing a continuum of options, from the simple to the
         complex, to achieve that goal.

         In all the talk of macros and properties and tables and
         scripting that will follow in this and other guides, don't lose
         sight of the reason you're checking MapTool out anyway: it's a
         way to play games with friends.

         .. rubric:: About this Guide
            :name: about-this-guide

         The purpose of this guide is not to delve into the seamy
         underbelly of MapTool's macro scripting system, lighting,
         properties, or any of that complex stuff. Instead, this guide
         should get you started on the path of using MapTool as a
         *mapping* program for role-playing games. Other guides address
         topics like `hosting an online
         game </rptools/wiki/Introduction_to_Game_Hosting>`__, `working
         with tokens </rptools/wiki/Introduction_to_Tokens>`__, `setting
         up vision and
         light </rptools/wiki/Introduction_to_Lights_and_Sights>`__, and
         `writing
         macros </rptools/wiki/Introduction_to_Macro_Writing>`__.

         The following instructions should get you up and running with
         MapTool to use as a battle mapping/general mapping tool. This
         assumes a few things:

         #. You know how to create or get some map images. There are
            terabytes (exabytes! yottabytes!) of map images out there on
            the web. Check out the `RPTools
            Gallery <http://gallery.rptools.net>`__ or
            `RPGMapShare <http://www.rpgmapshare.com>`__ for tons of way
            cool images.
         #. You can run MapTool on your computer. MapTool requires Java
            1.5 to be installed on your machine; it's up to you to go
            find and handle that business.

         So here we go. To begin with, the no-brainers:

         #. Get MapTool from http://rptools.net. The latest "build"
            version of MapTool can always be found at the top of `this
            list <http://www.rptools.net/index.php?page=downloads#MapTool>`__.
            Currently, the latest build is 1.3.b88 (b88 is broken,
            however, and b87 should be used). **NOTE**: You can also run
            the `Java
            WebStart <http://www.rptools.net/index.php?page=launch>`__
            to run MapTool without downloading and unzipping the file.
         #. If you download the zip file of MapTool, unzip it somewhere
            on your computer and make sure it runs. The built in .bat
            files set some parameters when you run, like allocated
            memory and so forth. It will run if you double-click on the
            .jar file, but it will give you warnings. If you use
            Windows, you can use the Windows Launcher as well, which
            makes altering the settings very convenient.

         Now, let's get some useful mapping going.

         .. rubric:: Getting Images into your MapTool Resource Library
            :name: getting-images-into-your-maptool-resource-library

         | MapTool's **Resource Library** is actually a collection of
           "pointers" or "links" to folders on your computer containing
           images you want to use with MapTool. MapTool comes with a
           default set of images, but you can add any images you wish -
           you are in control of what images are available to MapTool.

         .. container:: thumb tright

            .. container:: thumbinner

               |image0|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` </rptools/wiki/File:Mt-f-addtoreslib.jpg>`__

                  File menu showing **Add to Resource Library**

         .. container:: thumb tright

            .. container:: thumbinner

               |image1|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` </rptools/wiki/File:Add-asset-dialog.jpg>`__

                  **Add Resource to Library** dialog

         1. Obtain some images (maps, for instance) from somewhere:
         these can be downloaded off the web, or created by you. Put
         them in a directory where you'll remember them - this directory
         is important for step 3.

         2. Open MapTool.

         3. Select **File -> Add Resource to Library** (shown below,
         left). This will open a dialog (click on the thumbnails to see
         the full images to the right - note that the thumbnails are
         from an older version of MapTool; the current menus may differ
         somewhat but the general options remain).

         4. The dialog offers three tabs - the default one is **Local
         Directory**. To add images from a local directory, click the
         button next to the path text field and select the directory
         containing the images you wish to add. The second tab lets you
         designate a URL to download resources from, and the third tab
         allows you to install some image packs that are made available
         by various artists specifically for MapTool.

         5. Once you've made your selection, click *Install>>* to have
         MapTool add the images to your resource library.

         **NOTE**: The name of the directory in MapTool's Resource
         Library will be the same as the name of the directory you
         picked in step 3.

         | 

         .. container:: thumb tright

            .. container:: thumbinner

               |image2|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` </rptools/wiki/File:Mtreslib.jpg>`__

                  Folders in the MapTool Resource Library. These are
                  pointers to folders on your hard drive.

         5. Afterwards, if you select one of the folders in your
         resource library (as seen in the image below), you'll see
         thumbnails of the images inside that folder. NOTE: if your
         folder has subfolders, hit the **+** to expand that folder
         tree. Also, you won't need to add that directory again -
         MapTool remembers what you picked.

         **NOTE**: Because the folders that appear in the Resource
         Library are in reality pointers to folders on your hard drive,
         you don't need to worry that MapTool is duplicating every file
         -- the Resource Library is just a way for MapTool to know where
         the images are.

         | 

         .. rubric:: Creating a Map
            :name: creating-a-map

         .. container:: thumb tright

            .. container:: thumbinner

               |image3|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` </rptools/wiki/File:Map-newmap.jpg>`__

                  The **New Map** menu item

         .. container:: thumb tright

            .. container:: thumbinner

               |image4|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` </rptools/wiki/File:Map-new-dialog.jpg>`__

                  The **Map Properties** dialog

         1. Go to **Map -> New Map**. This will bring up the *Map
         Properties* dialog.

         2. On the left hand side of the *Map Properties* dialog, you’ll
         see several options and text fields.

         -  **Name**: this is the map’s title. Note that if you select a
            map image, the title resets itself to the filename of the
            image. Best bet is to title the map *last*, so you can call
            it something you like, instead of xqmap2.jpg or whatever it
            was originally called.
         -  **Cell Type**: hex or square map, or no grid at all.
         -  **Distance Per Cell**: this is how many arbitrary units each
            cell covers (*e.g.*, for Dungeons & Dragons 4th Edition,
            since everything is counted in squares, you can just set
            this to 1)
         -  **Pixels per cell**: this is how many pixels each cell
            should cover – the default is 50. This is most important for
            scaling to map images you downloaded.
         -  **Vision Distance**: MapTool has vision, fog-of-war, and
            other functions, so this indicates how far, by default, a
            character can see on the map.

         | 

         .. container:: thumb tright

            .. container:: thumbinner

               |image5|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` </rptools/wiki/File:Background-dialog.jpg>`__

                  The **Choose Background** dialog

         3. Click the **Background** button. You’ll get a pop-up dialog
         offering several options. The background texture and/or color
         are infinitely tiled in all directions.

         -  **Swatch**: lets you use a uniform color as the map
            background.

            -  **Warning:** In versions prior to 1.5.1, if you select
               the top-leftmost swatch (the "white" swatch), MapTool
               will generate an error. The error will not cause MapTool
               to crash or anything, but it will not set the background
               to white. Simply select a different color first and then
               select white.

         -  **Hue/RGB**: lets you specify colors instead of selecting a
            color swatch
         -  **Texture** (what I use most often): gives you access to
            your resource library, where you can select a texture to
            serve as the background.

         | 

         .. container:: thumb tright

            .. container:: thumbinner

               |image6|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` </rptools/wiki/File:Map-mapbutton.jpg>`__

                  The **Map** button on the map properties dialog

         4. If you have a map image in mind (like a downloaded one, or
         one you created in Photoshop or something like that), click the
         **Map** button. You’ll be taken to a dialog that shows your
         Resource Library. Select the image you want to use. This image
         will be layered above the background you already selected.

         | 

         .. container:: thumb tright

            .. container:: thumbinner

               |image7|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` </rptools/wiki/File:Map-create-done.jpg>`__

                  The **Map Properties** dialog after a map has been
                  selected from the Resource Library. Note the map
                  thumbnail in the preview.

         5. When you’re satisfied with the background and map – you’ll
         be given a preview thumbnail to double check, as shown below -
         give it a title, and click **OK**. The map will now be loaded
         into the main window of MapTool.

         | 

         .. rubric:: Creating Multiple Maps in One Campaign
            :name: creating-multiple-maps-in-one-campaign

         MapTool lets you create multiple maps, all of which will be in
         one campaign. The process is very simple: you simply repeat the
         `Creating a
         Map </rptools/wiki/Introduction_to_Mapping#Creating_a_Map>`__
         steps for each new map, selecting a new image, background
         color/texture, and title for each new map.

         Each new map you create will automatically be created within
         the campaign you are currently working on (creating a new map
         does not automatically save your campaign, so make sure to
         `save your
         work </rptools/wiki/Introduction_to_Mapping#Saving_Your_Work>`__
         when you're finished).

         You can also add new maps to a campaign you've already saved -
         just open the campaign file (by going to **File > Open
         Campaign**) and follow the steps to create a new map.

         .. rubric:: MapTool Main Window
            :name: maptool-main-window

         .. rubric:: MapTool Layers
            :name: maptool-layers

         .. container:: thumb tright

            .. container:: thumbinner

               |image8|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` </rptools/wiki/File:Layer-window.png>`__

                  The **Layer** window, which is present on all maps in
                  MapTool

         Once you have a map loaded, you’ll see a small box in the map
         window titled *Layer*. MapTool maps have four layers:

         -  **Background**: this is the layer for images, background
            maps, and anything that isn’t going to move.
         -  **Hidden**: for online games, this is a layer only the GM
            can see.
         -  **Object**: this is a layer for token-like objects, things
            that might move, or that players might be able to move
            (lamps, tables, etc.).
         -  **Token**: this layer is the layer that tokens go on (tokens
            are small images that represent characters or NPCs). Make
            sure you have the Token layer selected when you’re adding
            characters and enemies to the map.

         Think of the MapTool Layers as four different sheets of acetate
         or tracing paper, one on top of the other. The bottom one - the
         **Background** - is where you draw the basic parts of the map:
         walls, floors, trees, etc. On the next sheet of tracing paper,
         the one called **Objects** you draw the *things* that your
         characters might use, mess with, or break: doors, chests,
         tables, chairs, and so forth. On the next one up - the
         **Hidden** layer - you put things only the GM can see (which
         might be objects *or* hidden characters!). Finally, on the very
         top layer - the **Token** layer, you put your miniatures - the
         monsters, characters, and NPCs of the game world.

         Tokens can be put on any of the 4 layers in MapTool. To do so,
         just right-click on the token image, and select **Change To
         >**. In the menu, select the layer you want to change the token
         to, and it will be moved.

         .. rubric:: Selecting Maps
            :name: selecting-maps

         .. container:: thumb tright

            .. container:: thumbinner

               |image9|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` </rptools/wiki/File:Blueglobe.jpg>`__

                  The Globe button, where you can select among your maps

         .. container:: thumb tright

            .. container:: thumbinner

               |image10|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` </rptools/wiki/File:Maplist.jpg>`__

                  A list of maps, which appears after you click the
                  Globe button.

         If you create only one map in your campaign, it will be loaded
         by default and will be the only map you can see.

         If you `create multiple
         maps </rptools/wiki/Introduction_to_Mapping#Creating_Multiple_Maps_in_One_Campaign>`__
         or have a campaign with multiple maps, you can choose between
         them by clicking the blue globe icon in the upper right hand
         side of the MapTool window – this will present a list of
         possible maps. Note that if you have only one map, clicking on
         the blue globe will show that map's name.

         | 

         .. rubric:: Zooming and Moving
            :name: zooming-and-moving

         To zoom the map, you can use the mouse scroll wheel (if you
         have one), or you can use the equals sign to zoom in, and the
         hyphen to zoom out.

         Hitting the plus sign will zoom to 1:1.

         To move the map, right click on it and move the mouse. This
         will pan the map in any direction.

         .. rubric:: Token Basics
            :name: token-basics

         `MapTool Tokens </rptools/wiki/Token:token>`__ (or just
         "Tokens") are small images that act as visual representations
         of many things in a MapTool map. The most common use for tokens
         is to represent player and non-player characters - in other
         words, tokens take the place of miniatures on the virtual map.

         Tokens, like everything else, start as image files that are
         stored in your `Resource
         Library </rptools/wiki/Macros:Glossary#R>`__. MapTool comes
         with some default tokens (and they have a great, separate
         program called
         `TokenTool <http://www.rptools.net/index.php?page=tokentool>`__
         that lets you make tokens), or you can supply your own from
         wherever you find them.

         This section of the Introduction to Mapping guide deals with
         only a few of the most basic, common things you might want to
         do with MapTool Tokens. There are *many* features, tricks, and
         cool functions available when working with tokens - so many
         that they deserve a guide all to themselves.

         .. rubric:: Placing Tokens on the Map
            :name: placing-tokens-on-the-map

         .. container:: thumb tright

            .. container:: thumbinner

               |image11|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` </rptools/wiki/File:Default-library.jpg>`__

                  The *Default* folder in the Resource Library

         1. To see the default tokens mentioned above, go to the Default
         folder in your *Resource Library*, and click the **+** to
         expand it.

         | 

         .. container:: thumb tright

            .. container:: thumbinner

               |image12|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` </rptools/wiki/File:Default-tokens.jpg>`__

                  The *Tokens* subfolder

         2. Select the Tokens folder.

         | 

         .. container:: thumb tright

            .. container:: thumbinner

               |image13|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` </rptools/wiki/File:Token-drag-to-map.jpg>`__

                  Dragging a token onto the map

         .. container:: thumb tright

            .. container:: thumbinner

               |image14|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` </rptools/wiki/File:Token-on-map.jpg>`__

                  The token appears!

         3. In the window below (where the thumbnails appear), use the
         mouse to drag a token onto the map. The cursor will change to a
         hand, and you just need to hold the token over the map
         somewhere and release the button.

         When you release the mouse button, the token will appear on the
         map, as shown in the thumbnail.

         | 

         .. rubric:: Moving Tokens
            :name: moving-tokens

         Once a token is on the map, it can be dragged around using the
         mouse, or moved by selecting the token (clicking on it) and
         using the arrow keys to move the token, and pressing the **D**
         key to complete the move.

         If you want to create a complex path, you can hit the space bar
         to make a waypoint in your path.

         .. rubric:: Changing a Token's Name, GM Name, and Label
            :name: changing-a-tokens-name-gm-name-and-label

         .. container:: thumb tright

            .. container:: thumbinner

               |image15|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` </rptools/wiki/File:Token-default-name.jpg>`__

                  A token, showing the default name assigned when it was
                  first dragged onto the map.

         .. container:: thumb tright

            .. container:: thumbinner

               |image16|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` </rptools/wiki/File:Edit-token.jpg>`__

                  The **Edit Token** dialog

         Tokens have three possible "names" you can assign to them. When
         a token is first dragged onto the map, it is given a default
         name (typically, the same as the token's *filename* on your
         computer, with the extension trimmed off). For example, the
         token shown in the image below was dragged from MapTool's
         default token set, and its default name is "Hero."

         The three possible names a token can have are:

         -  **Token Name**: The name of the token that will appear to
            all users. This is not optional.

            -  **NOTE**: Make sure each token has a unique name!
               Otherwise, MapTool macros may behave unpredictably.

         -  **GM Name**: This name appears only to the person(s)
            currently connected to MapTool in the role of "GM."
         -  **Label**: This text appears below the Token Name, and is
            visible to all connected individuals.

         To change a token's name, GM name, and/or label:

         1. Double-click on the token image on the map. This will open
         the **Edit Token** dialog, as shown below.

         | 

         .. container:: thumb tright

            .. container:: thumbinner

               |image17|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` </rptools/wiki/File:Edit-token-changednames.jpg>`__

                  Editing the token's name, GM name, and label

         .. container:: thumb tright

            .. container:: thumbinner

               |image18|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` </rptools/wiki/File:New-token-names.jpg>`__

                  Token showing the new names and label

         2. In the **Name** field, enter the name you'd like. For this
         example, I've entered "Bork the Brave"

         3. In the **GM Name** field, enter a name. For this example,
         I've entered "Cork the Cowardly"

         4. In the **Label** field, enter a Label. For this example,
         I've entered "Human Warrior".

         5. Click **OK** to save your changes.

         Once you've clicked okay, you'll see that the token has
         changed:

         You can do this name changing process with any token you drop
         on the map.

         | 

         .. rubric:: Changing a Token's Image
            :name: changing-a-tokens-image

         Sometimes, when you create a new token, you will want to change
         the image on the token's face. Say, for instance, you find a
         cool new picture that you just *have* to use for your evil
         overlord, but you already have a token made up for him - you
         don't want to delete the whole token just to change the image,
         right? That's overkill. Instead, just change the token image
         using the following steps:

         .. container:: thumb tright

            .. container:: thumbinner

               |image19|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` </rptools/wiki/File:Edit-token.jpg>`__

                  The **Edit Token** dialog

         1. Make sure you have a new token image in PNG or JPG format,
         already available in your MapTool Resource Library. If you look
         at `Getting Images Into your MapTool Resource
         Library </rptools/wiki/Introduction_to_Mapping#Getting_Images_into_your_MapTool_Resource_Library>`__
         section, above, it talks about how to get map images into your
         Resource Library: well, token images (in fact, *any* image) can
         be added to your resource library in exactly the same way.

         2. Double-click on the token to open the **Edit Token** dialog.

         | 

         .. container:: thumb tright

            .. container:: thumbinner

               |image20|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` </rptools/wiki/File:Edit-token-changeimage.jpg>`__

                  The button to change the token image

         3. In the upper-left of that dialog, click the small green plus
         sign.

         | 

         .. container:: thumb tright

            .. container:: thumbinner

               |image21|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` </rptools/wiki/File:New-image-picked.jpg>`__

                  A new image is selected from the resource library

         4. In the **Choose Image** dialog, select the Resource Library
         folder that has the new token image in it (a red-and-white
         border will indicate the image you've selected), and click
         **OK**.

         | 

         .. container:: thumb tright

            .. container:: thumbinner

               |image22|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` </rptools/wiki/File:Token-image-changed.jpg>`__

                  The token's image has been changed

         5. Once you hit **OK**, you are taken back to the Edit Token
         dialog, and you will see that the token image has been changed
         to the one you selected.

         | 

         .. rubric:: Changing Token Size
            :name: changing-token-size

         .. container:: thumb tright

            .. container:: thumbinner

               |image23|

               .. container:: thumbcaption

                  .. container:: magnify

                     ` </rptools/wiki/File:Token-rightclick.jpg>`__

                  Changing the token size using the right-click menu

         Tokens will default to the size of one grid square (note that
         by default, MapTool’s grid is 50x50 pixels). If you right-click
         on a token, the menu has a lot of options – one of which is
         **Size**. You can then set it using the size values there, so
         you can make large or huge or gargantuan creatures, and so
         forth. The image below illustrates the right-click menu for a
         token.

         NOTE: these size values (large, huge, gargantuan, etc.) only
         apply to maps that have a grid (remember, when you create a
         map, you have the option to make a map with no grid). If you
         use a gridless map, the size values are more fine-grained.

         | 

         .. rubric:: Saving Your Work
            :name: saving-your-work

         MapTool's default "save" format is called a *Campaign File*.
         The Campaign File (which has the extension *.cmpgn*) contains
         the maps and tokens that you've set up. If you're interested in
         this sort of thing, the campaign file is actually a zipped XML
         file.

         To save your work so far, choose **File -> Save Campaign**,
         give your campaign a name, and that’s all there is to it.

         When you save a campaign, MapTool saves the locations of the
         tokens on all of the maps, so you can pick up right where you
         left off!

         .. rubric:: Exporting Map Images
            :name: exporting-map-images

         MapTool can export your map images to an image file (PNG
         format). To export an image to a location of your choice:

         1. Go to **File->Export** and select **Screenshot As**.

         2. In the dialog that comes up, select a "View" (either GM
         view, where you can see everything, or Player View, where the
         only things visible are what *players* can see...I told you
         MapTool had some cool vision capabilities!)

         3. Select the destination for your file using the Browse button
         (or, alternatively, send it to an FTP server)

         4. Click **Export**.

         .. rubric:: Next Steps
            :name: next-steps

         Now that you can create a basic map and put some tokens on it,
         the next step is connecting up with some friends over the
         Internet (or face to face) and using it for a game session!
         This topic is covered in the `Introduction to Game
         Hosting </rptools/wiki/Introduction_to_Game_Hosting>`__.

         .. container:: template_languages

            Languages:  English
             • \ `Deutsch </rptools/wiki/Introduction_to_Mapping/de>`__\ 
             • \ `español </rptools/wiki/Introduction_to_Mapping/es>`__\  • \ `français </rptools/wiki/Introduction_to_Mapping/fr>`__\  • \ `italiano </rptools/wiki/Introduction_to_Mapping/it>`__\  • \ `日本語 </rptools/wiki/Introduction_to_Mapping/ja>`__\ 

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Introduction_to_Mapping&oldid=7567"

