.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub|Examples of usage.}}

.. raw:: mediawiki

   {{MacroFunction
   |name=setPropertyType
   |version=1.3b48
   |description=
   Sets the [[Property_Type|Property Type]] of a [[Token|Token]].

   |usage=
   <source lang="mtmacro" line>
   setPropertyType(type)
   setPropertyType(type, id)
   setPropertyType(type, id, mapname)
   </source>
   ''Parameters'''
   {{param|type|The property type to set on the token.}}
   {{param|id|The token {{code|id}} of the token which has its property type set, defaults to the [[Current_Token|Current Token]]. {{TrustedParameter}} }}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}


   |also=
   [[getPropertyType|getPropertyType()]]

   |changes=
   {{change|1.3b51|Added {{code|id}} parameter option.}}
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}

   }}

`Category:Property Function <Category:Property_Function>`__
`Category:Token Function <Category:Token_Function>`__
