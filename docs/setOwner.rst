=====================
setOwner - MapToolDoc
=====================

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

   .. rubric:: setOwner
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

            -  `1 setOwner() Function <#setOwner.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: setOwner() Function
            :name: setowner-function

         .. container:: template_version

            • **Introduced in version 1.3b48?**

         .. container:: template_description

            Changes the owners of a token (default is the `Current
            Token </rptools/wiki/Current_Token>`__) when given a
            `String </rptools/wiki/String>`__ owner name or `JSON
            Array </rptools/wiki/JSON_Array>`__ of owner names. All
            other owners are removed.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setOwner(ownerName)

               #. .. code-block:: none

                     setOwner(ownerName, id)

               #. .. code-block:: none

                     setOwner(ownerName, id, mapname)

               #. .. code-block:: none

                     setOwner(ownerNames)

               #. .. code:: de2

                     setOwner(ownerNames, id)

               #. .. code-block:: none

                     setOwner(ownerNames, id, mapname)

         **Parameters**

         -  ``ownerName`` - The player name to set the ownership on the
            token. Ownership is not constrained to the client names
            currently connected, but only currently connected clients
            appear in the Token Editor Dialog. This parameter is a
            `String </rptools/wiki/String>`__. An empty string here is
            treated as an empty JSON array (see next parameter).
         -  ``ownerNames`` - The player names to set the ownership on
            the token. Ownership is not constrained to the client names
            currently connected, but only currently connected clients
            appear in the Token Editor Dialog. This parameter is a `JSON
            Array </rptools/wiki/JSON_Array>`__.
         -  ``id`` - The token ``id`` of the token which has its owners
            changed, defaults to the `Current
            Token </rptools/wiki/Current_Token>`__.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro </rptools/wiki/Trusted_Macro>`__. 

         -  ``mapname`` - The name of the map to find the token.
            Defaults to the current map.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            To change the
            `owners </maptool/index.php?title=Owners&action=edit&redlink=1>`__
            of the `Current Token </rptools/wiki/Current_Token>`__ to a
            single user use:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: setOwner("Frank")]

            To change the
            `owners </maptool/index.php?title=Owners&action=edit&redlink=1>`__
            of the `Current Token </rptools/wiki/Current_Token>`__ to a
            list of three players use:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: setOwner("['Peter', 'Paul', 'Mary']")]

            or:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: list = json.append("[]", "Peter", "Paul", "Mary")]

                  #. .. code-block:: none

                        [h: setOwner(list)]

            To make all current players
            `owners </maptool/index.php?title=Owners&action=edit&redlink=1>`__
            of the `Current Token </rptools/wiki/Current_Token>`__ use:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: setOwner(getAllPlayerNames("json"))]

            To remove all
            `owners </maptool/index.php?title=Owners&action=edit&redlink=1>`__
            of the `Current Token </rptools/wiki/Current_Token>`__ use:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: setOwner("")]

            or:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: setOwner("[]")]

            To display the current
            `owners </maptool/index.php?title=Owners&action=edit&redlink=1>`__
            of the `Current Token </rptools/wiki/Current_Token>`__ as
            checkboxes, then accept the user's changes to apply back
            onto the token, use the following. Note that this example
            does not provide for adding owners to the list, only
            removing them. (Adding owners would require the use of
            `getAllPlayerNames() </rptools/wiki/getAllPlayerNames>`__
            and would make this example even more complex.)

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: names = getOwners("json")]

                  #. .. code-block:: none

                        [h: input = "tab0 | OwnerList || TAB"]

                  #. .. code-block:: none

                        [h: count = 0]

                  #. .. code-block:: none

                        [h, foreach(name, names), code: {

                  #. .. code:: de2

                            [input = input + strformat(" ## ckb_%{count}|1|%{name}|CHECK")]

                  #. .. code-block:: none

                            [count = count+1]

                  #. .. code-block:: none

                        } ]

                  #. .. code-block:: none

                        [h: cancel = input(input)]

                  #. .. code-block:: none

                        [h: abort(cancel)]

                  #. .. code:: de2

                        [h: newOwners = "[]"]

                  #. .. code-block:: none

                        [h, for(x,0,count):

                  #. .. code-block:: none

                            newOwners = if(eval("ckb_"+x)==0, newOwners, json.append(newOwners, json.get(names, x))) ]

                  #. .. code-block:: none

                        [h: setOwner(newOwners)]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `isOwnedByAll() </rptools/wiki/isOwnedByAll>`__,
            `setOwnerOnlyVisible() </rptools/wiki/setOwnerOnlyVisible>`__,

            `isOwner() </rptools/wiki/isOwner>`__.

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b51** - Added ``id`` parameter option.
            -  **1.5.4** - Added ``mapname`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setOwner&oldid=7523"

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
            in </maptool/index.php?title=Special:UserLogin&returnto=setOwner>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/setOwner>`__
            -  `Discussion </rptools/wiki/Talk:setOwner>`__

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

            -  `Read </rptools/wiki/setOwner>`__
            -  `View
               source </maptool/index.php?title=setOwner&action=edit>`__
            -  `View
               history </maptool/index.php?title=setOwner&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/setOwner>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/setOwner>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=setOwner&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=setOwner&oldid=7523>`__
            -  `Page
               information </maptool/index.php?title=setOwner&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 15 August 2019, at 20:50.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
