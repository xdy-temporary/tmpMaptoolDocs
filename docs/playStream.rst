=======================
playStream - MapToolDoc
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

   .. rubric:: playStream
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

         .. rubric:: playStream() Function
            :name: playstream-function

         .. container:: template_version

            • **Introduced in version 1.5.5**

         .. container:: template_description

            Play an audio stream for the current player, from an online
            source or from a local file. Can be disabled in the sound
            preferences. Multiple files can be played at the same time.
            If attempting to play the same audio file twice, the
            previous streaming is stopped.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     playStream(uri)

               #. .. code-block:: none

                     playStream(uri, cycleCount)

               #. .. code-block:: none

                     playStream(uri, cycleCount, volume)

               #. .. code-block:: none

                     playStream(uri, cycleCount, volume, start)

               #. .. code:: de2

                     playStream(uri, cycleCount, volume, start, stop)

         **Parameter**

         -  ``uri`` - The uri/url of the file, for example
            http://www.mywebsite/mysong.mp3 or file:///C:/mysong.mp3
         -  ``cycleCount`` - The number of times the audio should play.
            If set to 0, the file is cached but not played; if set to
            -1, the file is played continuously. Defaults to 1.
         -  ``volume`` - The volume the audio is to be played at. Can
            range from 0 to 1. Defaults to 1.
         -  ``start`` - The time offset in seconds where audio should
            start playing, or restart from when repeating. Defaults to
            0.
         -  ``stop`` - The time offset where audio should stop playing
            or restart when repeating. Defaults to the end of the audio.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=playStream&oldid=7599"

