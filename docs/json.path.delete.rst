=============================
json.path.delete - MapToolDoc
=============================

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

   .. rubric:: json.path.delete
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

         .. rubric:: json.path.delete() Function
            :name: json.path.delete-function

         .. container:: template_version

            • **Introduced in version 1.5.5**

         .. container:: template_description

            Returns a `JSON Array </rptools/wiki/JSON_Array>`__ or `JSON
            Object </rptools/wiki/JSON_Object>`__ with deleted elements.
            These deletions are specified through the path parameter.
            Additional information on how to specify the path is
            availabe `here <https://github.com/json-path/JsonPath>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.path.delete(json, path)

         **Parameters**

         -  ``json`` - The json element to delete the value from.
         -  ``path`` - The path of the values.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            Suppose we have the following nested json:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h:troll = json.set("{}", "name", "Troll", "HP", 75, "Attacks", json.append("Claw", "Bite"))]

                  #. .. code-block:: none

                        [h:orc = json.set("{}", "name", "Orc", "HP", 13, "Attacks", json.append("Sword", "Punch"))]

                  #. .. code-block:: none

                        [h:monsters = json.set("{}", "Troll", troll, "Orc", orc)]

            To delete the "Punch" attack of the Orc, we could write

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: json.path.delete(monsters, "Orc.Attacks.[1]")]

            or, alternatively,

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: json.path.delete(monsters, "Orc.Attacks[?(@ == 'Punch')]")]

            Either statement return the json without the "Punch",

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        {"Troll":{"name":"Troll","HP":75,"Attacks":["Claw","Bite"]},"Orc":{"name":"Orc","HP":13,"Attacks":["Sword"]}}

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=json.path.delete&oldid=7608"

