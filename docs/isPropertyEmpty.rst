============================
isPropertyEmpty - MapToolDoc
============================

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

   .. rubric:: isPropertyEmpty
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
            | ** This article needs:** *Examples using the new
              functionality.*

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 isPropertyEmpty()
               Function <#isPropertyEmpty.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: isPropertyEmpty() Function
            :name: ispropertyempty-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Returns ``true``\ (``1``) if the `Token
            Property <Token_Property>`__ for a specific
            `Token <Token>`__ is empty. A `Token
            Property <Token_Property>`__ is considered
            empty if it is ``NULL``; if an empty string (``""``) has
            been assigned to it, it is not considered empty. **Note:**
            If the token type sets a default value, this function will
            still see the property as empty. Try using
            `json.isEmpty() <json.isEmpty>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     isPropertyEmpty(property)

               #. .. code-block:: none

                     isPropertyEmpty(property, id)

               #. .. code-block:: none

                     isPropertyEmpty(property, id, mapname)

         **Parameters**

         -  ``property`` - The name of the property that has its value
            checked.
         -  ``id`` - The token ``id`` of the token that has its value
            checked, defaults to the `Current
            Token <Current_Token>`__.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro <Trusted_Macro>`__. 

         -  ``mapname`` - The name of the map to find the token.
            Defaults to the current map.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r, if(isPropertyEmpty("propertyName")): propertyName = someDefaultValue]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `resetProperty() <resetProperty>`__,
            `getProperty() <getProperty>`__,
            `setProperty() <setProperty>`__,

            `json.isEmpty() <json.isEmpty>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b51** - Added ``id`` parameter option.
            -  **1.5.4** - Added ``mapname`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=isPropertyEmpty&oldid=7509"

