===============================
getVisibleMapNames - MapToolDoc
===============================

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

   .. rubric:: getVisibleMapNames
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

            -  `1 getVisibleMapNames()
               Function <#getVisibleMapNames.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: getVisibleMapNames() Function
            :name: getvisiblemapnames-function

         .. container:: template_version

            • **Introduced in version 1.3b55**

         .. container:: template_description

            Returns the names of all of the player visible maps as
            either a `String List <String_List>`__ or
            `JSON Array <JSON_Array>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getVisibleMapNames()

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getVisibleMapNames(delim)

         **Parameters**

         -  ``delim`` - The delimiter to use for the `String
            List <String_List>`__. If the value is
            ``json`` then a `JSON Array <JSON_Array>`__ is
            returned.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            To get the names of all of the player visible maps in a
            `String List <String_List>`__.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: maps = getVisibleMapNames()]

            To get the names of all of the player visible maps in a
            `JSON Array <JSON_Array>`__

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: maps = getVisibleMapNames("json")]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getCurrentMapName() <getCurrentMapName>`__
            `getAllMapNames() <getAllMapNames>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getVisibleMapNames&oldid=6697"

