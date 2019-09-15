==========================
resetProperty - MapToolDoc
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

   .. rubric:: resetProperty
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

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 resetProperty()
               Function <#resetProperty.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 See Also <#See_Also>`__
               -  `1.3 Version Changes <#Version_Changes>`__

         .. rubric:: resetProperty() Function
            :name: resetproperty-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Resets the specified `Token
            Property </rptools/wiki/Token_Property>`__ on a specific
            `Token </rptools/wiki/Token>`__ so that it is empty and will
            return the default value when queried (if it has one).

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     resetProperty(property)

               #. .. code-block:: none

                     resetProperty(property, id)

               #. .. code-block:: none

                     resetProperty(property, id, mapname)

         **Parameters**

         -  ``property`` - The name of the property to reset.
         -  ``id`` - The token ``id`` of the token which has its
            property reset, defaults to the `Current
            Token </rptools/wiki/Current_Token>`__.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro </rptools/wiki/Trusted_Macro>`__. 

         -  ``mapname`` - The name of the map to find the token.
            Defaults to the current map.

         | 

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `isPropertyEmpty() </rptools/wiki/isPropertyEmpty>`__,
            `setProperty() </rptools/wiki/setProperty>`__,

            `getProperty() </rptools/wiki/getProperty>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b51** - Added ``id`` parameter option.
            -  **1.3b68** - `Token
               Property </rptools/wiki/Token_Property>`__ is now deleted
               from `Token </rptools/wiki/Token>`__
            -  **1.5.4** - Added ``mapname`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=resetProperty&oldid=7506"

