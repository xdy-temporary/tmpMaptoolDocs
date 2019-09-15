.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub|Examples of usage.}}

.. raw:: mediawiki

   {{MacroFunction
   |name=hasProperty
   |version=1.3b48
   |description=
   Returns {{true}} if the [[Token_Property|Token Property]] with the specified name exists on a [[Token|Token]]. The function will return true if the token possesses the specified property, even if that property is not defined in the token's current property type. 

   |usage=
   <source lang="mtmacro" line>
   hasProperty(name)
   hasProperty(name, id)
   hasProperty(name, id, mapname)
   </source>
   '''Parameters'''
   {{param|name|The name of the [[Token_Property|Token Property]] which is checked for on the token.}}
   {{param|id|The token {{code|id}} of the token which is checked for the [[Token_Property|Token Property]], defaults to the [[Current_Token|Current Token]]. {{TrustedParameter}} }}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}

   |changes=
   {{change|1.3b51|Added {{code|id}} parameter option.}}
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}
   }}

`Category:Token Function <Category:Token_Function>`__ `Category:Property
Function <Category:Property_Function>`__
