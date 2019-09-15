======================
json.type - MapToolDoc
======================

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

   .. rubric:: json.type
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

         .. rubric:: json.type() Function
            :name: json.type-function

         .. container:: template_version

            • **Introduced in version 1.3b49**

         .. container:: template_description

            Returns a string which contains the type of JSON variable
            that is passed in.
            Return values are

            -  ``ARRAY`` - The object is a `JSON
               Array </rptools/wiki/JSON_Array>`__.
            -  ``OBJECT`` - The object is a `JSON
               Object </rptools/wiki/JSON_Object>`__.
            -  ``UNKNOWN`` - It is neither a `JSON
               Array </rptools/wiki/JSON_Array>`__ nor `JSON
               Object </rptools/wiki/JSON_Object>`__.

             

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: jarr = json.type(val)]

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                          [h:a=json.fromStrProp("a=1;b=44;c=12")] [r:json.type(a)]

                  #. .. code-block:: none

                          [h:a=json.fromList("a,1,g,4")][r:json.type(a)]

                  #. .. code-block:: none

                          [r:json.type("some thing or other")]

            Returns

            ::

                OBJECT
                ARRAY

            UNKNOWN

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=json.type&oldid=7161"

