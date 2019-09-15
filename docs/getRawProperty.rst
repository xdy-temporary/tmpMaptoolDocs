===========================
getRawProperty - MapToolDoc
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

   .. rubric:: getRawProperty
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

         .. container:: template_stub

            ** This article is a stub, you can help the RPTools Wiki
            project by contributing content to expand this article.**

         .. rubric:: getRawProperty() Function
            :name: getrawproperty-function

         .. container:: template_version

            • **Introduced in version 1.3b51**

         .. container:: template_description

            Gets the unevaluated value of a `token
            property <Token:token_property>`__, returns
            ``""`` if the property is empty. This will not return the
            property's default value.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getRawProperty(prop)

               #. .. code-block:: none

                     getRawProperty(prop, id)

               #. .. code-block:: none

                     getRawProperty(prop, id, mapname)

         **Parameters**

         -  ``prop`` - The name of the property to return.
         -  ``id`` - The id of the token to retrieve the property from.
         -  ``mapname`` - The name of the map to find the token.
            Defaults to the current map.

         | 

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.5.4** - Added ``mapname`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getRawProperty&oldid=7514"

