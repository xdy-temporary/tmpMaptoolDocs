.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub|Documentation on how the decor(suffixed/unsuffixed) parameter works.}}

.. raw:: mediawiki

   {{MacroFunction
   |name=varsFromStrProp
   |version=1.3b42
   |description=
   Creates variables from a [[Macros:string_property_list|string property list]] with the values assigned to variables with the names of the keys in the [[Macros:string_property_list|string property list]]. The function returns the number of variables that were created.

   |usage=
   <source lang="mtmacro">
   varsFromStrProp(props)
   varsFromStrProp(props, decor)
   </source>
   '''Parameters'''
   {{param|props|A string property list.}}
   {{param|decor|Either SUFFIXED, which appends an underscore to the variable name, or UNSUFFIXED (default) which leaves the name as is.}}

   |examples=
   <source lang="mtmacro" line>
   [h: varsFromStrProp("a=blah; b=doh; c=meh")]
   [r: a] [r: b] [r: c]
   </source>
   '''Returns''' 
   <source lang="mtmacro">
   blah doh meh
   </source>
   |also=
   {{func|strPropFromVars}}
   |changes=
   {{change|1.3b49|Added {{code|suffixed}} or {{code|unsuffixed}} parameter option.}}

   }}

`Category:String Property List
Function <Category:String_Property_List_Function>`__
