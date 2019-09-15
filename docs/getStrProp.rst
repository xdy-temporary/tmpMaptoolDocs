=======================
getStrProp - MapToolDoc
=======================

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

   .. rubric:: getStrProp
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

            -  `1 getStrProp() Function <#getStrProp.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 Version Changes <#Version_Changes>`__

         .. rubric:: getStrProp() Function
            :name: getstrprop-function

         .. container:: template_version

            • **Introduced in version 1.3b42**

         .. container:: template_description

            Returns the value associated with a key from the specified
            `string property
            list <Macros:string_property_list>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getStrProp(propList, key)

               #. .. code-block:: none

                     getStrProp(propList, key, default)

               #. .. code-block:: none

                     getStrProp(propList, key, default, delim)

         **Parameters**

         -  ``proplist`` - String property list to extract data from.
         -  ``key`` - Key within string to extract. This cannot include
            a space.
         -  ``default`` - Value returned if the key is not found.
         -  ``delim`` - Delimiter between fields (default is ";").

         .. rubric:: Example
            :name: example

         .. container:: template_example

            To get the name from a weapon `string property
            list <Macros:string_property_list>`__

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: weapon = "name=longsword; damage=1d8; maxdamage=8"]

                  #. .. code-block:: none

                        Name of Weapon: [r: getStrProp(weapon, "name")]

            Returns ``Name of Weapon: longsword``.

            To get the minimum damage from a weapon `string property
            list <Macros:string_property_list>`__ with a
            default value should the key not exist

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: weapon = "name=longsword; damage=1d8; maxdamage=8"]

                  #. .. code-block:: none

                        Minimum damage of Weapon: [r: getStrProp(weapon, "mindamage", 1)]

            Returns ``Minimum damage of Weapon: 1``.

            To get the damage from a weapon `string property
            list <Macros:string_property_list>`__ where
            the field delimiter is a colon. The default is **1d3** (note
            that a default value must be provided in order to specify
            the delimiter).

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: weapon = "name=longsword: damage=1d8: maxdamage=8"]

                  #. .. code-block:: none

                        Damage of Weapon: [r: getStrProp(weapon, "damage", "1d3", ":")]

            Returns ``Damage of Weapon: 1d8``.

         | 

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b43** - Added the optional ``error`` parameter.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getStrProp&oldid=6067"

