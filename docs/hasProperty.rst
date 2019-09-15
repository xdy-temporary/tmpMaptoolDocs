========================
hasProperty - MapToolDoc
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

   .. rubric:: hasProperty
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

            | ** This article is a stub, you can help the RPTools Wiki
              project by contributing content to expand this article.**
            | ** This article needs:** *Examples of usage.*

         .. rubric:: hasProperty() Function
            :name: hasproperty-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Returns ``true``\ (``1``) if the `Token
            Property </rptools/wiki/Token_Property>`__ with the
            specified name exists on a `Token </rptools/wiki/Token>`__.
            The function will return true if the token possesses the
            specified property, even if that property is not defined in
            the token's current property type.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     hasProperty(name)

               #. .. code-block:: none

                     hasProperty(name, id)

               #. .. code-block:: none

                     hasProperty(name, id, mapname)

         **Parameters**

         -  ``name`` - The name of the `Token
            Property </rptools/wiki/Token_Property>`__ which is checked
            for on the token.
         -  ``id`` - The token ``id`` of the token which is checked for
            the `Token Property </rptools/wiki/Token_Property>`__,
            defaults to the `Current
            Token </rptools/wiki/Current_Token>`__.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro </rptools/wiki/Trusted_Macro>`__. 

         -  ``mapname`` - The name of the map to find the token.
            Defaults to the current map.

         | 

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b51** - Added ``id`` parameter option.
            -  **1.5.4** - Added ``mapname`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=hasProperty&oldid=7493"

