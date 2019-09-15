================================
getStreamProperties - MapToolDoc
================================

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

   .. rubric:: getStreamProperties
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

         .. rubric:: getStreamProperties() Function
            :name: getstreamproperties-function

         .. container:: template_version

            • **Introduced in version 1.5.5**

         .. container:: template_description

            Get the properties of an audio stream currently loaded in
            memory.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getStreamProperties()

               #. .. code-block:: none

                     getStreamProperties(uri)

         **Parameter**

         -  ``uri`` - The uri/url of the stream to edit. If set to "*",
            a `JSON Array <JSON_Array>`__ containing the
            properties of all streams is returned. Defaults to "*".

         Properties returned: uri, cycleCount, volume, startTime,
         stopTime, currentTime, totalTime, bufferTime, currentCount,
         status.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getStreamProperties&oldid=7604"

