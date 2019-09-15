===============================
getPropertyDefault - MapToolDoc
===============================

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

   .. rubric:: getPropertyDefault
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

         .. rubric:: getPropertyDefault() Function
            :name: getpropertydefault-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Returns the `default
            value </maptool/index.php?title=Campaign:property_default_value&action=edit&redlink=1>`__
            of a `token
            property </maptool/index.php?title=Token:property&action=edit&redlink=1>`__
            for the `Current Token <Current_Token>`__. If
            the `default
            value </maptool/index.php?title=Campaign:property_default_value&action=edit&redlink=1>`__
            contains nothing then an empty string (``""``) is returned.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getPropertyDefault(name)

               #. .. code-block:: none

                     getPropertyDefault(name, propType)

         **Parameter**

         -  ``name`` - The name of the property to get the default value
            of.
         -  ``propType`` - The token type to get the property from.
            Defaults to the token type of the `Current
            Token <Current_Token>`__.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getPropertyDefault&oldid=7545"

