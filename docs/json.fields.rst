========================
json.fields - MapToolDoc
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

   .. rubric:: json.fields
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

         .. rubric:: json.fields() Function
            :name: json.fields-function

         .. container:: template_version

            • **Introduced in version 1.3b49**

         .. container:: template_description

            Returns the fields (keys) for a `JSON
            Object </rptools/wiki/JSON_Object>`__ or the indexes for a
            `JSON Array </rptools/wiki/JSON_Array>`__ as a string list.
            The type of the value returned depends on the delimiter
            parameter. Note: Because `JSON
            Objects </rptools/wiki/JSON_Object>`__ are unordered,
            *json.fields* will not reflect the order they were set in.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.fields(jobj)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.fields(jobj, delim)

         **Parameters**

         -  ``delim`` =

            -  ``unspecified``: a standard `string
               list </rptools/wiki/Macros:string_list>`__ is returned,
               with its default ``","`` delimiter.
            -  ``"json"``: a `JSON Array </rptools/wiki/JSON_Array>`__
               is returned.
            -  ``"x"``: a `string
               list </rptools/wiki/Macros:string_list>`__ is returned
               with ``"x"`` used as a delimiter.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: a=json.fromStrProp("a=1;b=44;c=12")]

                  #. .. code-block:: none

                        [r: json.fields(a)]

            Returns

            ::

                b,c,a

            | 

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: a=json.fromList("a,1,g,4")]

                  #. .. code-block:: none

                        [r: json.fields(a,";")]

            Returns

            ::

                0;1;2;3

            | 

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: a=json.fromStrProp("a=1;b=44;c=12")]

                  #. .. code-block:: none

                        [r: json.fields(a, "json")]

            Returns

            ["a","c","b"]

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=json.fields&oldid=5866"

