========================
json.unique - MapToolDoc
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

   .. rubric:: json.unique
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

            -  `1 json.unique()
               Function <#json.unique.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: json.unique() Function
            :name: json.unique-function

         .. container:: template_version

            • **Introduced in version 1.3b53**

         .. container:: template_description

            Returns a `JSON Array </rptools/wiki/JSON_Array>`__ with
            each value that occurs in the source `JSON
            Array </rptools/wiki/JSON_Array>`__ occurring only once. The
            relative order of the values in the array may not be
            preserved.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.unique(array)

         **Parameters**

         -  ``array`` - The `JSON Array </rptools/wiki/JSON_Array>`__ to
            return only unique values from.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            Lets say you have a `JSON
            Array </rptools/wiki/JSON_Array>`__ that contains the
            following `Token </rptools/wiki/Token>`__ names:
            ``["Hero", "Dragon"]``, and you use ``getPCNames()`` to
            return the names of
            the `PC
            Tokens </maptool/index.php?title=PC_Token&action=edit&redlink=1>`__,
            you could use the following code to generate a `JSON
            Array </rptools/wiki/JSON_Array>`__ that contains the values
            in both `JSON Arrays </rptools/wiki/JSON_Array>`__ with no
            value present more than once.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: names1 = '["Hero", "Dragon"]']

                  #. .. code-block:: none

                        [h: names2 = getNPCNames()]

                  #. .. code-block:: none

                        [h: names = json.merge(names1, names2)]

                  #. .. code-block:: none

                        [r: json.unique(names)]

            If ``getPCNames()`` returns
            ``["Hero", "Sidekick", "Policeman"]`` then the result of the
            above code will be
            ``["Policeman","Sidekick","Hero","Dragon"]``

            While the above example demonstrates the output of
            ``json.unique()`` if you want to merge two or more arrays
            and get the unique values in one step you can use the
            ``json.union()``

            function.

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `json.merge() </rptools/wiki/json.merge>`__
            `json.union() </rptools/wiki/json.union>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=json.unique&oldid=2520"

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
            in </maptool/index.php?title=Special:UserLogin&returnto=json.unique>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/json.unique>`__
            -  `Discussion </maptool/index.php?title=Talk:json.unique&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/json.unique>`__
            -  `View
               source </maptool/index.php?title=json.unique&action=edit>`__
            -  `View
               history </maptool/index.php?title=json.unique&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/json.unique>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/json.unique>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=json.unique&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=json.unique&oldid=2520>`__
            -  `Page
               information </maptool/index.php?title=json.unique&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 31 March 2009, at 23:39.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
