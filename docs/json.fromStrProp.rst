=============================
json.fromStrProp - MapToolDoc
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

   .. rubric:: json.fromStrProp
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

         .. rubric:: json.fromStrProp() Function
            :name: json.fromstrprop-function

         .. container:: template_version

            • **Introduced in version 1.3b49**

         .. container:: template_description

            Creates a `json object </rptools/wiki/JSON_Object>`__ from a
            `string property
            list </rptools/wiki/Macros:string_property_list>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.fromStrProp(propList)

               #. .. code-block:: none

                     json.fromStrProp(propList,delim)

         **Parameters**

         -  ``propList`` - String property list to extract data from.
         -  ``delim`` - Delimiter between fields (default is ``";"``).

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r:json.fromStrProp("a=1;b=44;c=12")]

            Returns

            {"a":1,"c":12,"b":44}

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=json.fromStrProp&oldid=5867"

