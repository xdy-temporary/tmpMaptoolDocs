======================
getOwners - MapToolDoc
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

   .. rubric:: getOwners
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
            | ** This article needs:** *Examples using new
              functionality.*

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 getOwners() Function <#getOwners.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: getOwners() Function
            :name: getowners-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Returns a `String List </rptools/wiki/String_List>`__ or
            `JSON Array </rptools/wiki/JSON_Array>`__ containing the
            names of the owners of a `Token </rptools/wiki/Token>`__.
            The type of the value returned depends on the delimiter
            parameter.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getOwners()

               #. .. code-block:: none

                     getOwners(delim)

               #. .. code-block:: none

                     getOwners(delim, id)

               #. .. code-block:: none

                     getOwners(delim, id, mapname)

         **Parameters**

         -  ``delim`` - The delimiter used to separate the values in the
            `String List </rptools/wiki/String_List>`__, defaults to
            ``","``. If set to ``"json"``, this function will return a
            `JSON Array </rptools/wiki/JSON_Array>`__ instead of a
            `String List </rptools/wiki/String_List>`__.
         -  ``id`` - The token ``id`` of the token which has its owners
            returned, defaults to the `Current
            Token </rptools/wiki/Current_Token>`__.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro </rptools/wiki/Trusted_Macro>`__. 

         -  ``mapname`` - The name of the map to find the token.
            Defaults to the current map.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            To display the
            `owners </maptool/index.php?title=Owners&action=edit&redlink=1>`__
            of the `Current Token </rptools/wiki/Current_Token>`__ use.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: names = getOwners()]

                  #. .. code-block:: none

                        [foreach(name, names, "<br>"): name]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `isOwnedByAll() </rptools/wiki/isOwnedByAll>`__,
            `isOwner() </rptools/wiki/isOwner>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b49** - Added ``json`` delimiter option.
            -  **1.3b51** - Added ``id`` parameter option.
            -  **1.5.4** - Added ``mapname`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getOwners&oldid=7503"

