.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub|Examples using the new functionality.}}

.. raw:: mediawiki

   {{MacroFunction
   |name=isPropertyEmpty
   |version=1.3b48
   |description=
   Returns {{true}} if the [[Token_Property|Token Property]] for a specific [[Token|Token]] is empty. A [[Token_Property|Token Property]] is considered empty if it is {{code|NULL}}; if an empty string ({{code|""}}) has been assigned to it, it is not considered empty.

   '''Note:''' If the token type sets a default value, this function will still see the property as empty. Try using [[json.isEmpty|json.isEmpty()]].

   |usage=
   <source lang="mtmacro" line>
   isPropertyEmpty(property)
   isPropertyEmpty(property, id)
   isPropertyEmpty(property, id, mapname)
   </source>
   '''Parameters'''
   {{param|property|The name of the property that has its value checked.}}
   {{param|id|The token {{code|id}} of the token that has its value checked, defaults to the [[Current_Token|Current Token]]. {{TrustedParameter}} }}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}


   |example=
   <source lang="mtmacro" line>
   [r, if(isPropertyEmpty("propertyName")): propertyName = someDefaultValue]
   </source>

   |also=
   [[resetProperty|resetProperty()]], 
   [[getProperty|getProperty()]], 
   [[setProperty|setProperty()]],
   [[json.isEmpty|json.isEmpty()]]
   |changes=
   {{change|1.3b51|Added {{code|id}} parameter option.}}
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}

   }}

`Category:Token Function <Category:Token_Function>`__ `Category:Property
Function <Category:Property_Function>`__
