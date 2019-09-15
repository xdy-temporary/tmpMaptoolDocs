================================
frame (roll option) - MapToolDoc
================================

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

   .. rubric:: frame (roll option)
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

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 [frame():] Roll
               Option <#.5Bframe.28.29:.5D_Roll_Option>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: [frame():] Roll Option
            :name: frame-roll-option

         Opens a frame window. Unlike the modeless
         `[dialog():] </rptools/wiki/dialog_(roll_option)>`__, frames
         are dockable panels that are usually intended to remain open.
         Frames can be closed with a button located in the title bar or
         via the `closeDialog() </rptools/wiki/closeDialog>`__ macro
         function.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h: frame(frameName [,"width; height; temporary; title; tabtitle; value"] )]

         The first parameter, shown as **frameName**, should be a
         double-quoted string that specifies the internal name of the
         frame window. The visible title that appears in the title bar
         of the window is set separately, either by using HTML that
         appears inside the frame itself or use of the **title**
         parameter from b50 forward. Any attempts to open another frame
         with the same name instead cause the old contents to be removed
         and new contents displayed. Note this behavior relates to the
         internal name of the frame, not the displayed title of the
         frame as multiple frames can share a title. Once the named
         frame is opened and resized by the user, that size becomes its
         default opening size in the future, unless the temporary option
         is set to "1".

         | 
         | The second parameter is optional, it is a semicolon separated
           `String Property
           List </rptools/wiki/String_Property_List>`__, which could
           include the following options:

         The **temporary** option dictates whether Maptool remembers the
         size of the frame between displays. Setting this value to 1
         causes Maptool to forget the window size. Example "temporary=1"

         The **title** option sets the title of the frame and replaces
         the need to set the title from within the HTML code.

         The **tabtitle** is the title shown when the frame is
         minimized. If not used as a parameter, the tabtitle is the same
         as the frame's title.

         The **width** and **height** options determine the (initial)
         size of the frame. Depending whether **temporary** has been set
         or not the frame will always open with these dimensions.

         The last parameter is **value**. It can be used to store some
         data inside the frame. For example, if a frame display the
         equipment of a character, the value parameter can be set to the
         token id of that character, so that you can know which
         character's equipment is being displayed.

         Prior to 1.5.4, using the **title** parameter when opening up a
         new frame could break the frame. Calls to the macro after
         closing the frame would not show the frame. This was remedied
         by adding a line to the calling macro before running the macro.
         The line below could be used, substituting your own frame name.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [ if( isFrameVisible("YourFrame") ), code: {}; { [resetFrame("YourFrame")] } ]

         This checks if the bugged frame is visible or not. If the frame
         is open it does nothing, but if it is closed it resets the
         frame, which forces it to be shown. The bug is fixed from 1.5.4
         onward.

         .. rubric:: Examples
            :name: examples

         Sample header

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [frame("Frame Test", "width=300; height=200; temporary=1;"): {

         The following code opens up a frame that contains the HTML as
         shown here:

         +-----------------------------------+-----------------------------------+
         | |FrameDemo.png|                   | .. container::                    |
         |                                   | mw-geshi mw-code mw-content-ltr   |
         |                                   |                                   |
         |                                   |    .. container::                 |
         |                                   |    mtmacro source-mtmacro         |
         |                                   |                                   |
         |                                   |       #. .. code:: de1            |
         |                                   |                                   |
         |                                   |             [frame("Frame Test"): |
         |                                   |  {                                |
         |                                   |                                   |
         |                                   |       #. .. code:: de1            |
         |                                   |                                   |
         |                                   |               <html>              |
         |                                   |                                   |
         |                                   |       #. .. code:: de1            |
         |                                   |                                   |
         |                                   |                 <head>            |
         |                                   |                                   |
         |                                   |       #. .. code:: de1            |
         |                                   |                                   |
         |                                   |                   <title>Test of  |
         |                                   | Frame Windows</title>             |
         |                                   |                                   |
         |                                   |       #. .. code:: de2            |
         |                                   |                                   |
         |                                   |                 </head>           |
         |                                   |                                   |
         |                                   |       #. .. code:: de1            |
         |                                   |                                   |
         |                                   |                 <body>            |
         |                                   |                                   |
         |                                   |       #. .. code:: de1            |
         |                                   |                                   |
         |                                   |                 <table border="1" |
         |                                   | >                                 |
         |                                   |                                   |
         |                                   |       #. .. code:: de1            |
         |                                   |                                   |
         |                                   |                 <tr><th>Column 1< |
         |                                   | /th><th>Column 2</th><th>Column 3 |
         |                                   | </th></tr>                        |
         |                                   |                                   |
         |                                   |       #. .. code:: de1            |
         |                                   |                                   |
         |                                   |                 <tr><td>Line 1, C |
         |                                   | ol 1</td><td colspan="2">Line 1,  |
         |                                   | Cols 2 and 3</td></tr>            |
         |                                   |                                   |
         |                                   |       #. .. code:: de2            |
         |                                   |                                   |
         |                                   |                 <tr><td rowspan=" |
         |                                   | 2">Lines 2 and 3, Col 1</td><td>L |
         |                                   | ine 2, Col 2</td><td>Line 2, Col  |
         |                                   | 3</td></tr>                       |
         |                                   |                                   |
         |                                   |       #. .. code:: de1            |
         |                                   |                                   |
         |                                   |                 <tr><td>Line 3, C |
         |                                   | ol 3</td><td>Line 3, Col 3</td></ |
         |                                   | tr>                               |
         |                                   |                                   |
         |                                   |       #. .. code:: de1            |
         |                                   |                                   |
         |                                   |                 </table>          |
         |                                   |                                   |
         |                                   |       #. .. code:: de1            |
         |                                   |                                   |
         |                                   |                 </body>           |
         |                                   |                                   |
         |                                   |       #. .. code:: de1            |
         |                                   |                                   |
         |                                   |               </html>             |
         |                                   |                                   |
         |                                   |       #. .. code:: de2            |
         |                                   |                                   |
         |                                   |             } ]                   |
         +-----------------------------------+-----------------------------------+

         .. rubric:: See Also
            :name: see-also

         | `[dialog():] </rptools/wiki/dialog_(roll_option)>`__
         | `isFrameVisible() </rptools/wiki/isFrameVisible>`__
         | `Introduction to Dialogs and
           Frames </rptools/wiki/Introduction_to_Dialogs_and_Frames>`__
         | `Forms tutorial </rptools/wiki/Forms_tutorial>`__

         .. rubric:: Version Changes
            :name: version-changes

         -  **1.3b50** - Added **title** parameter option.
         -  **1.5.4** - Added **temporary**, **tabtitle** and **value**
            parameter options.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=frame_(roll_option)&oldid=7584"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `Roll Option </rptools/wiki/Category:Roll_Option>`__
            -  `Display Roll
               Option </rptools/wiki/Category:Display_Roll_Option>`__
            -  `Frame
               Function </rptools/wiki/Category:Frame_Function>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__ > `Frame
         Function </rptools/wiki/Category:Frame_Function>`__
         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Roll
         Option </rptools/wiki/Category:Roll_Option>`__
         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Roll
         Option </rptools/wiki/Category:Roll_Option>`__ > `Display Roll
         Option </rptools/wiki/Category:Display_Roll_Option>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=frame+%28roll+option%29>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/frame_(roll_option)>`__
            -  `Discussion </rptools/wiki/Talk:frame_(roll_option)>`__

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

            -  `Read </rptools/wiki/frame_(roll_option)>`__
            -  `View
               source </maptool/index.php?title=frame_(roll_option)&action=edit>`__
            -  `View
               history </maptool/index.php?title=frame_(roll_option)&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/frame_(roll_option)>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/frame_(roll_option)>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=frame_(roll_option)&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=frame_(roll_option)&oldid=7584>`__
            -  `Page
               information </maptool/index.php?title=frame_(roll_option)&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 22 August 2019, at 15:34.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |FrameDemo.png| image:: /maptool/images/8/8c/FrameDemo.png
   :width: 216px
   :height: 216px
   :target: /rptools/wiki/File:FrameDemo.png
.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
