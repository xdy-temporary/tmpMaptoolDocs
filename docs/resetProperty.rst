.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub|Examples of usage.}}

.. raw:: mediawiki

   {{MacroFunction
   |name=resetProperty
   |version=1.3b48
   |description=
   Resets the specified [[Token_Property|Token Property]] on a specific [[Token|Token]] so that it is empty and will return the default value when queried (if it has one). 

   |usage=
   <source lang="mtmacro" line>
   resetProperty(property)
   resetProperty(property, id)
   resetProperty(property, id, mapname)
   </source>
   '''Parameters'''
   {{param|property|The name of the property to reset.}}
   {{param|id|The token {{code|id}} of the token which has its property reset, defaults to the [[Current_Token|Current Token]]. {{TrustedParameter}} }}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}

   |also=
   [[isPropertyEmpty|isPropertyEmpty()]], 
   [[setProperty|setProperty()]], 
   [[getProperty|getProperty()]]

   |changes=
   {{change|1.3b51|Added {{code|id}} parameter option.}}
   {{change|1.3b68|[[Token_Property|Token Property]] is now deleted from [[Token|Token]]}}
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}

   }}

`Category:Property Function <Category:Property_Function>`__
`Category:Token Function <Category:Token_Function>`__
