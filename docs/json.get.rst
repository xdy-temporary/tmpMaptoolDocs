=====================
json.get - MapToolDoc
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

   .. rubric:: json.get
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

            -  `1 json.get() Function <#json.get.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 Version Changes <#Version_Changes>`__

         .. rubric:: json.get() Function
            :name: json.get-function

         .. container:: template_version

            • **Introduced in version 1.3b49**

         .. container:: template_description

            Returns the value in a `JSON
            Array </rptools/wiki/JSON_Array>`__ at the specified index,
            returns a slice of a `JSON
            Array </rptools/wiki/JSON_Array>`__ from the specified
            indexes, or returns the value from `JSON
            Object </rptools/wiki/JSON_Object>`__ for the specified key.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.get(array, index)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.get(array, start, end)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.get(object, key, key, ...)

         **Parameters**

         -  ``array`` - The `JSON Array </rptools/wiki/JSON_Array>`__ to
            retrieve the element from.
         -  ``index`` - The numerical index of the element you want
            returned.
         -  ``start`` - The starting index of the element you wish the
            slice to begin at.
         -  ``end`` - The ending index of the element you wish the slice
            to end at.
         -  ``object`` - The `JSON Object </rptools/wiki/JSON_Object>`__
            to retrieve the element from.
         -  ``key`` - The name of a field that should be returned. This
            parameter can exist more than once, if it does then a `JSON
            Object </rptools/wiki/JSON_Object>`__ is returned with all
            the specified elements.

         When extracting slices: Negative numbers can be used as the
         offsets from the end of the array, ``-1`` is the last element
         in the array, ``-2`` is the second to last, and so on. If the
         ``end`` index is smaller than the ``start`` index then the
         array slice is returned in reverse. This does not work for
         single indices, so if you want to retrieve a single index, say
         the last one in an array, you do that like this:
         json.get(array, -1,-1). This way you take a *slice* of 1 index.
         To get the last element you thus need to do:
         json.get(json.get(array, -1,-1),0) as you get a *slice* and you
         want an *element*.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                          a) [h: jo = json.fromStrProp("a=1; b=44; cat=meow")] [r: json.get(jo, "b")] <br>

                  #. .. code-block:: none

                          b) [h: jo = json.fromStrProp("a=1; b=44; cat=meow")] [r: json.get(jo, "XX")] <br>

                  #. .. code-block:: none

                          c) [h: jo = json.fromStrProp("a=1; b=44; cat=meow")] [r: json.get(jo, "cat", "a")] <br>

                  #. .. code-block:: none

                          d) [h: jo = json.fromStrProp("a=1; b=44; cat=meow")] [r: json.get(jo, "b", "XX")] <br>

                  #. .. code:: de2

                          e) [h: ja = json.fromList("1,44,meow")] [r: json.get(ja, 1)] <br>

                  #. .. code-block:: none

                          f) [h: ja = json.fromList("1,44,meow")] [r: json.get(ja, 2)] <br>

                  #. .. code-block:: none

                          g) [h: ja = json.fromList("1,44,meow")] [r: json.get(ja, 1, 2)] <br>

                  #. .. code-block:: none

                          h) [h: ja = json.fromList("1,44,meow")] [r: json.get(ja, 0, -1)] <br>

                  #. .. code-block:: none

                          i) [h: ja = json.fromList("1,44,meow")] [r: json.get(ja, 2, 0)] <br> 

                  #. .. code:: de2

                          j) [h: ja = json.fromList("1,44,meow")] [r: json.get(ja, -1, 0)] <br>

                  #. .. code-block:: none

                          ERROR a) [h: ja = json.fromList("1,44,meow")] [r: json.get(ja, -1)] <br>

                  #. .. code-block:: none

                          ERROR b) [h: ja = json.fromList("1,44,meow")] [r: json.get(ja, 3)] <br>

            Returns

            ::

                a) 44 -- a value
                b)    -- empty string "", as XX does not exist
                c) {"cat":"meow","a":1} -- a JSON object
                d) {"b":44,"XX":""} -- a JSON object
                e) 44 -- a value
                f) meow -- a value
                g) [1,44,"meow"] -- an array slice of 0..2  
                h) ["meow",44] -- an array slice from 2..1 
                i) [1,44,"meow"] -- an array slice from 0..end
                j) ["meow",44] -- an array slice from end..1

            ::

                ERROR a) -- java.lang.ArrayIndexOutOfBoundsException, can't use negatives with a single index param (works OK with slices). 

            ERROR a) -- java.lang.ArrayIndexOutOfBoundsException, the
            last valid index is 2

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b51** - Added ability to return `JSON
               Array </rptools/wiki/JSON_Array>`__ slices.
            -  **1.3b51** - Added ability to return `JSON
               Objects </rptools/wiki/JSON_Object>`__ of select fields
               from other `JSON Objects </rptools/wiki/JSON_Object>`__.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=json.get&oldid=6848"

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
            in </maptool/index.php?title=Special:UserLogin&returnto=json.get>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/json.get>`__
            -  `Discussion </maptool/index.php?title=Talk:json.get&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/json.get>`__
            -  `View
               source </maptool/index.php?title=json.get&action=edit>`__
            -  `View
               history </maptool/index.php?title=json.get&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/json.get>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/json.get>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=json.get&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=json.get&oldid=6848>`__
            -  `Page
               information </maptool/index.php?title=json.get&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 21 August 2016, at 21:14.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
