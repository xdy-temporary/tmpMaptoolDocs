=========================
getWithState - MapToolDoc
=========================

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

   .. rubric:: getWithState
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

            -  `1 getWithState()
               Function <#getWithState.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 Version Changes <#Version_Changes>`__

         .. rubric:: getWithState() Function
            :name: getwithstate-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Gets a list containing the ids of all the
            `tokens </rptools/wiki/Token:token>`__ on the current
            `map </maptool/index.php?title=Map:map&action=edit&redlink=1>`__
            that have the specified `token
            state </rptools/wiki/Token:state>`__ set. The type of the
            value returned depends on the delimiter parameter.

            -  If the delimiter is not specified then a `string
               list </rptools/wiki/Macros:string_list>`__ is returned
               with the default value of ``","`` is used.
            -  If the delimiter ``json`` then a `JSON
               Array </rptools/wiki/JSON_Array>`__ is returned.
            -  Otherwise a `string
               list </rptools/wiki/Macros:string_list>`__ is returned
               with the delimiter passed in.

             

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getWithState(state)

               #. .. code-block:: none

                     getWithState(state, delim)

         If ``delim`` is specified then it is used to separate the
         values in the list, if it is not specified then it defaults to
         ``","``.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            You can use the following code to print out the ids of all
            of the `tokens </rptools/wiki/Token:token>`__ on the current
            `map </maptool/index.php?title=Map:map&action=edit&redlink=1>`__
            with the "Dead" `token state </rptools/wiki/Token:state>`__
            set.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: ids = getWithState("Dead")]

                  #. .. code-block:: none

                        [foreach(id, ids, "<br>"): id]

         | 

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b49** - Added ``json`` delimiter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getWithState&oldid=7159"

