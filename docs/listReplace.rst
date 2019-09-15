.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=listReplace
   |version=1.3b42
   |description=
   Replaces the element at the specified index of a [[String_List|String List]] with a new value. If a delimiter is not specified then the default value of {{code|","}} is used. The index for lists starts at {{code|0}}.

   |usage=
   <source lang="mtmacro" line>
   listReplace(list, index, value)
   </source>
   <source lang="mtmacro" line>
   listReplace(list, index, value, delim)
   </source>

   |examples=
   '''Simple example:'''
   <source lang="mtmacro" line>
   [r: listReplace("This, isnt, a , test", 1, "is")]
   </source>
   Returns {{code|This, is, a, Test}}

   '''Example using a [[String_List|String List]] with a non-default delimiter:'''
   <source lang="mtmacro" line>
   [r: listReplace("This: isnt: a: test", 1, "is", ":")] 
   </source>
   Returns {{code|This: is: a: test}}

   '''Example using a [[String_List|String List]] stored in a variable:'''
   <source lang="mtmacro" line>
   [h: ListVar = "This, is, a, great, test"]
   [h: ListVar = listReplace(ListVar, 3, "silly")]
   [r: ListVar]
   </source>
   Returns: {{code|This, is, a, silly, test}}
   }}

`Category:String List Function <Category:String_List_Function>`__
