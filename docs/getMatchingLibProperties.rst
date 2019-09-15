=====================================
getMatchingLibProperties - MapToolDoc
=====================================

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

   .. rubric:: getMatchingLibProperties
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

            -  `1 getMatchingLibProperties()
               Function <#getMatchingLibProperties.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: getMatchingLibProperties() Function
            :name: getmatchinglibproperties-function

         .. container:: template_version

            • **Introduced in version 1.3b54**

         .. container:: template_description

            Returns a `String List </rptools/wiki/String_List>`__ or
            `JSON Array </rptools/wiki/JSON_Array>`__ with names of the
            `Token Properties </rptools/wiki/Token_Property>`__ on a
            specific `Library Token </rptools/wiki/Library_Token>`__
            that match the given pattern.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getMatchingLibProperties(pattern)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getMatchingLibProperties(pattern, lib)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getMatchingLibProperties(pattern, lib, delim)

         **Parameters**

         -  ``pattern`` - A regular expression(regex) that represents
            the pattern the properties should match.
         -  ``lib`` - The name of the `Library
            Token </rptools/wiki/Library_Token>`__ that is checked for
            properties that match, defaults to the `Library
            Token </rptools/wiki/Library_Token>`__ the macro is running
            on.
         -  ``delim`` - The delimiter used in the `String
            List </rptools/wiki/String_List>`__ that is returned,
            defaults to ``","``. Returns a `JSON
            Array </rptools/wiki/JSON_Array>`__ if ``"json"`` is
            specified.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            Assuming that you have a `Library
            Token </rptools/wiki/Library_Token>`__ that contained a list
            of all the items and their detail in your campaign stored as
            `Token </rptools/wiki/Token>`__ properties names with the
            following format ``Type:Item Name`` (for example
            ``Weapon:Longsword)``, you could use the following code to
            loop through
            all the weapons.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [foreach(item, getMatchingLibProperties("Weapon:.*", "Lib:Items")): {

                  #. .. code-block:: none

                            <!-- Do something really exciting here -->

                  #. .. code-block:: none

                        }]

            Or the following to loop through all the armor

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [foreach(item, getMatchingLibProperties("Armor:.*", "Lib:Items")): {

                  #. .. code-block:: none

                            <!-- Do something really exciting here -->

                  #. .. code-block:: none

                        }]

            Or even all the armor and all the shields.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [foreach(item, getMatchingLibProperties("(Armor|Shield):.*", "Lib:Items")): {

                  #. .. code-block:: none

                            <!-- Do something really exciting here -->

                  #. .. code-block:: none

                        }]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getMatchingProperties() </rptools/wiki/getMatchingProperties>`__
            `getLibPropertyNames() </rptools/wiki/getLibPropertyNames>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getMatchingLibProperties&oldid=6032"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `Macro
               Function </rptools/wiki/Category:Macro_Function>`__
            -  `Property
               Function </rptools/wiki/Category:Property_Function>`__
            -  `Token Library
               Function </rptools/wiki/Category:Token_Library_Function>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__
         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__ > `Property
         Function </rptools/wiki/Category:Property_Function>`__
         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__ > `Token
         Library
         Function </rptools/wiki/Category:Token_Library_Function>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=getMatchingLibProperties>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/getMatchingLibProperties>`__
            -  `Discussion </maptool/index.php?title=Talk:getMatchingLibProperties&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/getMatchingLibProperties>`__
            -  `View
               source </maptool/index.php?title=getMatchingLibProperties&action=edit>`__
            -  `View
               history </maptool/index.php?title=getMatchingLibProperties&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/getMatchingLibProperties>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/getMatchingLibProperties>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=getMatchingLibProperties&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=getMatchingLibProperties&oldid=6032>`__
            -  `Page
               information </maptool/index.php?title=getMatchingLibProperties&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 20 November 2012, at 18:37.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
