======================
moveToken - MapToolDoc
======================

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

   .. rubric:: moveToken
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

            -  `1 moveToken() Function <#moveToken.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: moveToken() Function
            :name: movetoken-function

         .. container:: template_version

            • **Introduced in version 1.3b51**

         .. container:: template_description

            Move a token to a new location.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     moveToken(x, y)

               #. .. code-block:: none

                     moveToken(x, y, units)

               #. .. code-block:: none

                     moveToken(x, y, units, id)

         **Parameters**

         -  ``x`` - The X coordinate to move the token to.
         -  ``y`` - The Y coordinate to move the token to.
         -  ``units`` - If set to ``false``\ (``0``), the coordinates
            are a location on the grid in **cells**. Defaults to
            ``true``\ (``1``), where the coordinates are in *Distance
            Per Cell* **pixels**.
         -  ``id`` - The id
            `string </rptools/wiki/Macros:Variables:string>`__ of the
            token to move, defaults to the `Current
            Token </rptools/wiki/Current_Token>`__.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro </rptools/wiki/Trusted_Macro>`__. 

          

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            Moves the `Current Token </rptools/wiki/Current_Token>`__
            down ``5`` **units**, and left ``10`` **units**.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: CurrentX = getTokenX()]

                  #. .. code-block:: none

                        [h: CurrentY = getTokenY()]

                  #. .. code-block:: none

                        [h: NewX = CurrentX + 5]

                  #. .. code-block:: none

                        [h: NewY = CurrentY - 10]

                  #. .. code:: de2

                        [h: moveToken(NewX, NewY)]

            Moves the `Current Token </rptools/wiki/Current_Token>`__
            down ``5`` **cells**, and left ``10`` **cells**.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: CurrentX = getTokenX(0)]

                  #. .. code-block:: none

                        [h: CurrentY = getTokenY(0)]

                  #. .. code-block:: none

                        [h: NewX = CurrentX + 5]

                  #. .. code-block:: none

                        [h: NewY = CurrentY - 10]

                  #. .. code:: de2

                        [h: moveToken(NewX, NewY, 0)]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getTokenX() </rptools/wiki/getTokenX>`__,
            `getTokenY() </rptools/wiki/getTokenY>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=moveToken&oldid=7222"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `Macro
               Function </rptools/wiki/Category:Macro_Function>`__
            -  `Token
               Function </rptools/wiki/Category:Token_Function>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__
         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__ > `Token
         Function </rptools/wiki/Category:Token_Function>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=moveToken>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/moveToken>`__
            -  `Discussion </maptool/index.php?title=Talk:moveToken&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/moveToken>`__
            -  `View
               source </maptool/index.php?title=moveToken&action=edit>`__
            -  `View
               history </maptool/index.php?title=moveToken&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/moveToken>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/moveToken>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=moveToken&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=moveToken&oldid=7222>`__
            -  `Page
               information </maptool/index.php?title=moveToken&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 7 March 2019, at 04:38.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
