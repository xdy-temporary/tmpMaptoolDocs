.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=stopStream
   |version=1.5.5
   |description=
   Stop an audio stream currently playing.

   |usage=
   <source lang="mtmacro" line>
   stopStream()
   stopStream(uri)
   stopStream(uri, remove)
   stopStream(uri, remove, fadeout)
   </source>

   '''Parameter'''
   {{param|uri|The uri/url of the stream to stop. If set to "*", all audio streams are stopped. Defaults to "*".}}
   {{param|remove|If set to 1, the audio file is removed from memory. Defaults to 1.}}
   {{param|fadeout|Optional fadeout (in seconds) before stopping the stream. If set to 0, stop as soon as possible. Defaults to 0.}}

   }}

`Category:Audio Function <Category:Audio_Function>`__
