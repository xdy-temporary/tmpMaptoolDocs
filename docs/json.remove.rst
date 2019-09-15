========================
json.remove - MapToolDoc
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

   .. rubric:: json.remove
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

         .. rubric:: json.remove() Function
            :name: json.remove-function

         .. container:: template_version

            • **Introduced in version 1.3b49**

         .. container:: template_description

            Removes a field from a `JSON
            Object </rptools/wiki/JSON_Object>`__, or the value at the
            specified index from a `JSON
            Array </rptools/wiki/JSON_Array>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: jarr = json.remove(jarr, index)]

               #. .. code-block:: none

                     [h: jarr = json.remove(jobj, key)]

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                          [h:a=json.fromStrProp("a=1;b=44;c=12")] [r:json.remove(a, "c")]

                  #. .. code-block:: none

                          [h:a=json.fromList("a,1,g,4")][r:json.remove(a,3)]

            Returns

            ::

                {"a":1,"b":44}

            ["a",1,"g"]

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=json.remove&oldid=2922"

