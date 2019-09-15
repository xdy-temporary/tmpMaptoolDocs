==========================
getTableEntry - MapToolDoc
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

   .. rubric:: getTableEntry
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

            -  `1 getTableEntry()
               Function <#getTableEntry.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: getTableEntry() Function
            :name: gettableentry-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro <Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.5.4**

         .. container:: template_description

            Retrieves the raw table data for the specified entry as a
            JSON object. Returns an empty string if the entry doesn't
            exist. If no image is associated with the entry the
            ``assetid`` will be an empty string.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  getTableEntry(table, roll)

         **Parameters**

         -  ``table`` - Name of table as a string.
         -  ``roll`` - The entry to retrieve as if a roll of that value
            had been made.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            Get the entry from table "Critters" matching a roll of 4.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: getTableEntry("Critters", 4)]

            Returns:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: javascript source-javascript

                  .. code-block:: none

                     {"min":3, "max":5, "value": "duck", "assetid":""}

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `addTableEntry() <addTableEntry>`__
            `setTableEntry() <setTableEntry>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getTableEntry&oldid=7554"

