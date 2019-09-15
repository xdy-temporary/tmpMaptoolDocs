==============================
getAllPlayerNames - MapToolDoc
==============================

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

   .. rubric:: getAllPlayerNames
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

         .. rubric:: getAllPlayerNames() Function
            :name: getallplayernames-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro <Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Gets a `string list <Macros:string_list>`__
            containing the names of all the players that are connected.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getAllPlayerNames()

               #. .. code-block:: none

                     getAllPlayerNames(delim)

         If ``delim`` is specified then it is used to separate the
         values in the list; if it is not specified then it defaults to
         "``,``". When ``delim`` is the string "``json``" the return
         value will be in the form of a `JSON
         Array <JSON_Array>`__.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            You can use the following code to print the names of all of
            the players that are connected.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        Players Connected<br>

                  #. .. code-block:: none

                        [h: players = getAllPlayerNames()]

                  #. .. code-block:: none

                        [foreach(name, players, "<br>"): name]

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getAllPlayerNames&oldid=5155"

