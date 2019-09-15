==========================
json.isSubset - MapToolDoc
==========================

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

   .. rubric:: json.isSubset
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

            | ** This article is a stub, you can help the RPTools Wiki
              project by contributing content to expand this article.**
            | ** This article needs:** *Examples of usage.*

         .. rubric:: json.isSubset() Function
            :name: json.issubset-function

         .. container:: template_version

            • **Introduced in version 1.3b53**

         .. container:: template_description

            Returns ``true``\ (``1``) if all of the `JSON
            Object </rptools/wiki/JSON_Object>`__ keys or `JSON
            Array </rptools/wiki/JSON_Array>`__ values are contained
            within the first `JSON Object </rptools/wiki/JSON_Object>`__
            or `JSON Array </rptools/wiki/JSON_Array>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.isSubset(firstArray, array, array, ...)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.isSubset(firstObject, object, object, ...)

         **Parameters**

         -  ``firstArray`` - The `JSON
            Array </rptools/wiki/JSON_Array>`__ that must contain all of
            the values of the subsequent `JSON
            Arrays </rptools/wiki/JSON_Array>`__ for this function to
            return ``true``\ (``1``).
         -  ``array`` - A `JSON Array </rptools/wiki/JSON_Array>`__ with
            values that are tested to be within the ``firstArray``.
         -  ``firstObject`` - The `JSON
            Object </rptools/wiki/JSON_Object>`__ that must contain all
            of the keys of the subsequent `JSON
            Objects </rptools/wiki/JSON_Object>`__ for this function to
            return ``true``\ (``1``).
         -  ``object`` - A `JSON Object </rptools/wiki/JSON_Object>`__
            with keys that are tested to be within the ``firstObject``.

         | 

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `json.contains() </rptools/wiki/json.contains>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=json.isSubset&oldid=6054"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `Stub </rptools/wiki/Category:Stub>`__
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
            in </maptool/index.php?title=Special:UserLogin&returnto=json.isSubset>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/json.isSubset>`__
            -  `Discussion </maptool/index.php?title=Talk:json.isSubset&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/json.isSubset>`__
            -  `View
               source </maptool/index.php?title=json.isSubset&action=edit>`__
            -  `View
               history </maptool/index.php?title=json.isSubset&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/json.isSubset>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/json.isSubset>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=json.isSubset&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=json.isSubset&oldid=6054>`__
            -  `Page
               information </maptool/index.php?title=json.isSubset&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 19 January 2013, at 14:17.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
