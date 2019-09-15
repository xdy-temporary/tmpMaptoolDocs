.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=indexValueStrProp
   |version=1.3b42
   |description=
   Returns the value from the specified [[Macros:string_property_list|string property list]] at the specified index. The index for the [[Macros:string_property_list|string property list]] starts at 0.

   |usage=
   <source lang="mtmacro" line>
   indexValueStrProp(prop, index)
   </source>

   |example=
   <source lang="mtmacro" line>
   [indexValueStrProp("a=blah; b=doh; c=meh", 1)]
   </source>
   Returns "doh".
   }}

`Category:String Property List
Function <Category:String_Property_List_Function>`__
