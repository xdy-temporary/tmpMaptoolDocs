.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=editStream
   |version=1.5.5
   |description=
   Edit an audio stream currently playing.

   |usage=
   <source lang="mtmacro" line>
   editStream(uri, cycleCount)
   editStream(uri, cycleCount, volume)
   editStream(uri, cycleCount, volume, start)
   editStream(uri, cycleCount, volume, start, stop)
   </source>

   '''Parameter'''
   {{param|uri|The uri/url of the stream to edit. If set to "*", all audio streams are edited.}}
   {{param|cycleCount|The number of times the audio should play. If set to 0, the file is cached but not played; if set to -1, the file is played continuously. If set to a blank string "", the property is not changed. Defaults to "".}}
   {{param|volume|The volume the audio is to be played at. Can range from 0 to 1. If set to "", the property is not changed. Defaults to "".}}
   {{param|start|The time offset in seconds where audio should start playing, or restart from when repeating. If set to "", the property is not changed. Defaults to "".}}
   {{param|stop|The time offset where audio should stop playing or restart when repeating. If set to "", the property is not changed. Defaults to "".}}

   }}

`Category:Audio Function <Category:Audio_Function>`__
