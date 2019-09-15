=======================
setStrProp - MapToolDoc
=======================

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

   .. rubric:: setStrProp
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

            -  `1 setStrProp() Function <#setStrProp.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: setStrProp() Function
            :name: setstrprop-function

         .. container:: template_version

            • **Introduced in version 1.3b42**

         .. container:: template_description

            Returns a `String Property
            List <String_Property_List>`__ with the key
            set to the value passed in.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setStrProp(propList, key, value)

         **Parameters**

         -  ``propList`` - The `String Property
            List <String_Property_List>`__ affected by
            this function.
         -  ``key`` - The key in the specified `String Property
            List <String_Property_List>`__ that will have
            its value set.
         -  ``value`` - The value that the specified key will be set to.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            Add a new key to an existing `String Property
            List <String_Property_List>`__:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: weapon = "name=longsword; damage=1d8; maxdamage=8"]

                  #. .. code-block:: none

                        [h: weapon = setStrProp(weapon, "value", 10)]

                  #. .. code-block:: none

                        [r: weapon]

            Returns
            ``"name=longsword ; damage=1d8 ; maxdamage=8 ; value=10 ; "``

            Change the value of a key in an existing `String Property
            List <String_Property_List>`__:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: weapon = "name=longsword; damage=1d8; maxdamage=8"]

                  #. .. code-block:: none

                        [h: weapon = setStrProp(weapon, "damage", "1d6")]

                  #. .. code-block:: none

                        [r: weapon]

            Returns ``"name=longsword ; damage=1d6 ; maxdamage=8 ; "``

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getStrProp() <getStrProp>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setStrProp&oldid=2813"

