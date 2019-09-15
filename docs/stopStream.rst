=======================
stopStream - MapToolDoc
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

   .. rubric:: stopStream
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

         .. rubric:: stopStream() Function
            :name: stopstream-function

         .. container:: template_version

            • **Introduced in version 1.5.5**

         .. container:: template_description

            Stop an audio stream currently playing.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     stopStream()

               #. .. code-block:: none

                     stopStream(uri)

               #. .. code-block:: none

                     stopStream(uri, remove)

               #. .. code-block:: none

                     stopStream(uri, remove, fadeout)

         **Parameter**

         -  ``uri`` - The uri/url of the stream to stop. If set to "*",
            all audio streams are stopped. Defaults to "*".
         -  ``remove`` - If set to 1, the audio file is removed from
            memory. Defaults to 1.
         -  ``fadeout`` - Optional fadeout (in seconds) before stopping
            the stream. If set to 0, stop as soon as possible. Defaults
            to 0.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=stopStream&oldid=7601"

