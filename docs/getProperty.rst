.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub|Examples of usage.}}

.. raw:: mediawiki

   {{MacroFunction
   |name=getProperty
   |version=1.3b48
   |description=
   Returns the value of a [[Token_Property|Token Property]] on a [[Token|Token]].  
   If the [[Token_Property|Token Property]] is empty ({{code|NULL}}) or not defined, an empty string ({{code|""}}) is returned. 
   |usage=
   <source lang="mtmacro" line>
   getProperty(property)
   getProperty(property, id)
   getProperty(property, id, mapname)
   </source>

   '''Parameter'''
   {{param|property|The property that has its value returned. For referencing the literal name of the property (for instance, if you wish to get the property ''Constitution'' configured in Campaign Properties), enclose the property name in quotes. If using a variable whose ''value ''is the name of the property, do not enclose the variable name in quotes.}}
   {{param|id|The token {{code|id}} or name of the token that has its property value returned, defaults to the [[Current_Token|Current Token]]. {{TrustedParameter}} }}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}


   |example=
   Getting a property using the literal property name.
   <source lang="mtmacro" line>
   The value of property 'Strength' is [r: getProperty("Strength")].
   </source>

   This will output the following if '''Strength''' has the value '''18''':
    The value of property 'Strength' is 18.

   Getting a property using a variable.
   <source lang="mtmacro" line>
   [h:desiredProperty = "Constitution"]
   The value of property 'Constitution' is [r: getProperty(desiredProperty)].
   </source>
   This will output the following if '''Constitution''' has the value '''12''':
     The value of property 'Constitution' is 12.
   |also=
   [[setProperty|setProperty()]], 
   [[resetProperty|resetProperty()]], 
   [[isPropertyEmpty|isPropertyEmpty()]]

   |changes=
   {{change|1.3b51|Added {{code|id}} parameter option.}}
   {{change|1.3b51|Changed to return the default value if the property has no value.}}
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}

   }}

`Category:Token Function <Category:Token_Function>`__ `Category:Property
Function <Category:Property_Function>`__
