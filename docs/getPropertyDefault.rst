.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getPropertyDefault
   |version=1.3b48
   |description=
   Returns the [[Campaign:property_default_value|default value]] of a [[Token:property|token property]] for the [[Current_Token|Current Token]]. If the [[Campaign:property_default_value|default value]] contains nothing then an empty string ({{code|""}}) is returned. 

   |usage=
   <source lang="mtmacro" line>
   getPropertyDefault(name)
   getPropertyDefault(name, propType)
   </source>

   '''Parameter'''
   {{param|name|The name of the property to get the default value of.}}
   {{param|propType|The token type to get the property from. Defaults to the token type of the [[Current_Token|Current Token]].}}


   }}

`Category:Token Function <Category:Token_Function>`__ `Category:Property
Function <Category:Property_Function>`__
