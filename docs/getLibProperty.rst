===========================
getLibProperty - MapToolDoc
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

   .. rubric:: getLibProperty
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

         .. rubric:: getLibProperty() Function
            :name: getlibproperty-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Returns the value of a `token
            property </rptools/wiki/Token:token_property>`__ from a
            `library token </rptools/wiki/Token:library_token>`__. If
            the lib argument is not specified then the `token
            property </rptools/wiki/Token:token_property>`__ will be
            retrieved from the `library
            token </rptools/wiki/Token:library_token>`__ that the macro
            is currently running from. Unlike
            `getProperty() </rptools/wiki/getProperty>`__, this function
            will not retrieve the default value of a campaign property.
            Default values are generally programmed as local variables
            in a macro, then overridden with the result of this function
            if this function returns a value. An example is shown below.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getLibProperty(name)

               #. .. code-block:: none

                     getLibProperty(name, lib)

         **Important Note** As mentioned in the introduction, if the
         value of the property on the Token equals the default value,
         the function will return nothing! This means that if e.g. you
         set the default property to

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     Weapons : Shotgun, Pistol, Revolver

         And you leave the e.g. the value on the token lib:Compendium
         unchanged, so it will also contain the value "Shotgun, Pistol,
         Revolver", then

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [getLibProperty("Weapons", "lib:Compendium")]

         will return nothing!

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            To get the "init" `token
            property </rptools/wiki/Token:token_property>`__ from the
            `library token </rptools/wiki/Token:library_token>`__ that a
            macro is running from use.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [getLibProperty("init")]

            To get the "init" `token
            property </rptools/wiki/Token:token_property>`__ from the
            `library token </rptools/wiki/Token:library_token>`__ if the
            library token has such a property. If not, use a default
            value of "default".

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [result = getLibProperty("init")]

                  #. .. code-block:: none

                        [IF(result == ""): result = "default" ]

            To get the "init" `token
            property </rptools/wiki/Token:token_property>`__ from a
            `library token </rptools/wiki/Token:library_token>`__ called
            "lib:Attacks" use.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [getLibProperty("init", "lib:Attacks")]

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getLibProperty&oldid=4137"

