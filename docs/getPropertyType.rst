.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub|Examples of usage.}}

.. raw:: mediawiki

   {{MacroFunction
   |name=getPropertyType
   |version=1.3b48
   |description=
   Returns the [[Property_Type|Property Type]] of a [[Token|Token]].

   |usage=
   <source lang="mtmacro" line>
   getPropertyType()
   getPropertyType(id)
   getPropertyType(id, mapname)
   </source>
   '''Parameter'''
   {{param|id|The token {{code|id}} of the token which has its [[Property_Type|Property Type]] returned, defaults to the [[Current_Token|Current Token]]. {{TrustedParameter}} }}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}


   |also=
   [[setPropertyType|setPropertyType()]]

   |changes=
   {{change|1.3b51|Added {{code|id}} parameter option.}}
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}

   }}

`Category:Token Function <Category:Token_Function>`__ `Category:Property
Function <Category:Property_Function>`__
