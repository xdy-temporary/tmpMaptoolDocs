==========================
json.objrolls - MapToolDoc
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

   .. rubric:: json.objrolls
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

         .. rubric:: json.objrolls() Function
            :name: json.objrolls-function

         .. container:: template_version

            • **Introduced in version 1.4.0.5**

         .. container:: template_description

            Is similar to `json.rolls() <json.rolls>`__
            but returns a JSON object.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.objrolls(names, stat, rolls)

         **Parameters**

         -  ``names`` - A JSON array containing the names to be used for
            each group.
         -  ``stat`` - A JSON array with the stat names.
         -  ``rolls`` - Either a single string containing a dice roll
            expression or a JSON array of dice roll expressions.

         This will generate rolls for each stat in a group for each
         "name". Rolls is either a single string with a roll expression
         in which case every stat will use same roll expression, or a
         json array with a roll expression for each stat (so must be
         same size as stat).

         *Example:*

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     {json.indent(json.objrolls("['henchman1', 'henchman2', 'henchman3']",

               #. .. code-block:: none

                             "['Str', 'Dex', 'Con', 'Int', 'Wis', 'Chr']",

               #. .. code-block:: none

                             "3d6"),2)}

         ::

            code:{  "henchman1":   {
                "Str": 10,
                "Dex": 12,
                "Con": 10,
                "Int": 10,
                "Wis": 8,
                "Chr": 12
              },
                   "henchman2":   {
                "Str": 11,
                "Dex": 10,
                "Con": 7,
                "Int": 13,
                "Wis": 9,
                "Chr": 7
              },
                   "henchman3":   {
                "Str": 10,
                "Dex": 10,
                "Con": 10,
                "Int": 12,
                "Wis": 15,
                "Chr": 13
              }}

         *Example:*

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     {json.indent(json.objrolls("['henchman1', 'henchman2', 'henchman3']",

               #. .. code-block:: none

                             "['Str', 'Dex', 'Con', 'Int', 'Wis', 'Chr']",

               #. .. code-block:: none

                             "['3d6+1', '3d6', '3d6', '3d6-2', '3d6', '2d6']"),2)}

         ::

            code:{  "henchman1":   {
                "Str": 11,
                "Dex": 12,
                "Con": 13,
                "Int": 8,
                "Wis": 10,
                "Chr": 11
              },
                    "henchman2":   {
                "Str": 12,
                "Dex": 11,
                "Con": 12,
                "Int": 8,
                "Wis": 12,
                "Chr": 3
              },
                    "henchman3":   {
                "Str": 12,
                "Dex": 13,
                "Con": 9,
                "Int": 8,
                "Wis": 13,
                "Chr": 7
              }}

         | 

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `Introduction to JSON
            Datatypes <Introduction_to_JSON_Datatypes>`__
            , `json.rolls() <json.rolls>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=json.objrolls&oldid=7124"

