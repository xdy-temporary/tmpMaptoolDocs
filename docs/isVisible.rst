======================
isVisible - MapToolDoc
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

   .. rubric:: isVisible
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

         .. rubric:: isVisible() Function
            :name: isvisible-function

         .. container:: template_version

            • **Introduced in version 1.3b69**

         .. container:: template_description

            Check whether a point on the map is visible from a token or
            not. It returns 1 is the token is visible, 0 otherwise. This
            vision is based off of the impersonated token.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     isVisible(x,y)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     isVisible(x,y,id)

         **Parameter**

         -  ``x`` - Then tokens x coordinate. Always in map units, not
            grid .
         -  ``y`` - Then tokens x coordinate. Always in map units, not
            grid .
         -  ``id`` - The check for visibility is performed from token
            ``id``.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro </rptools/wiki/Trusted_Macro>`__. 

         .. rubric:: Example
            :name: example

         .. container:: template_example

            A simple example for testing out ``isVisible()``. Drop the
            default tokens "Hero" and "Troll" on a map. Make sure "Hero"
            has sight (make him PC or set sight manually). You can then
            execute the following code as a campaign macro to check if
            the Hero can see the Troll.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        <!-- lets check if token1 can see token2 -->

                  #. .. code:: de1

                        [h: token1 = "Hero"]

                  #. .. code:: de1

                        [h: id1 = findToken(token1)]

                  #. .. code:: de1

                         

                  #. .. code:: de2

                        [h: token2 = "Troll"]

                  #. .. code:: de1

                        [h: id2 = findToken(token2)]

                  #. .. code:: de1

                         

                  #. .. code:: de1

                        <!-- get the map coordinates of token2 -->

                  #. .. code:: de1

                        <!-- i want to check if the center of the occupied cell can be seen -->

                  #. .. code:: de2

                        <!-- getTokenX/Y retrieves the top-left corner, so -->

                  #. .. code:: de1

                        <!-- in a 50 pixel grid the center is offset by 25 pixel -->

                  #. .. code:: de1

                        [h: x = getTokenX(1, id2)+25]

                  #. .. code:: de1

                        [h: y = getTokenY(1, id2)+25]

                  #. .. code:: de1

                         

                  #. .. code:: de2

                        <!-- and final the check for visiblity -->

                  #. .. code:: de1

                        [r:getName(id1)] <b>[r, if(isVisible(x,y, id1)): "can"; "cannot"]</b> see [r:getName(id2)].

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=isVisible&oldid=7216"

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
            in </maptool/index.php?title=Special:UserLogin&returnto=isVisible>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/isVisible>`__
            -  `Discussion </maptool/index.php?title=Talk:isVisible&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/isVisible>`__
            -  `View
               source </maptool/index.php?title=isVisible&action=edit>`__
            -  `View
               history </maptool/index.php?title=isVisible&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/isVisible>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/isVisible>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=isVisible&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=isVisible&oldid=7216>`__
            -  `Page
               information </maptool/index.php?title=isVisible&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 6 March 2019, at 22:09.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
