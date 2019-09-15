==========================
deleteStrProp - MapToolDoc
==========================

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

   .. rubric:: deleteStrProp
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

         .. rubric:: deleteStrProp() Function
            :name: deletestrprop-function

         .. container:: template_version

            • **Introduced in version 1.3b42**

         .. container:: template_description

            Returns a copy of the `string property
            list </rptools/wiki/Macros:string_property_list>`__ with the
            specified key removed.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     deleteStrProp(props, key)

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: deleteStrProp("a=blah; b=doh; c=meh", "a")]

            Returns "b=doh; c=meh".

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=deleteStrProp&oldid=1905"

