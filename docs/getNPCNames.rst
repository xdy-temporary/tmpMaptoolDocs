========================
getNPCNames - MapToolDoc
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

   .. rubric:: getNPCNames
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

            -  `1 getNPCNames()
               Function <#getNPCNames.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: getNPCNames() Function
            :name: getnpcnames-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Returns a list containing the names of the `NPC
            tokens </maptool/index.php?title=NPC_Token&action=edit&redlink=1>`__
            on the current
            `map </maptool/index.php?title=Map&action=edit&redlink=1>`__.
            The type of the value returned depends on the delimiter
            parameter.

            -  If the delimiter is not specified then a `string
               list </rptools/wiki/String_List>`__ is returned with the
               default value of ``","`` is used.
            -  If the delimiter ``json`` then a `JSON
               Array </rptools/wiki/JSON_Array>`__ is returned.
            -  Otherwise a `string list </rptools/wiki/String_List>`__
               is returned with the delimiter passed in.

             

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: macros = getNPCNames()]

               #. .. code-block:: none

                     [h: macros = getNPCNames(delim)]

         ``delim`` is the delimiter used to separate the values in the
         `string list </rptools/wiki/String_List>`__ which defaults to
         ``","`` if not specified.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            To display the names of all of the `NPC
            tokens </maptool/index.php?title=NPC_Token&action=edit&redlink=1>`__
            on the current
            `map </maptool/index.php?title=Map:map&action=edit&redlink=1>`__
            use.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: names = getNPCNames()]

                  #. .. code-block:: none

                        [foreach(name, names, "<br>"): name]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `[foreach():] </rptools/wiki/foreach_(roll_option)>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b49** - Added ``json`` delimiter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getNPCNames&oldid=7147"

