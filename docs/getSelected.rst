========================
getSelected - MapToolDoc
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

   .. rubric:: getSelected
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

            -  `1 getSelected()
               Function <#getSelected.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 Version Changes <#Version_Changes>`__

         .. rubric:: getSelected() Function
            :name: getselected-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Returns a list containing the ids of the selected
            `tokens <Token:token>`__ on the current
            `map </maptool/index.php?title=Map:map&action=edit&redlink=1>`__.
            The type of the value returned depends on the delimiter
            parameter.

            -  If the delimiter is not specified then a `string
               list <Macros:string_list>`__ is returned
               with the default value of ``","`` is used.
            -  If the delimiter ``json`` then a `JSON
               Array <JSON_Array>`__ is returned.
            -  Otherwise a `string
               list <Macros:string_list>`__ is returned
               with the delimiter passed in.

             

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getSelected()

               #. .. code-block:: none

                     getSelected(delim)

         ``delim`` is the delimiter used to separate the values in the
         `string list <Macros:string_list>`__ which
         defaults to ``","`` if not specified.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            To display the ids of all of the selected
            `tokens <Token:token>`__ on the current
            `map </maptool/index.php?title=Map:map&action=edit&redlink=1>`__
            use.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: ids = getSelected()]

                  #. .. code-block:: none

                        [foreach(id, ids, "<br>"): id]

         | 

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b49** - Added ``json`` delimiter option.
            -  **1.3b51** - No longer a trusted function.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getSelected&oldid=7152"

