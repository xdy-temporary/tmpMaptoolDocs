========================
setProperty - MapToolDoc
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

   .. rubric:: setProperty
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

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 setProperty()
               Function <#setProperty.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: setProperty() Function
            :name: setproperty-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Sets the value of a `Token
            Property <Token_Property>`__ on the `Current
            Token <Current_Token>`__ (unless trusted, in
            which case a Token ID can be supplied to indicate which
            token is to be affected). Note that if there is not already
            an existing property by the name listed in the macro,
            setProperty will create a new Token Property with that name.
            Any created Property will not be visible in the Properties
            tab of the Edit Token window but can still be used like
            normal. It's value can be retrieved with the getProperty
            command.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setProperty(property, value)

               #. .. code-block:: none

                     setProperty(property, value, id)

               #. .. code-block:: none

                     setProperty(property, value, id, mapname)

         **Parameters**

         -  ``property`` - A string containing the name of the property
            that has its value set.
         -  ``value`` - The value that the property is set to.
         -  ``id`` - The token ``id`` of the token which has its
            property set, defaults to the `Current
            Token <Current_Token>`__.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro <Trusted_Macro>`__. 

         -  ``mapname`` - The name of the map to find the token.
            Defaults to the current map.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            Sets a property named ``Health`` to the value of ``10`` on
            the `Current Token <Current_Token>`__.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: setProperty("Health", 10)]

            Sets a property named ``Fatigue`` to the value of ``5`` on
            the selected token.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: setProperty("Fatigue", 5, getSelected())]

            Sets a property named ``Strength`` to the value of ``20`` on
            the selected token using variables.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: Property = "Strength"]

                  #. .. code-block:: none

                        [h: Value = 20]

                  #. .. code-block:: none

                        [h: ID = getSelected()]

                  #. .. code-block:: none

                        [h: setProperty(Property, Value, ID)]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getProperty() <getProperty>`__,
            `resetProperty() <resetProperty>`__,

            `isPropertyEmpty() <isPropertyEmpty>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b51** - Added ``id`` parameter option.
            -  **1.5.4** - Added ``mapname`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setProperty&oldid=7508"

