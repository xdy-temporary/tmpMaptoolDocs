=====================================
getMatchingLibProperties - MapToolDoc
=====================================

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

   .. rubric:: getMatchingLibProperties
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

            -  `1 getMatchingLibProperties()
               Function <#getMatchingLibProperties.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: getMatchingLibProperties() Function
            :name: getmatchinglibproperties-function

         .. container:: template_version

            • **Introduced in version 1.3b54**

         .. container:: template_description

            Returns a `String List </rptools/wiki/String_List>`__ or
            `JSON Array </rptools/wiki/JSON_Array>`__ with names of the
            `Token Properties </rptools/wiki/Token_Property>`__ on a
            specific `Library Token </rptools/wiki/Library_Token>`__
            that match the given pattern.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getMatchingLibProperties(pattern)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getMatchingLibProperties(pattern, lib)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getMatchingLibProperties(pattern, lib, delim)

         **Parameters**

         -  ``pattern`` - A regular expression(regex) that represents
            the pattern the properties should match.
         -  ``lib`` - The name of the `Library
            Token </rptools/wiki/Library_Token>`__ that is checked for
            properties that match, defaults to the `Library
            Token </rptools/wiki/Library_Token>`__ the macro is running
            on.
         -  ``delim`` - The delimiter used in the `String
            List </rptools/wiki/String_List>`__ that is returned,
            defaults to ``","``. Returns a `JSON
            Array </rptools/wiki/JSON_Array>`__ if ``"json"`` is
            specified.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            Assuming that you have a `Library
            Token </rptools/wiki/Library_Token>`__ that contained a list
            of all the items and their detail in your campaign stored as
            `Token </rptools/wiki/Token>`__ properties names with the
            following format ``Type:Item Name`` (for example
            ``Weapon:Longsword)``, you could use the following code to
            loop through
            all the weapons.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [foreach(item, getMatchingLibProperties("Weapon:.*", "Lib:Items")): {

                  #. .. code-block:: none

                            <!-- Do something really exciting here -->

                  #. .. code-block:: none

                        }]

            Or the following to loop through all the armor

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [foreach(item, getMatchingLibProperties("Armor:.*", "Lib:Items")): {

                  #. .. code-block:: none

                            <!-- Do something really exciting here -->

                  #. .. code-block:: none

                        }]

            Or even all the armor and all the shields.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [foreach(item, getMatchingLibProperties("(Armor|Shield):.*", "Lib:Items")): {

                  #. .. code-block:: none

                            <!-- Do something really exciting here -->

                  #. .. code-block:: none

                        }]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getMatchingProperties() </rptools/wiki/getMatchingProperties>`__
            `getLibPropertyNames() </rptools/wiki/getLibPropertyNames>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getMatchingLibProperties&oldid=6032"

