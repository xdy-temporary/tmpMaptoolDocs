========================
getLastPath - MapToolDoc
========================

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

   .. rubric:: getLastPath
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

         .. rubric:: getLastPath() Function
            :name: getlastpath-function

         .. container:: template_version

            • **Introduced in version 1.3.b74**

         .. container:: template_description

            Returns a json array of the coordinates of every step in the
            last movement path of the impersonated token. The
            coordinates are json objects with the keys ``x`` and ``y``.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [r: getLastPath()]

               #. .. code-block:: none

                     [r: getLastPath(units)]

         **Parameters**

         -  ``units`` - If set to ``false``\ (``0``), the coordinate is
            a location on the grid in *cells*. Defaults to
            ``true``\ (``1``), where the coordinate is in *Distance Per
            Cell* *units* (in other words 0:distance in cells, 1:
            distance in pixels)'.

         | 

         | 

         .. container:: template_stub

            | ** This article is a stub, you can help the RPTools Wiki
              project by contributing content to expand this article.**
            | ** This article needs:** *example needed*

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getLastPath&oldid=5981"

