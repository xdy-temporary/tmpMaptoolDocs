=========================
setTableRoll - MapToolDoc
=========================

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

   .. rubric:: setTableRoll
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

            -  `1 setTableRoll()
               Function <#setTableRoll.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: setTableRoll() Function
            :name: settableroll-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.4.0.1**

         .. container:: template_description

            Sets the roll expression for the specified table.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getTableRoll(tableName, roll)

         **Parameters**

         -  ``tableName`` - A string containing the name of the Table.
         -  ``roll`` - A string containing the new roll expression. If
            the value is "" the roll will be set to a default expression
            that should cover all table entries.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r:setTableRoll("test","")]

                  #. .. code-block:: none

                        [r:setTableRoll("test","1d6+1")]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getTableRoll() </rptools/wiki/getTableRoll>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setTableRoll&oldid=6726"

