===========================
json.toStrProp - MapToolDoc
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

   .. rubric:: json.toStrProp
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

         .. rubric:: json.toStrProp() Function
            :name: json.tostrprop-function

         .. container:: template_version

            • **Introduced in version 1.3b49**

         .. container:: template_description

            Creates a `string
            list <Macros:string_property_list>`__ from a
            `json object <JSON_Object>`__. With the
            specified delimiter, if a delimiter is not provided then the
            default value of ';' is used.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: strProp = json.toStrProp(jobj)]

               #. .. code-block:: none

                     [h: strProp = json.toStrProp(jobj, delim)]

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                          [h:a=json.fromStrProp("a=1;b=44;c=12")] [r:json.toStrProp(a)]

                  #. .. code-block:: none

                          [h:a=json.fromList("a,1,g,4")][r:json.toStrProp(a)]

            Returns

            ::

                a=1;c=12;b=44

            0=a;1=1;2=g;3=4

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=json.toStrProp&oldid=5613"

