======================
getLights - MapToolDoc
======================

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

   .. rubric:: getLights
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

            -  `1 getLights() Function <#getLights.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 Version Changes <#Version_Changes>`__

         .. rubric:: getLights() Function
            :name: getlights-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Returns a string list containing the names of the `light
            sources </maptool/index.php?title=Map:light_source&action=edit&redlink=1>`__
            that are turned on for the `Current
            Token </rptools/wiki/Current_Token>`__. The type of the
            value returned depends on the delimiter parameter.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getLights()

               #. .. code-block:: none

                     getLights(type)

               #. .. code-block:: none

                     getLights(type, delim)

               #. .. code-block:: none

                     getLights(type, delim, id)

               #. .. code:: de2

                     getLights(type, delim, id, mapname)

         **Parameters**

         -  ``type`` - The `light source
            type </maptool/index.php?title=LightSource:light_source_type&action=edit&redlink=1>`__,
            (e.g. "Generic", "D20"). If set to "*", all light sources
            are returned. Defaults to "*".
         -  ``delim`` - The delimiter used to separate values in the
            `string list </rptools/wiki/Macros:string_list>`__. If set
            to "json", a `JSON Array </rptools/wiki/JSON_Array>`__ is
            returned. Defaults to ",".
         -  ``id`` - The token ``id`` of the token to change the light
            sources, defaults to the `Current
            Token </rptools/wiki/Current_Token>`__.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro </rptools/wiki/Trusted_Macro>`__. 

         -  ``mapname`` - The name of the map to find the token.
            Defaults to the current map.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            To get a `string list </rptools/wiki/Macros:string_list>`__
            of all of the `LightSource:light
            sources </maptool/index.php?title=LightSource:light_source&action=edit&redlink=1>`__
            that the current `token </rptools/wiki/Token:token>`__ has
            on.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [getLights()]

            To get a `string list </rptools/wiki/Macros:string_list>`__
            of the `LightSource:light
            sources </maptool/index.php?title=LightSource:light_source&action=edit&redlink=1>`__
            that the current `token </rptools/wiki/Token:token>`__ has
            on with the `lighet source
            type </maptool/index.php?title=LightSource:type&action=edit&redlink=1>`__
            of "Generic".

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [getLights("Generic")]

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b49** - Added *"json"* delimiter option.
            -  **1.5.4** - Added ``id`` and ``mapname`` parameter
               options.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getLights&oldid=7551"

