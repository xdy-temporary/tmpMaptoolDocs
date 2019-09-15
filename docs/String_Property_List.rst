=================================
String Property List - MapToolDoc
=================================

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

   .. rubric:: String Property List
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

         A string property list is a delimited string containing
         multiple key-value pairs in the format
         ``"var1=value1; var2=value2;..."``

         For example:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: stringPropertyList="var1=foo; var2=bar; var3=baz;"]

         String property lists are zero-based (*i.e.*, the first item in
         a string property list is item ``0``). When a key-value pair is
         extracted from a string property list using one of the
         available `String
         Functions </rptools/wiki/Category:String_Function>`__ that work
         with string property lists, the value of the pair is considered
         a string, and must be converted to or evaluated to a number to
         perform numeric computations.

         The default delimiter in a string property list is the
         semicolon (``";"``), however, the `String
         Functions </rptools/wiki/Category:String_Function>`__ that work
         with string property lists permit the use of alternate
         delimiters.

         The `String Property List
         Functions </rptools/wiki/Category:String_Property_List_Function>`__
         only work with the default delimiter.

         String property lists may be stored in a `token
         property </rptools/wiki/Token_Property>`__.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=String_Property_List&oldid=3998"

