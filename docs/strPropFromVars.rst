.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=strPropFromVars
   |description=
   Creates a property string from the names and values of the variables listed in the varList string.

   |usage=
   <source lang="mtmacro">
   [h: strPropFromVars(varList) ]
   [h: strPropFromVars(varList, varStyle) ]
   [h: strPropFromVars(varList, varStyle, delim) ]
   </source>
   '''Parameters'''
   {{param|varList|A list of variable names, separated by ",".}}
   {{param|varStyle|Either "SUFFIXED" or "UNSUFFIXED". The "SUFFIXED" option will look for variables with underscores appended to the given names. Defaults to "UNSUFFIXED".}}
   {{param|delim|The delimiter for the return string. Defaults to ";". }}

   |examples=
   <source lang="mtmacro" line>
   [H: props = "a=3 ; b=bob ; c=cow ; "]
   [H: varsFromStrProp(props, "SUFFIXED")] <!-- creates variables a_, b_, c_ -->
   [strPropFromVars("c,a,b", "SUFFIXED")]
   </source>
   '''Returns'''
   <source lang="mtmacro">
   "c=cow ; a=3 ; b=bob"
   </source>

   |also=
   {{func|varsFromStrProp}}
   |changes=
   {{change|1.5.4|Made {{code|varStyle}} optional.}}

   }}

`Category:String Property List
Function <Category:String_Property_List_Function>`__
