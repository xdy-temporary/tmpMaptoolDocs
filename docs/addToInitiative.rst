============================
addToInitiative - MapToolDoc
============================

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

   .. rubric:: addToInitiative
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

         .. container:: template_stub

            ** This article is a stub, you can help the RPTools Wiki
            project by contributing content to expand this article.**

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 addToInitiative()
               Function <#addToInitiative.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: addToInitiative() Function
            :name: addtoinitiative-function

         .. container:: template_description

            Adds the `Current Token </rptools/wiki/Current_Token>`__ to
            the `initiative
            panel </maptool/index.php?title=Initiative:initiative_panel&action=edit&redlink=1>`__.
            This function will not assign any initiative value to the
            `tokens </rptools/wiki/Token:token>`__, you can use the
            `setInitiative() </rptools/wiki/setInitiative>`__ function

            to set the initiative value of tokens.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: addToInitiative()]

               #. .. code-block:: none

                     [H: return = addToInitiative( AllowDuplicates, value ) ]

         **Parameters**

         -  ``AllowDuplicates`` - If false (default) then will not add
            the token if it is already in the initiative list. If true
            (1) an additional entry will be added to the initiative list
            (so there could be multiple initiative entries for the same
            token).
         -  ``value`` - The initiative value to set. If included, the
            initiative will be set even if the token is already on the
            initiative list and duplicates are not allowed.
         -  ``return`` - Returns 1 if added to the initiative, 0 if did
            not.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            The following example shows how to add a `Current
            Token </rptools/wiki/Current_Token>`__ to the `initiative
            panel </maptool/index.php?title=Initiative:initiative_panel&action=edit&redlink=1>`__,
            set
            its initiative and then sort the `initiative
            panel </maptool/index.php?title=Initiative:initiative_panel&action=edit&redlink=1>`__.
            Normally you would not sort the `initiative
            panel </maptool/index.php?title=Initiative:initiative_panel&action=edit&redlink=1>`__
            every time you add a `Current
            Token </rptools/wiki/Current_Token>`__ but its done here to
            show you how it is done.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: addToInitiative()]

                  #. .. code-block:: none

                        [h: setInitiative(1d20)]

                  #. .. code-block:: none

                        [h: sortInitiative()]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `setInitiative() </rptools/wiki/setInitiative>`__
            `addAllPCsToInitiative() </rptools/wiki/addAllPCsToInitiative>`__
            `addAllToInitiative() </rptools/wiki/addAllToInitiative>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=addToInitiative&oldid=4014"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `Stub </rptools/wiki/Category:Stub>`__
            -  `Macro
               Function </rptools/wiki/Category:Macro_Function>`__
            -  `Initiative
               Function </rptools/wiki/Category:Initiative_Function>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__
         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__ >
         `Initiative
         Function </rptools/wiki/Category:Initiative_Function>`__
         `Review </rptools/wiki/Category:Review>`__ >
         `Stub </rptools/wiki/Category:Stub>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=addToInitiative>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/addToInitiative>`__
            -  `Discussion </maptool/index.php?title=Talk:addToInitiative&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/addToInitiative>`__
            -  `View
               source </maptool/index.php?title=addToInitiative&action=edit>`__
            -  `View
               history </maptool/index.php?title=addToInitiative&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/addToInitiative>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/addToInitiative>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=addToInitiative&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=addToInitiative&oldid=4014>`__
            -  `Page
               information </maptool/index.php?title=addToInitiative&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 27 October 2009, at 18:45.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
