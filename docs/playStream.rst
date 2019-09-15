.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=playStream
   |version=1.5.5
   |description=
   Play an audio stream for the current player, from an online source or from a local file. Can be disabled in the sound preferences. Multiple files can be played at the same time. If attempting to play the same audio file twice, the previous streaming is stopped.

   |usage=
   <source lang="mtmacro" line>
   playStream(uri)
   playStream(uri, cycleCount)
   playStream(uri, cycleCount, volume)
   playStream(uri, cycleCount, volume, start)
   playStream(uri, cycleCount, volume, start, stop)
   </source>

   '''Parameter'''
   {{param|uri|The uri/url of the file, for example http://www.mywebsite/mysong.mp3 or file:///C:/mysong.mp3}}
   {{param|cycleCount|The number of times the audio should play. If set to 0, the file is cached but not played; if set to -1, the file is played continuously. Defaults to 1.}}
   {{param|volume|The volume the audio is to be played at. Can range from 0 to 1. Defaults to 1.}}
   {{param|start|The time offset in seconds where audio should start playing, or restart from when repeating. Defaults to 0.}}
   {{param|stop|The time offset where audio should stop playing or restart when repeating. Defaults to the end of the audio.}}

   }}

`Category:Audio Function <Category:Audio_Function>`__
