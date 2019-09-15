=======================
json.merge - MapToolDoc
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

   .. rubric:: json.merge
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

            -  `1 json.merge() Function <#json.merge.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: json.merge() Function
            :name: json.merge-function

         .. container:: template_version

            • **Introduced in version 1.3b53**

         .. container:: template_description

            Merges multiple `JSON Arrays </rptools/wiki/JSON_Array>`__
            or `JSON Objects </rptools/wiki/JSON_Object>`__.
            For `JSON Arrays </rptools/wiki/JSON_Array>`__ the value
            returned is that of all the `JSON
            Arrays </rptools/wiki/JSON_Array>`__ concatenated together.

            For `JSON Objects </rptools/wiki/JSON_Object>`__ the value
            returned is a `JSON Object </rptools/wiki/JSON_Object>`__
            with all of the keys from all of the `JSON
            Objects </rptools/wiki/JSON_Object>`__ set, if any key is
            specified in more than one `JSON
            Object </rptools/wiki/JSON_Object>`__ then the value for the
            last specified `JSON Object </rptools/wiki/JSON_Object>`__
            is used.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     json.merge(array, array, ...)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     json.merge(object, object, ...)

         **Parameters**

         -  ``array`` - A `JSON Array </rptools/wiki/JSON_Array>`__.
         -  ``object`` - A `JSON Object </rptools/wiki/JSON_Object>`__.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            Merge three `JSON Arrays </rptools/wiki/JSON_Array>`__:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [r: json.merge("[1,2]", "[3,4]", "[1,2]")]

            Returns: ``[1,2,3,4,1,2]``

            Merge two `JSON Objects </rptools/wiki/JSON_Object>`__ with
            no matching keys:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [r: json.merge("{a:1, b:2}", "{c:10, d:7}")]

            Returns: ``{"a":1,"b":2,"c":10,"d":7}``

            Merge three `JSON Objects </rptools/wiki/JSON_Object>`__
            with a matching key, ``a``:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [r: json.merge("{a:1, b:2}", "{c:10, d:7}", "{a:11, z:7}")]

            Returns: ``{"a":11,"b":2,"c":10,"d":7,"z":7}``

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `json.union() </rptools/wiki/json.union>`__,
            `json.intersection() </rptools/wiki/json.intersection>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b54** - Fixed bug which allows ``json.merge()`` to
               work correctly with `JSON
               Objects </rptools/wiki/JSON_Object>`__.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=json.merge&oldid=6193"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `Macro
               Function </rptools/wiki/Category:Macro_Function>`__
            -  `JSON Function </rptools/wiki/Category:JSON_Function>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__
         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__ > `JSON
         Function </rptools/wiki/Category:JSON_Function>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=json.merge>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/json.merge>`__
            -  `Discussion </maptool/index.php?title=Talk:json.merge&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/json.merge>`__
            -  `View
               source </maptool/index.php?title=json.merge&action=edit>`__
            -  `View
               history </maptool/index.php?title=json.merge&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/json.merge>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/json.merge>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=json.merge&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=json.merge&oldid=6193>`__
            -  `Page
               information </maptool/index.php?title=json.merge&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 12 July 2013, at 07:02.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
