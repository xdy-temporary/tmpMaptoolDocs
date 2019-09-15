========================
setTokenVBL - MapToolDoc
========================

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

   .. rubric:: setTokenVBL
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

         .. rubric:: setTokenVBL() Function
            :name: settokenvbl-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.4.1.6**

         .. container:: template_description

            Sets the VBL of a token to that given in the JSON object
            parameter.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setTokenVBL(vbl, id)

         This function is used to attach the TOKEN VBL passed in as a
         JSON object to a token. The JSON object may be be created by
         calling `getTokenVBL() </rptools/wiki/getTokenVBL>`__ on a
         different token and may also be used with
         `drawVBL() </rptools/wiki/drawVBL>`__ or
         `eraseVBL() </rptools/wiki/eraseVBL>`__.

         Token VBL moves with the token, can be set under the VBL tab on
         the token edit menu and is colored YELLOW. Normal VBL is
         static, can be created with the VBL drawing tools or with the
         use of VBL functions and is colored BLUE.

         **Parameters**

         -  ``vbl`` - A JSON object containing the ``vbl`` to be added
            to the token. Use
            `getTokenVBL() </rptools/wiki/getTokenVBL>`__ to get VBL
            from another token.
         -  ``id`` - OPTIONAL: The token ``id`` of the token for which
            you want to set this setting, defaults to the `Current
            Token </rptools/wiki/Current_Token>`__.

         *Example: Transfer VBL from one Token to another*

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code:: de1

                  [h: vbl = getTokenVBL("Door, Steel")]
                  [h: setTokenVBL(vbl, "Door, Wood")]

         *Example: Erase VBL from Token*

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code:: de1

                  [r: finalVblData = "{'shape':'none'}"]
                  [r: setTokenVBL(finalVblData)]

         | 

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `Introduction to Vision
            Blocking </rptools/wiki/Introduction_to_Vision_Blocking>`__
            , `getTokenVBL() </rptools/wiki/getTokenVBL>`__,
            `drawVBL() </rptools/wiki/drawVBL>`__,
            `eraseVBL() </rptools/wiki/eraseVBL>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setTokenVBL&oldid=7009"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `Macro
               Function </rptools/wiki/Category:Macro_Function>`__
            -  `Miscellaneous
               Function </rptools/wiki/Category:Miscellaneous_Function>`__
            -  `VBL Function </rptools/wiki/Category:VBL_Function>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__
         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__ >
         `Miscellaneous
         Function </rptools/wiki/Category:Miscellaneous_Function>`__
         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__ > `VBL
         Function </rptools/wiki/Category:VBL_Function>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=setTokenVBL>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/setTokenVBL>`__
            -  `Discussion </maptool/index.php?title=Talk:setTokenVBL&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/setTokenVBL>`__
            -  `View
               source </maptool/index.php?title=setTokenVBL&action=edit>`__
            -  `View
               history </maptool/index.php?title=setTokenVBL&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/setTokenVBL>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/setTokenVBL>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=setTokenVBL&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=setTokenVBL&oldid=7009>`__
            -  `Page
               information </maptool/index.php?title=setTokenVBL&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 3 February 2019, at 16:29.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
