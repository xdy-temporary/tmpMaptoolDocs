=======================
macro.args - MapToolDoc
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

   .. rubric:: macro.args
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

         The variable *macro.args* holds the value of the argument
         passed to a trusted macro via the
         `MACRO() </rptools/wiki/macro_(roll_option)>`__ roll option.
         *macro.args* exists only within the macro that is called, and
         may be manipulated like any variable in a macro.

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 Examples <#Examples>`__

               -  `1.1 1: Single parameter <#1:_Single_parameter>`__

                  -  `1.1.1 Calling Macro <#Calling_Macro>`__
                  -  `1.1.2 Called Macro <#Called_Macro>`__

               -  `1.2 2A: Multiple parameters using String Property
                  List <#2A:_Multiple_parameters_using_String_Property_List>`__

                  -  `1.2.1 Calling Macro <#Calling_Macro_2>`__
                  -  `1.2.2 Called Macro <#Called_Macro_2>`__

               -  `1.3 2B: Multiple parameters using JSON
                  Array <#2B:_Multiple_parameters_using_JSON_Array>`__

                  -  `1.3.1 Calling Macro using JSON
                     Array <#Calling_Macro_using_JSON_Array>`__
                  -  `1.3.2 Called Macro using JSON
                     Array <#Called_Macro_using_JSON_Array>`__

               -  `1.4 2C: Multiple parameters using JSON
                  Object <#2C:_Multiple_parameters_using_JSON_Object>`__

                  -  `1.4.1 Calling Macro using JSON
                     Object <#Calling_Macro_using_JSON_Object>`__
                  -  `1.4.2 Called Macro using JSON
                     Object <#Called_Macro_using_JSON_Object>`__

            -  `2 See Also <#See_Also>`__

         .. rubric:: Examples
            :name: examples

         .. rubric:: 1: Single parameter
            :name: single-parameter

         When a macro on a `library
         token </rptools/wiki/Token:library_token>`__ is called by
         another macro, the calling macro may pass one argument to the
         called macro:

         .. rubric:: Calling Macro
            :name: calling-macro

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     <!-- Call the getDamage macro -->

               #. .. code:: de1

                     [h:damageDice="2d6"]

               #. .. code:: de1

                     [MACRO("getDamage@Lib:test"): damageDice]

         .. rubric:: Called Macro
            :name: called-macro

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     <!-- getDamage Macro -->

               #. .. code:: de1

                     [h:damageRoll = eval(macro.args) + 9]

               #. .. code:: de1

                     You hit your target for [r:damageRoll] damage!

         In the example above, *damageDice* is the argument being passed
         to the macro **getDamage**, which resides on the **Lib:test**
         `library token </rptools/wiki/Token:library_token>`__. Within
         the **getDamage** macro, the variable ``macro.args`` is
         automatically generated and assigned the value of *damageDice*.

         It's important to note that only a single parameter can be
         passed to a macro and that parameter appears in the
         ``macro.args`` variable. If more than a single parameter needs
         to be sent to a macro, you may use string property lists, a
         JSON array or object, or a ``user-defined function``. The first
         two techniques are demonstrated below.

         .. rubric:: 2A: Multiple parameters using String Property List
            :name: a-multiple-parameters-using-string-property-list

         A string property list essentially bundles multiple values into
         a single string which would then be split back apart inside the
         macro body.

         .. rubric:: Calling Macro
            :name: calling-macro-1

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     <!-- Call the doDamage macro -->

               #. .. code:: de1

                     [h:damageDice="2d6"]

               #. .. code:: de1

                     [h:theToken = "Bobo Fett"]

               #. .. code:: de1

                     [MACRO("getDamage@Lib:test"): "Damage="+damageDice+"; Token="+theToken]

         .. rubric:: Called Macro
            :name: called-macro-1

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     <!-- doDamage Macro -->

               #. .. code:: de1

                     [h:dmg   = getStrProp(macro.args, "Damage")]

               #. .. code:: de1

                     [h:tokid = getStrProp(macro.args, "Token")]

               #. .. code:: de1

                     You hit [r: tokid] for [r:dmg] damage!

         .. rubric:: 2B: Multiple parameters using JSON Array
            :name: b-multiple-parameters-using-json-array

         The second way to pass multiple parameters is to use a `JSON
         Array </rptools/wiki/JSON_Array>`__ or `JSON
         Object </rptools/wiki/JSON_Object>`__.

         Using a JSON data type passes multiple values as a single unit.
         When using JSON data types, there will be a single parameter
         coming into the macro but because it's either an array or an
         object you can retrieve individual fields quite easily.

         As the `json.append() </rptools/wiki/json.append>`__ is being
         passed ``"[]"`` as the first parameter in this next code block,
         it's creating an empty `JSON
         Array </rptools/wiki/JSON_Array>`__ and then appending two new
         values to it.

         .. rubric:: Calling Macro using JSON Array
            :name: calling-macro-using-json-array

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     <!-- Call the doDamage macro -->

               #. .. code:: de1

                     [h:damageDice="2d6"]

               #. .. code:: de1

                     [h:theToken = "Bobo Fett"]

               #. .. code:: de1

                     [h:jsonData = json.append("[]", damageDice, theToken)]

               #. .. code:: de2

                     [MACRO("getDamage@Lib:test"): jsonData]

         .. rubric:: Called Macro using JSON Array
            :name: called-macro-using-json-array

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     <!-- doDamage Macro -->

               #. .. code:: de1

                     [h:dmg   = json.get(macro.args, 0)]

               #. .. code:: de1

                     [h:tokid = json.get(macro.args, 1)]

               #. .. code:: de1

                     You hit [r: tokid] for [r:dmg] damage!

         .. rubric:: 2C: Multiple parameters using JSON Object
            :name: c-multiple-parameters-using-json-object

         Notice that in this next example, the
         `json.set() </rptools/wiki/json.set>`__ is being passed
         ``"{}"`` as the first parameter. This indicates to the function
         that we want a `JSON Object </rptools/wiki/JSON_Object>`__.

         .. rubric:: Calling Macro using JSON Object
            :name: calling-macro-using-json-object

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     <!-- Call the doDamage macro -->

               #. .. code:: de1

                     [h:damageDice="2d6"]

               #. .. code:: de1

                     [h:theToken = "Bobo Fett"]

               #. .. code:: de1

                     [h:jsonData = json.set("{}", "Damage", damageDice, "Token", theToken)]

               #. .. code:: de2

                     [MACRO("getDamage@Lib:test"): jsonData]

         .. rubric:: Called Macro using JSON Object
            :name: called-macro-using-json-object

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     <!-- doDamage Macro -->

               #. .. code:: de1

                     [h:dmg   = json.get(macro.args, "Damage")]

               #. .. code:: de1

                     [h:tokid = json.get(macro.args, "Token")]

               #. .. code:: de1

                     You hit [r: tokid] for [r:dmg] damage!

         .. rubric:: See Also
            :name: see-also

         `macro.return </rptools/wiki/macro.return>`__,
         `[macro():] </rptools/wiki/macro_(roll_option)>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=macro.args&oldid=4040"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Category </rptools/wiki/Special:Categories>`__:

            -  `Special
               Variable </rptools/wiki/Category:Special_Variable>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Special
         Variable </rptools/wiki/Category:Special_Variable>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=macro.args>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/macro.args>`__
            -  `Discussion </maptool/index.php?title=Talk:macro.args&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/macro.args>`__
            -  `View
               source </maptool/index.php?title=macro.args&action=edit>`__
            -  `View
               history </maptool/index.php?title=macro.args&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/macro.args>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/macro.args>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=macro.args&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=macro.args&oldid=4040>`__
            -  `Page
               information </maptool/index.php?title=macro.args&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 10 November 2009, at 04:48.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
