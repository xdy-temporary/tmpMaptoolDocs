===========================
json.path.read - MapToolDoc
===========================

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

   .. rubric:: json.path.read
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

         .. rubric:: json.path.read() Function
            :name: json.path.read-function

         .. container:: template_version

            • **Introduced in version 1.5.5**

         .. container:: template_description

            Returns the values in a nested `JSON
            Array </rptools/wiki/JSON_Array>`__ or `JSON
            Object </rptools/wiki/JSON_Object>`__ corresponding to the
            provided path. For detailed information on how to specify
            the path, please read the `following
            document <https://github.com/json-path/JsonPath>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.path.read(json, path)

         **Parameters**

         -  ``json`` - The json element to get the values from.
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

            To access the value of the first weapon of the Orc, we can
            type

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [json.path.read(monsters, "Orc.Attacks.[0]")]

            which returns "Sword".

            If we instead wanted to return an array with the attacks of
            every monster, we could type

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: json.path.read(monsters, ".Attacks")]

            which would return [["Claw","Bite"],["Sword","Punch"]].

            Inline filters are also supported, so that if we want the
            name of the monsters with > 30 HPs, we can type

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: json.path.read(monsters, ".[?(@.HP > 30)].name")]

            which returns ["Troll"].

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=json.path.read&oldid=7602"

