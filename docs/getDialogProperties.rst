.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub}}

.. raw:: mediawiki

   {{MacroFunction
   |name=getDialogProperties
   |version=1.5.4
   |description=
   Returns a json object holding the properties associated with a given dialog. The properties are {{code|width}}, {{code|height}}, {{code|temporary}}, {{code|title}}, and {{code|value}}.

   |usage=
   <source lang="mtmacro" line>
   getDialogProperties(name)
   </source>

   '''Parameters'''
   {{param|name|The name of the dialog.}}

   |example=
   Opening up a dialog
   <source lang="mtmacro" line>
   [dialog("Dialog Test", "width=300; height=200; temporary=0; title=A new title; value=data of relevance"): {test}]
   </source>

   Getting the properties of the dialog:

   <source lang="mtmacro" line>
   [getDialogProperties("Dialog Test")]
   </source>

   The output will be:
   <source lang="mtmacro" line>
    {"width":300,"height":200,"temporary":0,"title":"A new title","value":"data of relevance"}
   </source>

   }}

`Category:Dialog Function <Category:Dialog_Function>`__
