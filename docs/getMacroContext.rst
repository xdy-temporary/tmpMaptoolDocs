.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getMacroContext
   |version=1.4.0.2
   |description=
   Returns information about the source, name, index of the button of the macro being executed as a JSON object.

   |usage=
   <source lang="mtmacro" line>
   getMacroContext()
   </source>

   |example=
   <source lang="mtmacro" line>
   [r: getMacroContext()]
   </source>

   Returns for example:
    {"stackSize":1,"trusted":true,"name":"aMacroName","buttonIndex":127,"source":"lib:Test"}

   }}

`Category:Metamacro Function <Category:Metamacro_Function>`__
