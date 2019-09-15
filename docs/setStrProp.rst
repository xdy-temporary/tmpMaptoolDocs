.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setStrProp
   |version=1.3b42
   |description=
   Returns a [[String_Property_List|String Property List]] with the key set to the value passed in. 

   |usage=
   <source lang="mtmacro" line>
   setStrProp(propList, key, value)
   </source>
   '''Parameters'''
   {{param|propList|The [[String_Property_List|String Property List]] affected by this function.}}
   {{param|key|The key in the specified [[String_Property_List|String Property List]] that will have its value set.}}
   {{param|value|The value that the specified key will be set to.}} 

   |examples=
   Add a new key to an existing [[String_Property_List|String Property List]]:
   <source lang="mtmacro" line>
   [h: weapon = "name=longsword; damage=1d8; maxdamage=8"]
   [h: weapon = setStrProp(weapon, "value", 10)]
   [r: weapon]
   </source>
   Returns {{code|"name{{=}}longsword ; damage{{=}}

1d8 ; maxdamage{{=}}8 ; value{{=}}10 ; "}}

Change the value of a key in an existing `String Property
List <String_Property_List>`__:

.. code:: mtmacro
   :number-lines:

   [h: weapon = "name=longsword; damage=1d8; maxdamage=8"]
   [h: weapon = setStrProp(weapon, "damage", "1d6")]
   [r: weapon]

Returns longsword ; damage{{=}}1d6 ; maxdamage{{=}}8 ; "}}

\|also= }}

`Category:String Property List
Function <Category:String_Property_List_Function>`__
