===========================================
Using JSON Datatypes in Macros - MapToolDoc
===========================================

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

   .. rubric:: Using JSON Datatypes in Macros
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

         If you don't know JavaScript or JSON already I highly suggest
         you read `Introduction to JSON
         Datatypes </rptools/wiki/Introduction_to_JSON_Datatypes>`__
         first even though it is JavaScript based.

         So how do you create `JSON
         Objects </rptools/wiki/JSON_Object>`__ and `JSON
         Arrays </rptools/wiki/JSON_Array>`__ in MapTool macro script?
         Well the easy way if you already know everything you want is to
         create it as a string. Lets define a data structure that will
         hold the details for a weapon.

         The weapon will be a gun which has the following details:

         -  Number of shots before reload
         -  Damage done
         -  Attack penalty per shot (so more than one shot around has an
            attack penalty).

         So if we were to define this in JavaScript we could just do it
         as

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: javascript source-javascript

               #. .. code:: de1

                     weapon = {

               #. .. code:: de1

                         "name": "Handgun",

               #. .. code:: de1

                         "shots": 6,

               #. .. code:: de1

                         "damage": "1d10"

               #. .. code:: de2

                     }

         If you already know what your JSON object looks like defining
         it in MapTool is not too different.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [r: weapon = '{

               #. .. code:: de1

                         "name": "Handgun",

               #. .. code:: de1

                         "shots": 6,

               #. .. code:: de1

                         "damage": "1d10"

               #. .. code:: de2

                     }']

         If you copy and paste this into MapTool you will notice that
         the output is returned on one line

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [r: weapon = '{ "name": "Handgun", "shots": 6, "damage": "1d10" }']

         This is because the chat window displays html and new line
         characters are not displayed. If you wanted to see the carriage
         returns as you typed them then you could do

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     <pre>

               #. .. code:: de1

                     [r: weapon = '{

               #. .. code:: de1

                         "name": "Handgun",

               #. .. code:: de1

                         "shots": 6,

               #. .. code:: de2

                         "damage": "1d10"

               #. .. code:: de1

                     }']

               #. .. code:: de1

                     </pre>

         Which says the output is already preformatted so new line
         characters will be displayed.

         The above is well and good if you know what you want to store
         ahead of time, but how do you create a JSON object based on
         user input or results of a macro. For this you use
         `json.set() </rptools/wiki/json.set>`__.

         So to create the above weapon you could use

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [r: weapon = json.set("{}", "name", "Handgun", "shots", 6, "damage", "1d10" )]

         Where ``"{}"`` is an empty JSON object, for convenience ``""``
         can be used as the first argument to
         `json.set() </rptools/wiki/json.set>`__ to represent an empty
         object.

         `json.set() </rptools/wiki/json.set>`__ takes an object as well
         a list of key and value pairs and returns a new object with the
         specified keys set . **It is important to rememeber this last
         bit, all of the json functions do not modify the object,
         instead they create a new object with the changes.** For
         example

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h: weapon = json.set("{}", "name", "Handgun", "shots", 6, "damage", "1d10" )]

               #. .. code:: de1

                     [h: weapon2 = json.set(weapon, "name", "Bigger Handgun")]

               #. .. code:: de1

                     [r: weapon] <br>

               #. .. code:: de1

                     [r: weapon2]

         Displays

         ::

            {"name":"Handgun","shots":6,"damage":"1d10"}
            {"name":"Bigger Handgun","shots":6,"damage":"1d10"}

         The original value in weapon has not been modified.

         If you placed ``<pre> </pre>`` around the output you will
         notice that json.set() creates the object on one line, not
         formatted nicely across multiple lines as it was when we
         created it manually. If you want to "format" this nicely you
         can use the `json.indent() </rptools/wiki/json.indent>`__
         command.

         For example:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     <pre>[r: json.indent('{"name":"Handgun","shots":6,"damage":"1d10"}', 4)]</pre>

         Produces:

         ::

            {
                "name": "Handgun",
                "shots": 6,
                "damage": "1d10"
            }

         Using JSON arrays is similar Lets to our weapon above, in this
         mythical system that the gun belongs to you are able to fire
         all of the shots in one round but each after the first has a
         two hit penalty. We can represent this as an array with 6
         elements (we will include the first shot for simplicities sake
         even if it would always be 0).

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [r: modifiers = '[0, 1, 3, 5, 8, 12]']

         The `json.append() </rptools/wiki/json.append>`__ function
         allows you to append items to the end of an array, if the array
         is empty then it will create a new one.

         If the input is an ``"[]"`` it is an empty array, for
         convenience ``""`` also represents an empty array. json.set()
         can be used on arrays but only to set a value for an index, the
         array must already have that index.

         For example if I wanted to change the 3rd index in the array
         above to 4 I could do

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h: modifiers = json.set(modifiers, 2, 4)

         The value for index is ``2`` because indexes in the array start
         at ``0``.

         So given what we learned earlier you could add the modifiers to
         our weapon object in the following way

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [r: modifiers = '[0, 1, 3, 5, 8, 12]']

               #. .. code:: de1

                     [r: weapon = json.set(weapon, "modifiers", modifiers)]

         Or you could do it as

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h: weapon = json.set("{}", "name", "Handgun", "shots", 6, "damage", "1d10",

               #. .. code:: de1

                         "modifiers", "[0, 1, 3, 5, 8, 12]" )]

               #. .. code:: de1

                     <pre>[r: json.indent(weapon,4)]</pre>

         Which will display

         ::

            {
                "name": "Handgun",
                "shots": 6,
                "damage": "1d10",
                "modifiers":     [
                    0,
                    1,
                    3,
                    5,
                    8,
                    12
                ]
            }

         | 
         | Of course if you know all the details up front you can create
           the whole objects as before such as.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [r: weapon = '{

               #. .. code:: de1

                         "name" : "Handgun",

               #. .. code:: de1

                         "shots" : 6,

               #. .. code:: de1

                         "damage" : 1d10,

               #. .. code:: de2

                         "modifiers" : "[0, 1, 3, 5, 8, 12]"

               #. .. code:: de1

                     }']

         | 
         | The next question is now that we have all the information in
           a JSON object or array how do we get it out when we need it?

         To get things out of objects or arrays we use
         `json.get() </rptools/wiki/json.get>`__

         So

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h: weapon = json.set("{}", "name", "Handgun", "shots", 6, "damage", "1d10",

               #. .. code:: de1

                         "modifiers", "[0, 1, 3, 5, 8, 12]" )]

               #. .. code:: de1

                     Weapon Name: [r: json.get(weapon, "name")]<br>

               #. .. code:: de1

                     Damage: [r: json.get(weapon, "damage")] <br>

               #. .. code:: de2

                     Shots: [r: json.get(weapon, "shots")] <br>

               #. .. code:: de1

                     [h: modifiers = json.get(weapon, "modifiers")]

               #. .. code:: de1

                     Modifiers [r,c(json.get(weapon, "shots")): json.get(modifiers, roll.count)]

         | 
         | Which displays

         ::

            Weapon Name: Handgun 
            Damage: 1d10 
            Shots: 6 
            Modifiers 0, 1, 3, 5, 8, 12

         You could also use
         `json.length() </rptools/wiki/json.length>`__ to change the
         line that displays the modifiers to

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     Modifiers [r,c(json.length(modfiers)): json.get(modifiers, roll.count)]

         But there is an easier way to loop through every value in the
         array and that is using
         `foreach </rptools/wiki/foreach_(roll_option)>`__

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     Modifiers [r,foreach(val,modifiers): val]

         json.length() and foreach can be used on JSON objects as well
         as arrays. In this case json.length() returns the number of
         key/value pairs, and foreach will loop through the keys in the
         object.

         So using the above objects

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [r: json.length(weapon)]

         Displays ``4``.

         and

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [r,foreach(val,weapon): val]

         Displays

         ::

            name, shots, damage, modifiers

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Using_JSON_Datatypes_in_Macros&oldid=5099"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Category </rptools/wiki/Special:Categories>`__:

            -  `Tutorial </rptools/wiki/Category:Tutorial>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Tutorial </rptools/wiki/Category:Tutorial>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=Using+JSON+Datatypes+in+Macros>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/Using_JSON_Datatypes_in_Macros>`__
            -  `Discussion </maptool/index.php?title=Talk:Using_JSON_Datatypes_in_Macros&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/Using_JSON_Datatypes_in_Macros>`__
            -  `View
               source </maptool/index.php?title=Using_JSON_Datatypes_in_Macros&action=edit>`__
            -  `View
               history </maptool/index.php?title=Using_JSON_Datatypes_in_Macros&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/Using_JSON_Datatypes_in_Macros>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/Using_JSON_Datatypes_in_Macros>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=Using_JSON_Datatypes_in_Macros&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=Using_JSON_Datatypes_in_Macros&oldid=5099>`__
            -  `Page
               information </maptool/index.php?title=Using_JSON_Datatypes_in_Macros&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 3 January 2011, at 20:32.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
