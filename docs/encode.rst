===================
encode - MapToolDoc
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

   .. rubric:: encode
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

         .. rubric:: encode() Function
            :name: encode-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Encodes a string that was can be decoded with the
            `decode() <decode>`__ function. The
            `decode() <decode>`__ and encode() functions
            can be used to encode a property list so that it can be
            embedded within another property list.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     encode(str)

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: innerPropList = encode("val1=blah ; val2=blahblah")]

                  #. .. code-block:: none

                        [h: props = setStrProp(props, key, innerPropList)]

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=encode&oldid=1929"

