=======================
getStrProp - MapToolDoc
=======================

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

   .. rubric:: getStrProp
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

            -  `1 getStrProp() Function <#getStrProp.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 Version Changes <#Version_Changes>`__

         .. rubric:: getStrProp() Function
            :name: getstrprop-function

         .. container:: template_version

            • **Introduced in version 1.3b42**

         .. container:: template_description

            Returns the value associated with a key from the specified
            `string property
            list </rptools/wiki/Macros:string_property_list>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getStrProp(propList, key)

               #. .. code-block:: none

                     getStrProp(propList, key, default)

               #. .. code-block:: none

                     getStrProp(propList, key, default, delim)

         **Parameters**

         -  ``proplist`` - String property list to extract data from.
         -  ``key`` - Key within string to extract. This cannot include
            a space.
         -  ``default`` - Value returned if the key is not found.
         -  ``delim`` - Delimiter between fields (default is ";").

         .. rubric:: Example
            :name: example

         .. container:: template_example

            To get the name from a weapon `string property
            list </rptools/wiki/Macros:string_property_list>`__

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: weapon = "name=longsword; damage=1d8; maxdamage=8"]

                  #. .. code-block:: none

                        Name of Weapon: [r: getStrProp(weapon, "name")]

            Returns ``Name of Weapon: longsword``.

            To get the minimum damage from a weapon `string property
            list </rptools/wiki/Macros:string_property_list>`__ with a
            default value should the key not exist

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: weapon = "name=longsword; damage=1d8; maxdamage=8"]

                  #. .. code-block:: none

                        Minimum damage of Weapon: [r: getStrProp(weapon, "mindamage", 1)]

            Returns ``Minimum damage of Weapon: 1``.

            To get the damage from a weapon `string property
            list </rptools/wiki/Macros:string_property_list>`__ where
            the field delimiter is a colon. The default is **1d3** (note
            that a default value must be provided in order to specify
            the delimiter).

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: weapon = "name=longsword: damage=1d8: maxdamage=8"]

                  #. .. code-block:: none

                        Damage of Weapon: [r: getStrProp(weapon, "damage", "1d3", ":")]

            Returns ``Damage of Weapon: 1d8``.

         | 

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b43** - Added the optional ``error`` parameter.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getStrProp&oldid=6067"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `Macro
               Function </rptools/wiki/Category:Macro_Function>`__
            -  `String Property List
               Function </rptools/wiki/Category:String_Property_List_Function>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__
         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__ > `String
         Property List
         Function </rptools/wiki/Category:String_Property_List_Function>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=getStrProp>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/getStrProp>`__
            -  `Discussion </maptool/index.php?title=Talk:getStrProp&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/getStrProp>`__
            -  `View
               source </maptool/index.php?title=getStrProp&action=edit>`__
            -  `View
               history </maptool/index.php?title=getStrProp&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/getStrProp>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/getStrProp>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=getStrProp&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=getStrProp&oldid=6067>`__
            -  `Page
               information </maptool/index.php?title=getStrProp&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 27 February 2013, at 08:13.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
