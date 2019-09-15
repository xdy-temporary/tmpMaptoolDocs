.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getStreamProperties
   |version=1.5.5
   |description=
   Get the properties of an audio stream currently loaded in memory.

   |usage=
   <source lang="mtmacro" line>
   getStreamProperties()
   getStreamProperties(uri)
   </source>

   '''Parameter'''
   {{param|uri|The uri/url of the stream to edit. If set to "*", a [[JSON_Array|JSON Array]] containing the properties of all streams is returned. Defaults to "*".}}

   Properties returned: uri, cycleCount, volume, startTime, stopTime, currentTime, totalTime, bufferTime,  currentCount, status.

   }}

`Category:Audio Function <Category:Audio_Function>`__
