.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub}}

.. raw:: mediawiki

   {{MacroFunction
   |name=getRawProperty
   |version=1.3b51
   |description=
   Gets the unevaluated value of a [[Token:token_property|token property]], returns {{code|""}} if the property is empty. This will not return the property's default value.

   |usage=
   <source lang="mtmacro" line>
   getRawProperty(prop)
   getRawProperty(prop, id)
   getRawProperty(prop, id, mapname)
   </source>
   '''Parameters'''
   {{param|prop|The name of the property to return.}}
   {{param|id|The id of the token to retrieve the property from.}}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}

   |changes=
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}
   }}

`Category:Property Function <Category:Property_Function>`__
`Category:Token Function <Category:Token_Function>`__
