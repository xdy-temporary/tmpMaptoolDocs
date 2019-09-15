========================
getProperty - MapToolDoc
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

   .. rubric:: getProperty
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

            -  `1 getProperty()
               Function <#getProperty.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: getProperty() Function
            :name: getproperty-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Returns the value of a `Token
            Property </rptools/wiki/Token_Property>`__ on a
            `Token </rptools/wiki/Token>`__. If the `Token
            Property </rptools/wiki/Token_Property>`__ is empty
            (``NULL``) or not defined, an empty string (``""``) is
            returned.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getProperty(property)

               #. .. code-block:: none

                     getProperty(property, id)

               #. .. code-block:: none

                     getProperty(property, id, mapname)

         **Parameter**

         -  ``property`` - The property that has its value returned. For
            referencing the literal name of the property (for instance,
            if you wish to get the property *Constitution* configured in
            Campaign Properties), enclose the property name in quotes.
            If using a variable whose *value* is the name of the
            property, do not enclose the variable name in quotes.
         -  ``id`` - The token ``id`` or name of the token that has its
            property value returned, defaults to the `Current
            Token </rptools/wiki/Current_Token>`__.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro </rptools/wiki/Trusted_Macro>`__. 

         -  ``mapname`` - The name of the map to find the token.
            Defaults to the current map.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            Getting a property using the literal property name.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        The value of property 'Strength' is [r: getProperty("Strength")].

            This will output the following if **Strength** has the value
            **18**:

            ::

               The value of property 'Strength' is 18.

            Getting a property using a variable.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h:desiredProperty = "Constitution"]

                  #. .. code-block:: none

                        The value of property 'Constitution' is [r: getProperty(desiredProperty)].

            This will output the following if **Constitution** has the
            value **12**:

            The value of property 'Constitution' is 12.

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `setProperty() </rptools/wiki/setProperty>`__,
            `resetProperty() </rptools/wiki/resetProperty>`__,

            `isPropertyEmpty() </rptools/wiki/isPropertyEmpty>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b51** - Added ``id`` parameter option.
            -  **1.3b51** - Changed to return the default value if the
               property has no value.
            -  **1.5.4** - Added ``mapname`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getProperty&oldid=7507"

