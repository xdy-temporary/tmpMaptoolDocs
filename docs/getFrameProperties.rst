.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub}}

.. raw:: mediawiki

   {{MacroFunction
   |name=getFrameProperties
   |version=1.5.4
   |description=
   Returns a json object holding the properties associated with a given frame. The properties are {{code|width}}, {{code|height}}, {{code|temporary}}, {{code|title}}, and {{code|value}}.

   |usage=
   <source lang="mtmacro" line>
   getFrameProperties(name)
   </source>

   '''Parameters'''
   {{param|name|The name of the frame.}}

   |example=
   Opening up a frame 
   <source lang="mtmacro" line>
   [frame("Frame Test", "width=300; height=200; temporary=0; title=A new title; value=data of relevance"): {test}]
   </source>

   Getting the properties of the frame:

   <source lang="mtmacro" line>
   [getFrameProperties("Frame Test")]
   </source>

   The output will be:
   <source lang="mtmacro" line>
    {"width":300,"height":200,"temporary":0,"title":"A new title","value":"data of relevance"}
   </source>

   }}

`Category:Frame Function <Category:Frame_Function>`__
