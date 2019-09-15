======================
findToken - MapToolDoc
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

   .. rubric:: findToken
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

         .. rubric:: findToken() Function
            :name: findtoken-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Finds a `token </rptools/wiki/Token:token>`__ on the current
            `map </maptool/index.php?title=Map:map&action=edit&redlink=1>`__
            by the `token </rptools/wiki/Token:token>`__ name, GM name,
            or ID and returns its id. If the optional *mapname*
            parameter is supplied that map will be searched instead. If
            the `token </rptools/wiki/Token:token>`__ is not found then
            an empty string "" is returned.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     findToken(name/ID)

               #. .. code-block:: none

                     findToken(name/ID,mapname)

         **Parameters**

         -  ``name/ID`` - Either the name of the token or the ID.
         -  ``mapname`` - Optional name of the map to search for the
            token on.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            Search for token on current map

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: id = findToken("Hero")]

                  #. .. code-block:: none

                        [if (id == "", "Token not found!", "Token found")]

            Search for token on current map and then search the map
            named *Stash* if not found.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        <!-- Prompts for "TokenName" as it isn't already defined -->

                  #. .. code-block:: none

                        [h: name = TokenName]

                  #. .. code-block:: none

                        [h: id = findToken(name)]

                  #. .. code-block:: none

                        [r, if(id == ""), code: {

                  #. .. code:: de2

                         Not on current map. Searching Stash.<br>

                  #. .. code-block:: none

                         <!-- Search on the map named "Stash" -->

                  #. .. code-block:: none

                          [h: id = findToken(name, "Stash")]

                  #. .. code-block:: none

                         [r: if(id == "", name + " not found!", name + " found in Stash")]

                  #. .. code-block:: none

                        };{

                  #. .. code:: de2

                          [r: name] found on map [r: getCurrentMapName()].

                  #. .. code-block:: none

                        }]

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=findToken&oldid=7449"

