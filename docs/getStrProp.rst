.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getStrProp
   |version=1.3b42
   |description=
   Returns the value associated with a key from the specified [[Macros:string_property_list|string property list]]. 

   |usage=
   <source lang="mtmacro" line>
   getStrProp(propList, key)
   getStrProp(propList, key, default)
   getStrProp(propList, key, default, delim)
   </source>
   '''Parameters'''
   {{param|proplist|String property list to extract data from.}} 
   {{param|key|Key within string to extract. This cannot include a space.}}
   {{param|default|Value returned if the key is not found.}}
   {{param|delim|Delimiter between fields (default is ";").}}

   |example=
   To get the name from a weapon [[Macros:string_property_list|string property list]]
   <source lang="mtmacro" line>
   [h: weapon = "name=longsword; damage=1d8; maxdamage=8"]
   Name of Weapon: [r: getStrProp(weapon, "name")]
   </source>
   Returns {{code|Name of Weapon: longsword}}.

   To get the minimum damage from a weapon [[Macros:string_property_list|string property list]] with a default value should the key not exist
   <source lang="mtmacro" line>
   [h: weapon = "name=longsword; damage=1d8; maxdamage=8"]
   Minimum damage of Weapon: [r: getStrProp(weapon, "mindamage", 1)]
   </source>
   Returns {{code|Minimum damage of Weapon: 1}}.

   To get the damage from a weapon [[Macros:string_property_list|string property list]] where the field delimiter is a colon.  The default is '''1d3''' (note that a default value must be provided in order to specify the delimiter).
   <source lang="mtmacro" line>
   [h: weapon = "name=longsword: damage=1d8: maxdamage=8"]
   Damage of Weapon: [r: getStrProp(weapon, "damage", "1d3", ":")]
   </source>
   Returns {{code|Damage of Weapon: 1d8}}.

   |changes=
   {{change|1.3b43|Added the optional {{code|error}} parameter.}}

   }}

`Category:String Property List
Function <Category:String_Property_List_Function>`__
