==================
Token - MapToolDoc
==================

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

   .. rubric:: Token
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
             • \ `日本語 </rptools/wiki/Token/ja>`__\ 

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 Token: token <#Token:_token>`__

               -  `1.1 Overall File Format <#Overall_File_Format>`__
               -  `1.2 Examining the Contents of a Token
                  File <#Examining_the_Contents_of_a_Token_File>`__
               -  `1.3 Modifying the Images or Other Data Inside a Token
                  File <#Modifying_the_Images_or_Other_Data_Inside_a_Token_File>`__

         .. rubric:: Token: token
            :name: token-token

         Every object that can be dropped down on a map and manipulated
         by the GM or the players is a *token* of some type. The
         possible token types are `Image
         Token </rptools/wiki/Image_Token>`__, `Library
         Token </rptools/wiki/Library_Token>`__, `PC
         Token </maptool/index.php?title=PC_Token&action=edit&redlink=1>`__,
         and `NPC
         Token </maptool/index.php?title=NPC_Token&action=edit&redlink=1>`__.
         In addition, when images are dropped onto a `map
         layer </maptool/index.php?title=map_layer&action=edit&redlink=1>`__
         other than the **Token** layer, they take on the name *object*
         or *stamp* instead. (The term *stamp* is often used to denote
         an image that is placed repeatedly, sometimes in a pattern,
         whereas *object* means a less often used image. A forest would
         be full of **tree stamps** but an office building would have
         *table and chair objects*.)

         This page discusses how tokens and objects are saved
         externally; the overall file format as well as some specifics
         about how to manipulate the contents of the **.rptok** file.

         .. rubric:: Overall File Format
            :name: overall-file-format

         Tokens can be saved by the token owner by right-clicking on the
         token and choosing **Save As...**, then navigating to a
         directory and entering a filename. The filename will
         automatically have **.rptok** appended to the end to indicate
         that contents. The actual format of the file, however, is an
         ordinary ZIP file! This means you can rename the file to end
         with **.zip** and treat it as any other ZIP file. There are a
         number of features related to this:

         -  All tokens are automatically stored in a compressed format.
         -  All tokens can contain multiple data files inside

            -  One file is called **content.xml**
            -  Another one is **properties.xml**
            -  A directory is also included called **assets**

               -  The token image is stored here,
               -  The token portrait is stored here, and
               -  The token handout is stored here.

            -  The last file is called **thumbnail**

         .. rubric:: Examining the Contents of a Token File
            :name: examining-the-contents-of-a-token-file

         Because the token files are ZIP files, you can easily extract
         the images or other data from the token. To do so, unpack the
         ZIP file into a directory on your computer. Look inside the
         **assets** directory and you'll see multiple filenames. They
         will appear to be random strings of letters and numbers, but
         actually the are checksums of the image they contain. You can
         think of a checksum as a *summary* of the content. These files
         don't have filename extensions so you may not be able to view
         the content unless you use a program that ignores the filename
         extension and looks at the content instead. One example utility
         that does that is the GNU Image Manipulation Program, or GIMP
         for short.

         Note that some versions of MapTool (which ones?) store the
         asset as the image data encoded in XML. This makes the image
         unviewable using \_any\_ standard graphics tool. Trevor has
         said that this is a bug and future versions will use the actual
         graphics image format (JPG or PNG).

         .. rubric:: Modifying the Images or Other Data Inside a Token
            File
            :name: modifying-the-images-or-other-data-inside-a-token-file

         Modifying the images used in the token is more complex,
         however. Here are the required pieces of the puzzle:

         #. Locate the new image(s) to be stored in the token,
         #. Calculate the checksum of the image (it's an MD5 checksum),
         #. Rename the image file to be the checksum, removing any
            filename extension in the process,
         #. Move the new file into the **assets** directory,
         #. Record the name of the old image from the **assets**
            directory, and
         #. Remove the old image from the **assets** directory.

         Sounds easy, right? But that's only half of it. It turns out
         that just dumping images into the **assets** directory wouldn't
         tell MapTool enough about the image, such as what size to scale
         it to and whether it represented the portrait or handout image.
         Those details are stored in the **content.xml** file. This file
         is **NOT** in the **assets** directory, but is at the top level
         of the unpacked ZIP file.

         If you open the **content.xml** file use a text editor. Do not
         use a word processor or saving the file could corrupt the
         contents with extra information created by the word processor.
         Use a program such as Notepad or TextPad to perform any
         editing. Obviously, an editor that understands the XML syntax
         can make editing much easier.

         You need to locate the portion of the XML file that refers to
         the portrait image (if you were planning to replace the
         portrait) and replace the 16-character checksum from the old
         asset with the 16-character checksum of the new asset.
         Fortunately, you recorded that information as you performed the
         steps given above! But fear not -- if you did not record the
         old checksum value, you can simply delete the entire top-level
         directory and unpack the ZIP archive again, starting from the
         beginning.

         The simplest way to make the change, is to perform a string
         search for the old checksum, replacing it with the new one
         whenever you find it.

         After you've made all of your replacements, use a ZIP utility
         to create a ZIP file containing the contents of the top-level
         directory and everything below it in the directory structure
         (which currently means the **assets** directory). Be sure that
         the directory structure is preserved because the **assets**
         directory must be there. Now the file can be dragged and
         dropped into MapTool! You can change the filename extension to
         **.rptok** if you like, but MapTool isn't particular about the
         name of the file, only about the contents.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Token&oldid=4597"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Category </rptools/wiki/Special:Categories>`__:

            -  `Token </rptools/wiki/Category:Token>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Token </rptools/wiki/Category:Token>`__

      .. container:: visualClear

.. container::
   :name: mw-navigation

   .. rubric:: Navigation menu
      :name: navigation-menu

   .. container::
      :name: mw-head

      .. container::
         :name: p-personal

         .. rubric:: Personal tools
            :name: p-personal-label

         -  `Log
            in </maptool/index.php?title=Special:UserLogin&returnto=Token>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/Token>`__
            -  `Discussion </maptool/index.php?title=Talk:Token&action=edit&redlink=1>`__

         .. container:: vectorMenu emptyPortlet
            :name: p-variants

            .. rubric:: Variants\ ` <#>`__
               :name: p-variants-label

            .. container:: menu

      .. container::
         :name: right-navigation

         .. container:: vectorTabs
            :name: p-views

            .. rubric:: Views
               :name: p-views-label

            -  `Read </rptools/wiki/Token>`__
            -  `View
               source </maptool/index.php?title=Token&action=edit>`__
            -  `View
               history </maptool/index.php?title=Token&action=history>`__

         .. container:: vectorMenu emptyPortlet
            :name: p-cactions

            .. rubric:: More\ ` <#>`__
               :name: p-cactions-label

            .. container:: menu

         .. container::
            :name: p-search

            .. rubric:: Search
               :name: search

            .. container::
               :name: simpleSearch

   .. container::
      :name: mw-panel

      .. container::
         :name: p-logo

         ` </rptools/wiki/Main_Page>`__

      .. container:: portal
         :name: p-navigation

         .. rubric:: Navigation
            :name: p-navigation-label

         .. container:: body

            -  `Main page </rptools/wiki/Main_Page>`__
            -  `Random page </rptools/wiki/Special:Random>`__
            -  `Help <https://www.mediawiki.org/wiki/Special:MyLanguage/Help:Contents>`__

      .. container:: portal
         :name: p-Basic_Usage

         .. rubric:: Basic Usage
            :name: p-Basic_Usage-label

         .. container:: body

            -  `Tutorials </rptools/wiki/Category:Tutorial>`__
            -  `Chat Commands </rptools/wiki/Chat_Commands>`__
            -  `Dice Expressions </rptools/wiki/Dice_Expressions>`__
            -  `Glossary </rptools/wiki/Glossary>`__

      .. container:: portal
         :name: p-Macro_Reference

         .. rubric:: Macro Reference
            :name: p-Macro_Reference-label

         .. container:: body

            -  `List of
               Functions </rptools/wiki/Category:Macro_Function>`__
            -  `Roll Options </rptools/wiki/Category:Roll_Option>`__
            -  `Special
               Variables </rptools/wiki/Category:Special_Variable>`__
            -  `Macro Cookbook </rptools/wiki/Category:Cookbook>`__

      .. container:: portal
         :name: p-Editors

         .. rubric:: Editors
            :name: p-Editors-label

         .. container:: body

            -  `Editor Discussion </rptools/wiki/Editor>`__
            -  `Recent Changes </rptools/wiki/Special:RecentChanges>`__

      .. container:: portal
         :name: p-tb

         .. rubric:: Tools
            :name: p-tb-label

         .. container:: body

            -  `What links
               here </rptools/wiki/Special:WhatLinksHere/Token>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/Token>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=Token&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=Token&oldid=4597>`__
            -  `Page
               information </maptool/index.php?title=Token&action=info>`__

      .. container:: portal
         :name: p-lang

         .. rubric:: In other languages
            :name: p-lang-label

         .. container:: body

            -  `日本語 <http://lmwcs.com/rptools/wiki/Token/ja>`__

.. container::
   :name: footer

   -  This page was last modified on 29 September 2010, at 01:47.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
