=====================
getOwned - MapToolDoc
=====================

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

   .. rubric:: getOwned
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

            -  `1 getOwned() Function <#getOwned.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: getOwned() Function
            :name: getowned-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro <Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Returns a list containing the ids of the
            `tokens <token>`__ on the current
            `map </maptool/index.php?title=Map&action=edit&redlink=1>`__
            that are owned by the specified player. The type of the
            value returned depends on the delimiter parameter.

            -  If the delimiter is not specified then a `string
               list <String_List>`__ is returned with the
               default value of ``","`` is used.
            -  If the delimiter ``json`` then a `json
               array <JSON_Array>`__ is returned.
            -  Otherwise a `string list <String_List>`__
               is returned with the delimiter passed in.

             

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getOwned(player)

               #. .. code-block:: none

                     getOwned(player, delim)

         ``delim`` is the delimiter used to separate the values in the
         `string list <String_List>`__ which defaults to
         ``","`` if not specified.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            To display the ids of all of the
            `tokens <Token>`__ on the current
            `map </maptool/index.php?title=Map&action=edit&redlink=1>`__
            by the
            `Player </maptool/index.php?title=Player&action=edit&redlink=1>`__
            use.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: ids = getOwned(getPlayerName())]

                  #. .. code-block:: none

                        [foreach(id, ids, "<br>"): id]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `[foreach():] <foreach_(roll_option)>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b49** - Added ``json`` delimiter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getOwned&oldid=7148"

