==================
table - MapToolDoc
==================

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

   .. rubric:: table
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

            -  `1 table() Function <#table.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: table() Function
            :name: table-function

         .. container:: template_version

            • **Introduced in version 1.3b39**

         .. container:: template_description

            Gets the text value from the specified ``table``. If the row
            is not specified then the default ``roll`` for the ``table``
            is used. The row can be either a constant or a ``roll``.
            Note that what this function returns is interpreted as
            either a string or a number. You can put code in a table
            entry but that too will be returned as a string and will not
            be evaluated. To evaluate the result you can use
            `eval() </rptools/wiki/eval>`__ to evaluate e.g. the table
            entry ``1d5`` and `evalMacro() </rptools/wiki/evalMacro>`__
            to evaluate e.g. the table entry ``[r:1d5]``

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     table(name)

               #. .. code:: de1

                     table(name, row)

               #. .. code:: de1

                     tbl(name)

               #. .. code:: de1

                     tbl(name, row)

         **Parameters**

         -  ``name`` - A string containing the name of the
            `table </maptool/index.php?title=Table&action=edit&redlink=1>`__.
         -  ``row`` - The row of the
            `table </maptool/index.php?title=Table&action=edit&redlink=1>`__
            that should be returned.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            **Example 1:** Display a random value from table ``"tbl1"``
            using default roll:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [r: table("tbl1")]

            **Example 2:** Display the first value from table
            ``"tbl1"``:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [r: table("tbl1", 1)]

            **Example 3:** Display one of the first four values from
            ``"tbl1"``, chosen randomly:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [r: table("tbl1", "1d4")]

            **Example 4:** Display a table row that corresponds to a
            token property's value (the value must be numeric):

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [r: table("tbl1", Intelligence)]

                  #. .. code:: de1

                        [r: table("tbl1", getProperty("PCLevel"))]

            **Example 5:** Evaluate the outcome of a table entry. The
            table entry **must** thus be something that can be
            evaluated, like ``1d10`` or ``roll(1,6)`` or ``3+5``:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [r: eval(table("tbl1"))]

            **Example 5:** Evaluate the outcome of a table entry that
            contains code. The table entry **can** thus contain code,
            but its not required. 'code' in this case is anything
            between [brackets]. An example table entry could be
            *[h:roll=1d20]You [r:if(roll<10, 'hit', 'miss')] your
            target.* :

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [r: evalMacro(table("tbl1"))]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `tableImage() </rptools/wiki/tableImage>`__ There is a tool
            available to import tables from excel. You can find more
            about this
            `here <http://forums.rptools.net/viewtopic.php?f=3&t=11568#p124557>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=table&oldid=6720"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `Macro
               Function </rptools/wiki/Category:Macro_Function>`__
            -  `Table
               Function </rptools/wiki/Category:Table_Function>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__
         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__ > `Table
         Function </rptools/wiki/Category:Table_Function>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=table>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/table>`__
            -  `Discussion </maptool/index.php?title=Talk:table&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/table>`__
            -  `View
               source </maptool/index.php?title=table&action=edit>`__
            -  `View
               history </maptool/index.php?title=table&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/table>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/table>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=table&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=table&oldid=6720>`__
            -  `Page
               information </maptool/index.php?title=table&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 3 May 2016, at 15:08.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
