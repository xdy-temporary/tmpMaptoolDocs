.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getMatchingProperties
   |version=1.3b54
   |description=
   Returns a [[String_List|String List]] or [[JSON_Array|JSON Array]] with names of the [[Token_Property|Token Properties]] on a specific [[Token|Token]] that match the given pattern.

   |usage=
   <source lang="mtmacro" line>
   getMatchingProperties(pattern)
   getMatchingProperties(pattern, delim)
   getMatchingProperties(pattern, delim, id)
   getMatchingProperties(pattern, delim, id, mapname)
   </source>
   '''Parameters'''
   {{param|pattern|A regular expression(regex) that represents the pattern the properties should match.}}
   {{param|delim|The delimiter used in the [[String_List|String List]] that is returned, defaults to {{code|","}}.  Returns a [[JSON_Array|JSON Array]] if {{code|"json"}} is specified.}}
   {{param|id|The token {{code|id}} of the token that is checked for properties that match the given pattern, defaults to the [[Current_Token|Current Token]]. {{TrustedParameter}} }}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}

   |examples=
   Say you wanted to keep an inventory list for the [[Token|Token]] you could prefix all of your inventory properties with {{code|Inv:''Category'':}}. For example {{code|Inv:Weapon:Longsword}}.

   Then to loop through all of the inventory properties you could use 
   <source lang="mtmacro" line>
   [foreach(item, getMatchingProperties("Inv:.*")): {
       <!-- Do something really exciting here -->
   }]
   </source>

   Or the following to loop through all the weapons
   <source lang="mtmacro" line>
   [foreach(item, getMatchingProperties("Inv:Weapon:.*")): {
       <!-- Do something really exciting here -->
   }]
   </source>

   Or even all the armor and all the shields.
   <source lang="mtmacro" line>
   [foreach(item, getMatchingProperties("Inv:(Armor|Shield):.*")): {
       <!-- Do something really exciting here -->
   }]
   </source>


   |also=
   {{func|getMatchingLibProperties}} {{func|getPropertyNames}}

   |changes=
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}

   }}

`Category:Property Function <Category:Property_Function>`__
`Category:Token Function <Category:Token_Function>`__
