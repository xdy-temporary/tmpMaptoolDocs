==============================
onChangeSelection - MapToolDoc
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

   .. rubric:: onChangeSelection
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

         This event is triggered whenever the user selects a token.

         As a frame-based event, a frame containing the event code has
         to be opened.

         .. rubric:: Set up
            :name: set-up

         Create a frame that has this special html tag in it:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: html4strict source-html4strict

               .. code-block:: none

                  <link rel='onChangeSelection' type='macro' href='macroLink'>

         Replace ``macroLink`` by an actual macroLinkText-call to a
         macro of your choice (the returned value of
         `macroLinkText() </rptools/wiki/macroLinkText>`__). A common
         practice is to call the frame opening macro itself to actualize
         the content.

         .. rubric:: See Also
            :name: see-also

         `Forms tutorial#Events </rptools/wiki/Forms_tutorial#Events>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=onChangeSelection&oldid=5872"

