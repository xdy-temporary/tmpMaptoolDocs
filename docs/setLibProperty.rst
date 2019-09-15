===========================
setLibProperty - MapToolDoc
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

   .. rubric:: setLibProperty
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

         .. rubric:: setLibProperty() Function
            :name: setlibproperty-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Sets the `Token
            Property </rptools/wiki/Token:token_property>`__ on a
            `Library Token </rptools/wiki/Token:library_token>`__. if
            the name of the `Library
            Token </rptools/wiki/Token:library_token>`__ is not
            specified then the `Token
            Property </rptools/wiki/Token:token_property>`__ is set on
            the `Library Token </rptools/wiki/Token:library_token>`__
            that the macro is running from.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setLibProperty(name, value)

               #. .. code-block:: none

                     setLibProperty(name, value, libName)

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            Set a property on the `Library
            Token </rptools/wiki/Token:library_token>`__ that the macro
            is running from.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: setLibProperty("defaultStrength", 10)]

            Set a property on a specifig `Library
            Token </rptools/wiki/Token:library_token>`__.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: setLibProperty("defaultStrength", 10, "Lib:Character")]

            Known Bug: note that using setLibProperty during
            onCampaignLoad and not being on the map where the lib
            resides, will result in a duplicate of that lib on the
            current map!

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setLibProperty&oldid=7129"

