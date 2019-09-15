==========================
json.fromList - MapToolDoc
==========================

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

   .. rubric:: json.fromList
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

            -  `1 json.fromList()
               Function <#json.fromList.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: json.fromList() Function
            :name: json.fromlist-function

         .. container:: template_version

            • **Introduced in version 1.3b49**

         .. container:: template_description

            Returns a `JSON Array </rptools/wiki/JSON_Array>`__ from a
            `String List </rptools/wiki/String_List>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.fromList(strList)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.fromList(strList, delim)

         **Parameters**

         -  ``strList`` - The `String
            List </rptools/wiki/String_List>`__ that is converted to a
            `JSON Array </rptools/wiki/JSON_Array>`__.
         -  ``delim`` - The delimiter used in the `String
            List </rptools/wiki/String_List>`__, defaults to ``","``.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r:json.fromList("a,1,g,4")]

            Returns ``["a",1,"g",4]``

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `json.toList() </rptools/wiki/json.toList>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=json.fromList&oldid=3333"

