.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=deleteStrProp
   |version=1.3b42
   |description=Returns a copy of the [[Macros:string_property_list|string property list]] with the specified key removed.

   |usage=
   <source lang="mtmacro" line>
   deleteStrProp(props, key)
   </source>

   |example=
   <source lang="mtmacro" line>
   [r: deleteStrProp("a=blah; b=doh; c=meh", "a")]
   </source>
   Returns "b=doh; c=meh".
   }}

`Category:String Property List
Function <Category:String_Property_List_Function>`__
