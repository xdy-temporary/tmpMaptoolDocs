.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getMatchingLibProperties
   |version=1.3b54
   |description=
   Returns a [[String_List|String List]] or [[JSON_Array|JSON Array]] with names of the [[Token_Property|Token Properties]] on a specific [[Library_Token|Library Token]] that match the given pattern.

   |usage=
   <source lang="mtmacro" line>
   getMatchingLibProperties(pattern)
   </source>
   <source lang="mtmacro" line>
   getMatchingLibProperties(pattern, lib)
   </source>
   <source lang="mtmacro" line>
   getMatchingLibProperties(pattern, lib, delim)
   </source>
   '''Parameters'''
   {{param|pattern|A regular expression(regex) that represents the pattern the properties should match.}}
   {{param|lib|The name of the [[Library_Token|Library Token]] that is checked for properties that match, defaults to the [[Library_Token|Library Token]] the macro is running on.}}
   {{param|delim|The delimiter used in the [[String_List|String List]] that is returned, defaults to {{code|","}}.  Returns a [[JSON_Array|JSON Array]] if {{code|"json"}} is specified.}}


   |examples=
   Assuming that you have a [[Library_Token|Library Token]] that contained a list of all the items and their detail in your campaign stored as [[Token|Token]] properties names with the following format {{code|''Type'':''Item Name''}} (for example {{code|Weapon:Longsword)}}, you could use the following code to loop through 
   all the weapons.
   <source lang="mtmacro" line>
   [foreach(item, getMatchingLibProperties("Weapon:.*", "Lib:Items")): {
       <!-- Do something really exciting here -->
   }]
   </source>

   Or the following to loop through all the armor
   <source lang="mtmacro" line>
   [foreach(item, getMatchingLibProperties("Armor:.*", "Lib:Items")): {
       <!-- Do something really exciting here -->
   }]
   </source>

   Or even all the armor and all the shields.
   <source lang="mtmacro" line>
   [foreach(item, getMatchingLibProperties("(Armor|Shield):.*", "Lib:Items")): {
       <!-- Do something really exciting here -->
   }]
   </source>


   |also=
   {{func|getMatchingProperties}} {{func|getLibPropertyNames}}

   }}

`Category:Property Function <Category:Property_Function>`__
`Category:Token Library Function <Category:Token_Library_Function>`__
