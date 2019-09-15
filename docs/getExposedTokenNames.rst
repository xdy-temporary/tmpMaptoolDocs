=================================
getExposedTokenNames - MapToolDoc
=================================

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

   .. rubric:: getExposedTokenNames
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

            -  `1 getExposedTokenNames()
               Function <#getExposedTokenNames.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 Version Changes <#Version_Changes>`__

         .. rubric:: getExposedTokenNames() Function
            :name: getexposedtokennames-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Gets a list containing the names of all of the
            `tokens </rptools/wiki/Token:token>`__ on the current
            `map </maptool/index.php?title=Map:map&action=edit&redlink=1>`__
            that have been exposed, (i.e. not covered by `fog of
            war </maptool/index.php?title=Map:fog_of_war&action=edit&redlink=1>`__).
            The type of the value returned depends on the delimiter
            parameter.

            -  If the delimiter is not specified then a `string
               list </rptools/wiki/Macros:string_list>`__ is returned
               and the default value of ``","`` is used.
            -  If the delimiter ``"json"`` then a `JSON
               Array </rptools/wiki/JSON_Array>`__ is returned.
            -  Otherwise, a `string
               list </rptools/wiki/Macros:string_list>`__ is returned
               with the delimiter passed in.

             

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getExposedTokenNames()

               #. .. code-block:: none

                     getExposedTokenNames(delim)

         If delim is specified then it is used as the delimiter that
         separates the `token </rptools/wiki/Token:token>`__ names.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            The following example will print out the names of all the
            `tokens </rptools/wiki/Token:token>`__ on the current
            `map </maptool/index.php?title=Map:map&action=edit&redlink=1>`__
            not covered by `fog of
            war </maptool/index.php?title=Map:fog_of_war&action=edit&redlink=1>`__.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: names = getExposedTokenNames()]

                  #. .. code-block:: none

                        [r: foreach(name, names, "<br>"): name]

            The following example will return the exposed tokens from
            the TOKEN layer only.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        <!-- get all tokens from the token layer and store in json array -->

                  #. .. code-block:: none

                        [h:allToks        = getTokenNames("json",'{layer:["TOKEN"]}')]

                  #. .. code-block:: none

                        <!-- get all exposed tokens from map -->

                  #. .. code-block:: none

                        [h:allExposed = getExposedTokenNames("json")]

                  #. .. code:: de2

                        <!-- get the intersection of token layer tokens and all the exposed tokens, resulting in token layer exposed tokens only -->

                  #. .. code-block:: none

                        [h:tokExposed   = json.intersection(allToks, allExp)]

                  #. .. code-block:: none

                        <!-- sort the result ascending -->

                  #. .. code-block:: none

                        [h:tokExposed  = json.sort(allToks, allExp,"a")]

            This is exactly the same example as the one above, but then
            nested, so you can have the result in one line of code.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h:tokExposed   = json.sort(json.intersection(getTokenNames("json",'{layer:["TOKEN"]}'), getExposedTokenNames("json")),"a")]

         | 

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b49** - Added *"json"* delimiter option.
            -  **1.3b91** - Apparently now tokens from ALL layers are
               returned, instead of TOKEN LAYER only. Added example to
               correct this.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getExposedTokenNames&oldid=7142"

