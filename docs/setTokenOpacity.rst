============================
setTokenOpacity - MapToolDoc
============================

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

   .. rubric:: setTokenOpacity
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

            -  `1 setTokenOpacity()
               Function <#setTokenOpacity.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 Version Changes <#Version_Changes>`__

         .. rubric:: setTokenOpacity() Function
            :name: settokenopacity-function

         .. container:: template_version

            • **Introduced in version 1.4.2.0**

         .. container:: template_description

            sets the opacity value of the corresponding token.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  setTokenOpacity(value)
                  setTokenOpacity(value, id)
                  setTokenOpacity(value, id, mapname)

         **Parameters**

         -  ``value`` - The value of the opacity to set, ranging from 0
            (completely transparent) to 100 (completely opaque).
         -  ``id`` - OPTIONAL: The token ``id`` of the token for which
            you want to retrieve the opacity, defaults to the `Current
            Token <Current_Token>`__.
         -  ``mapname`` - OPTIONAL: The name of the map to find the
            token. Defaults to the current map.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: setTokenOpacity(50, "Dragon")]

                  #. .. code-block:: none

                        [h, token("Dragon"): setTokenOpacity(75)]

         | 

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.5.4** - Added ``mapname`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setTokenOpacity&oldid=7480"

