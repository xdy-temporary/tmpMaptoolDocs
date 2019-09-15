.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setProperty
   |version=1.3b48
   |description=
   Sets the value of a [[Token_Property|Token Property]] on the [[Current_Token|Current Token]] (unless trusted, in which case a Token ID can be supplied to indicate which token is to be affected).

   Note that if there is not already an existing property by the name listed in the macro, setProperty will create a new Token Property with that name.  Any created Property will not be visible in the Properties tab of the Edit Token window but can still be used like normal.  It's value can be retrieved with the getProperty command.

   |usage=
   <source lang="mtmacro" line>
   setProperty(property, value)
   setProperty(property, value, id)
   setProperty(property, value, id, mapname)
   </source>
   '''Parameters'''
   {{param|property|A string containing the name of the property that has its value set.}}
   {{param|value|The value that the property is set to.}}
   {{param|id|The token {{code|id}} of the token which has its property set, defaults to the [[Current_Token|Current Token]]. {{TrustedParameter}} }}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}


   |examples=
   Sets a property named {{code|Health}} to the value of {{code|10}} on the [[Current_Token|Current Token]].
   <source lang="mtmacro" line>
   [h: setProperty("Health", 10)]
   </source>

   Sets a property named {{code|Fatigue}} to the value of {{code|5}} on the selected token.
   <source lang="mtmacro" line>
   [h: setProperty("Fatigue", 5, getSelected())]
   </source>

   Sets a property named {{code|Strength}} to the value of {{code|20}} on the selected token using variables.
   <source lang="mtmacro" line>
   [h: Property = "Strength"]
   [h: Value = 20]
   [h: ID = getSelected()]
   [h: setProperty(Property, Value, ID)]
   </source>

   |also=
   [[getProperty|getProperty()]], 
   [[resetProperty|resetProperty()]], 
   [[isPropertyEmpty|isPropertyEmpty()]]

   |changes=
   {{change|1.3b51|Added {{code|id}} parameter option.}}
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}

   }}

`Category:Property Function <Category:Property_Function>`__
`Category:Token Function <Category:Token_Function>`__
