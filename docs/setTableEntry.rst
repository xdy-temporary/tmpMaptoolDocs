==========================
setTableEntry - MapToolDoc
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

   .. rubric:: setTableEntry
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

         .. rubric:: setTableEntry() Function
            :name: settableentry-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro <Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.4.0.1**

         .. container:: template_description

            Sets the result for a specified roll value. Returns
            ``true``\ (``1``) if update successful and
            ``false``\ (``0``) if not.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setTableEntry(tableName, roll, result)

               #. .. code-block:: none

                     setTableEntry(tableName, roll, result, imageId)

         **Parameters**

         -  ``tableName`` - A string containing the name of the Table.
         -  ``roll`` - A value to select the desired table entry.
         -  ``result`` - A string containing the result returned by the
            **table()** function.
         -  ``imageId`` - Optional and is the asset id of an image that
            will be returned by the **tableImage()** function.

         | 

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `table() <table_(function)>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setTableEntry&oldid=7168"

