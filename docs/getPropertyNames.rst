.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getPropertyNames
   |version=1.3b48
   |description=
   Returns a [[String_List|String List]] or [[JSON_Array|JSON Array]] containing the names of the [[Token_Property|Token Properties]] for the [[Current_Token|Current Token]]. The type of the value returned depends on the delimiter parameter. All names returned will be in lower case. Use {{func|getPropertyNamesRaw}} to get the names as they are shown in [[Introduction_to_Properties|Campaign Properties]].

   {{note|When a token is added to a campaign it inherits the currently defined properties of the current campaign.  These properties are persistent in the token even if the properties are subsequently removed from the campaign.  Properties that have been removed from the campaign are no longer editable via the Edit Token dialog but they are still present on the token and may be read and set with {{func|getProperty}} and {{func|setProperty}} respectively. To get ''all'' properties defined on a token, including those removed from the campaign, use ''getPropertyNames()''.  To see only the currently defined properties for the campaign, use {{func|getAllPropertyNames}}.}}

   |usage=
   <source lang="mtmacro" line>
   getPropertyNames()
   getPropertyNames(delim)
   getPropertyNames(delim, id)
   getPropertyNames(delim, id, mapname)
   </source>
   '''Parameters'''
   {{param|delim|The delimiter used to separate the values in the [[String_List|String List]], defaults to {{code|","}}. Returns a [[JSON_Array|JSON Array]] if set to {{code|"json"}}. }}
   {{param|id|The token {{code|id}} of the token which has its property names returned, defaults to the [[Current_Token|Current Token]]. {{TrustedParameter}} }}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}

   |example=
   To display the names of all of the [[Token:property|properties]] on the current [[Token:token|token]] use.
   <source lang="mtmacro" line>
   [h: names = getPropertyNames()]
   [foreach(name, names, "<br>"): name]
   </source>
   |changes=
   {{change|1.3b49|Added {{code|json}} delimiter option.}}
   {{change|1.3b51|Added {{code|id}} parameter option.}}
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}
   }}

`Category:Token Function <Category:Token_Function>`__ `Category:Property
Function <Category:Property_Function>`__
