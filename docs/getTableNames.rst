==========================
getTableNames - MapToolDoc
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

   .. rubric:: getTableNames
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

            -  `1 getTableNames()
               Function <#getTableNames.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: getTableNames() Function
            :name: gettablenames-function

         .. container:: template_version

            • **Introduced in version 1.4.0.1**

         .. container:: template_description

            Returns a list containing the names of the tables in the
            campaign. The type of the value returned depends on the
            delimiter parameter. The function can be used by players or
            from a non-trusted macro, but it will only return
            player-visible tables. When used by a GM or a trusted macro
            it returns all tables.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getTableNames()

               #. .. code-block:: none

                     getTableNames(delim)

         If ``delim`` is specified then it is used to separate the
         values in the list; if it is not specified then it defaults to
         "``,``". When ``delim`` is the string "``json``" the return
         value will be in the form of a `JSON
         Array <JSON_Array>`__.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r:getTableNames()]

                  #. .. code-block:: none

                        [r:getTableNames("<br>")]

                  #. .. code-block:: none

                        [r:getTableNames("json")]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `Table </maptool/index.php?title=Table&action=edit&redlink=1>`__,
            `table() <table_(function)>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getTableNames&oldid=6656"

