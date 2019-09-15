====================
isOwner - MapToolDoc
====================

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

   .. rubric:: isOwner
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

            -  `1 isOwner() Function <#isOwner.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: isOwner() Function
            :name: isowner-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Returns ``true``\ (``1``) if the given
            `Player </maptool/index.php?title=Player&action=edit&redlink=1>`__
            is an owner of a specific `Token </rptools/wiki/Token>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     isOwner()

               #. .. code-block:: none

                     isOwner(player)

               #. .. code-block:: none

                     isOwner(player, id)

               #. .. code-block:: none

                     isOwner(player, id, mapname)

         **Parameters**

         -  ``player`` - The name of the player to check for ownership,
            defaults to the `Current
            Player </maptool/index.php?title=Current_Player&action=edit&redlink=1>`__.
         -  ``id`` - The token ``id`` of the token which is checked for
            ownership, defaults to the `Current
            Token </rptools/wiki/Current_Token>`__.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro </rptools/wiki/Trusted_Macro>`__. 

         -  ``mapname`` - The name of the map to find the token.
            Defaults to the current map.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            Returns ``You can edit me.`` if the `Current
            Player </maptool/index.php?title=Current_Player&action=edit&redlink=1>`__
            is an owner of the `Current
            Token </rptools/wiki/Current_Token>`__.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r, if(isOwner()): "You can edit me."]

            Returns ``Azhrei can edit me.`` if the given
            `Player </maptool/index.php?title=Player&action=edit&redlink=1>`__
            is an owner of the given `Token </rptools/wiki/Token>`__.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: id = getSelected() ]

                  #. .. code-block:: none

                        [r, if(isOwner("Azhrei", id)): "Azhrei can edit me."]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getOwners() </rptools/wiki/getOwners>`__,
            `isOwnedByAll() </rptools/wiki/isOwnedByAll>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b51** - Added ``id`` parameter option.
            -  **1.5.4** - Added ``mapname`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=isOwner&oldid=7505"

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
            in </maptool/index.php?title=Special:UserLogin&returnto=isOwner>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/isOwner>`__
            -  `Discussion </maptool/index.php?title=Talk:isOwner&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/isOwner>`__
            -  `View
               source </maptool/index.php?title=isOwner&action=edit>`__
            -  `View
               history </maptool/index.php?title=isOwner&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/isOwner>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/isOwner>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=isOwner&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=isOwner&oldid=7505>`__
            -  `Page
               information </maptool/index.php?title=isOwner&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 15 August 2019, at 19:52.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
