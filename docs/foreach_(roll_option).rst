==================================
foreach (roll option) - MapToolDoc
==================================

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

   .. rubric:: foreach (roll option)
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

            -  `1 FOREACH Option <#FOREACH_Option>`__

               -  `1.1 Usage <#Usage>`__

            -  `2 Examples <#Examples>`__

               -  `2.1 String List Example <#String_List_Example>`__
               -  `2.2 JSON Array Example <#JSON_Array_Example>`__
               -  `2.3 JSON Object Example <#JSON_Object_Example>`__
               -  `2.4 Using with [code():] and
                  output_separator <#Using_with_.5Bcode.28.29:.5D_and_output_separator>`__
               -  `2.5 String Property List
                  Example <#String_Property_List_Example>`__

            -  `3 See Also <#See_Also>`__

         .. rubric:: FOREACH Option
            :name: foreach-option

         **Introduced**: Version 1.3.b46

         Iterates over the contents of a string list in the format
         ``"item1, item2, item3"``. Can also be used easily with `JSON
         arrays and JSON
         objects <Introduction_to_JSON_Datatypes>`__.
         `String Property Lists <String_Property_List>`__
         can be processed with a couple of extra functions.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [FOREACH(var, list): body]

               #. .. code-block:: none

                     [FOREACH(var, list, output_separator): body]

               #. .. code-block:: none

                     [FOREACH(var, list, output_separator, list_separator): body]

         | ``output_separator`` default value is ``","``
         | ``list_separator`` default value is ``","``. Some examples of
           other useful separators: *nothing* ``""``, *space* ``" "``
           and *break* ``"<br>"``.

         .. rubric:: Examples
            :name: examples

         .. rubric:: String List Example
            :name: string-list-example

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: enemyList="Orcs, Goblins, Ogres, Trolls"]

               #. .. code-block:: none

                     [FOREACH(enemy, enemyList, "<br>"): "You really hate " + enemy]

         .. rubric:: JSON Array Example
            :name: json-array-example

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: enemyList = json.append("","Orcs, Goblins, Ogres, Trolls")]

               #. .. code-block:: none

                     [FOREACH (enemy, enemyList, "<br>"): "You really hate " + enemy]

         .. rubric:: JSON Object Example
            :name: json-object-example

         (Note that using foreach with a JSON object will result in only
         the keys being returned as vars).

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: enemyList = json.set("","Orcs", "Bob, Dave", "Goblins", "Graham", "Ogres", "Philip, Emanual", "Trolls", "Ig, Og, Ug")]

               #. .. code-block:: none

                     [FOREACH (enemy, enemyList, "<br>"): "You really hate " + enemy]

         All the above will output:

         ::

            You really hate Orcs
            You really hate Goblins
            You really hate Ogres
            You really hate Trolls

         .. rubric:: Using with [code():] and output_separator
            :name: using-with-code-and-output_separator

         To use roll options with your ``FOREACH`` loop, you will need
         to use `[code():] <code_(roll_option)>`__ roll
         option. In this example I have separated the results with the
         string ``" then "``.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  [h: enemyList="Orcs; Goblins; Ogres; Trolls"]
                  [FOREACH(enemy, enemyList, " then ", ";"), CODE:
                      {
                      [r: enemy]
                      }
                  ]

         output:

         ::

            Orcs then Goblins then Ogres then Trolls

         .. rubric:: String Property List Example
            :name: string-property-list-example

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: enemyStrProp = json.toStrProp(json.set("","Orcs", "Bob, Dave", "Goblins", "Graham", "Ogres", "Philip, Emanual", "Trolls", "Ig, Og, Ug"))]

               #. .. code-block:: none

                     [FOREACH(enemy, enemyStrProp, "<br>", ";"), code:

               #. .. code-block:: none

                         {

               #. .. code-block:: none

                         [h: enemyList = stringToList(enemy, "=")]

               #. .. code:: de2

                       [h: name = listGet(enemyList, 0)]

               #. .. code-block:: none

                       [h: value = listDelete(enemyList, 0)]

               #. .. code-block:: none

                       [r: "You really hate " + name + " who are " + value]

               #. .. code-block:: none

                       }

               #. .. code-block:: none

                     ]

         output:

         ::

            You really hate Orcs who are Bob, Dave
            You really hate Goblins who are Graham
            You really hate Ogres who are Philip, Emanual
            You really hate Trolls who are Ig, Og, Ug

         .. rubric:: See Also
            :name: see-also

         `json.append() <json.append>`__,
         `json.set() <json.set>`__,
         `[code():] <code_(roll_option)>`__,
         `stringToList() <stringToList>`__,
         `listGet() <listGet>`__,
         `listDelete() <listDelete>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=foreach_(roll_option)&oldid=7568"

