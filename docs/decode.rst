===================
decode - MapToolDoc
===================

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

   .. rubric:: decode
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

         .. rubric:: decode() Function
            :name: decode-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Decodes a string that was encoded with the
            `encode() <encode>`__ function. The
            `encode() <encode>`__ and decode() functions
            can be used to encode a property list so that it can be
            embedded within another property list.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     decode(str)

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: getStrProp(decode(getStrProp(inv, "Weapons"), "Name")]

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=decode&oldid=1930"

