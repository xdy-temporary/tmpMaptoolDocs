=======================
editStream - MapToolDoc
=======================

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

   .. rubric:: editStream
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

         .. rubric:: editStream() Function
            :name: editstream-function

         .. container:: template_version

            • **Introduced in version 1.5.5**

         .. container:: template_description

            Edit an audio stream currently playing.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     editStream(uri, cycleCount)

               #. .. code-block:: none

                     editStream(uri, cycleCount, volume)

               #. .. code-block:: none

                     editStream(uri, cycleCount, volume, start)

               #. .. code-block:: none

                     editStream(uri, cycleCount, volume, start, stop)

         **Parameter**

         -  ``uri`` - The uri/url of the stream to edit. If set to "*",
            all audio streams are edited.
         -  ``cycleCount`` - The number of times the audio should play.
            If set to 0, the file is cached but not played; if set to
            -1, the file is played continuously. If set to a blank
            string "", the property is not changed. Defaults to "".
         -  ``volume`` - The volume the audio is to be played at. Can
            range from 0 to 1. If set to "", the property is not
            changed. Defaults to "".
         -  ``start`` - The time offset in seconds where audio should
            start playing, or restart from when repeating. If set to "",
            the property is not changed. Defaults to "".
         -  ``stop`` - The time offset where audio should stop playing
            or restart when repeating. If set to "", the property is not
            changed. Defaults to "".

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=editStream&oldid=7598"

