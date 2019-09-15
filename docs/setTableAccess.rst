===========================
setTableAccess - MapToolDoc
===========================

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

   .. rubric:: setTableAccess
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

            -  `1 setTableAccess()
               Function <#setTableAccess.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: setTableAccess() Function
            :name: settableaccess-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.4.0.1**

         .. container:: template_description

            Sets whether or not the specified table is accessible to
            players.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setTableAccess(tableName, accessible)

         **Parameters**

         -  ``tableName`` - A string containing the name of the Table.
         -  ``accessible`` - Whether or not the table can be accessed by
            players in the Table Window, ``true``\ (``1``) or
            ``false``\ (``0``).

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h:setTableAccess("randomMonsters", 0)]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getTableAccess() </rptools/wiki/getTableAccess>`__
            `getTableVisible() </rptools/wiki/getTableVisible>`__
            `setTableVisible() </rptools/wiki/setTableVisible>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setTableAccess&oldid=6724"

