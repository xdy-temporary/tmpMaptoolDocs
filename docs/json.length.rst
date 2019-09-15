========================
json.length - MapToolDoc
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

   .. rubric:: json.length
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

         .. rubric:: json.length() Function
            :name: json.length-function

         .. container:: template_version

            • **Introduced in version 1.3b49**

         .. container:: template_description

            Returns the number of fields in a `json
            object <JSON_Object>`__ or number of elements
            in a `json array <JSON_Array>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: len = json.length(jobj)]

               #. .. code-block:: none

                     [h: len = json.length(jarr)]

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                          [h:a=json.fromStrProp("a=1;b=44;c=12")] [json.length(a)]

                  #. .. code-block:: none

                          [h:a=json.fromList("a,1,g,4")][json.length(a)]

            Returns

            ::

                3

            4

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=json.length&oldid=5615"

