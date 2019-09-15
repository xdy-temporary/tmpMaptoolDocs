==================================
getMatchingProperties - MapToolDoc
==================================

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

   .. rubric:: getMatchingProperties
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

            -  `1 getMatchingProperties()
               Function <#getMatchingProperties.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: getMatchingProperties() Function
            :name: getmatchingproperties-function

         .. container:: template_version

            • **Introduced in version 1.3b54**

         .. container:: template_description

            Returns a `String List <String_List>`__ or
            `JSON Array <JSON_Array>`__ with names of the
            `Token Properties <Token_Property>`__ on a
            specific `Token <Token>`__ that match the
            given pattern.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getMatchingProperties(pattern)

               #. .. code-block:: none

                     getMatchingProperties(pattern, delim)

               #. .. code-block:: none

                     getMatchingProperties(pattern, delim, id)

               #. .. code-block:: none

                     getMatchingProperties(pattern, delim, id, mapname)

         **Parameters**

         -  ``pattern`` - A regular expression(regex) that represents
            the pattern the properties should match.
         -  ``delim`` - The delimiter used in the `String
            List <String_List>`__ that is returned,
            defaults to ``","``. Returns a `JSON
            Array <JSON_Array>`__ if ``"json"`` is
            specified.
         -  ``id`` - The token ``id`` of the token that is checked for
            properties that match the given pattern, defaults to the
            `Current Token <Current_Token>`__.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro <Trusted_Macro>`__. 

         -  ``mapname`` - The name of the map to find the token.
            Defaults to the current map.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            Say you wanted to keep an inventory list for the
            `Token <Token>`__ you could prefix all of your
            inventory properties with ``Inv:Category:``. For example
            ``Inv:Weapon:Longsword``.
            Then to loop through all of the inventory properties you
            could use

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [foreach(item, getMatchingProperties("Inv:.*")): {

                  #. .. code-block:: none

                            <!-- Do something really exciting here -->

                  #. .. code-block:: none

                        }]

            Or the following to loop through all the weapons

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [foreach(item, getMatchingProperties("Inv:Weapon:.*")): {

                  #. .. code-block:: none

                            <!-- Do something really exciting here -->

                  #. .. code-block:: none

                        }]

            Or even all the armor and all the shields.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [foreach(item, getMatchingProperties("Inv:(Armor|Shield):.*")): {

                  #. .. code-block:: none

                            <!-- Do something really exciting here -->

                  #. .. code-block:: none

                        }]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getMatchingLibProperties() <getMatchingLibProperties>`__
            `getPropertyNames() <getPropertyNames>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.5.4** - Added ``mapname`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getMatchingProperties&oldid=7521"

