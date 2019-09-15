========================
json.toList - MapToolDoc
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

   .. rubric:: json.toList
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

         .. rubric:: json.toList() Function
            :name: json.tolist-function

         .. container:: template_version

            • **Introduced in version 1.3b49**

         .. container:: template_description

            Creates a `string list <Macros:string_list>`__
            from a `JSON Array <JSON_Array>`__. If the
            delimiter is not specified then the default value of ',' is
            used.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: jarr = json.toList(jarr)]

               #. .. code-block:: none

                     [h: jarr = json.toList(jarr, delim)]

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                          [h:a=json.fromList("a,1,g,4")]

                  #. .. code-block:: none

                          [json.toList(a)]

            Returns

            a,1,g,4

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=json.toList&oldid=4004"

