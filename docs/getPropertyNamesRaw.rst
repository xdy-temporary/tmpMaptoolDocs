.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction |name=getPropertyNamesRaw |version=1.3b64
   |description=
   Returns a [[String_List|String List]] or [[JSON_Array|JSON Array]] containing the names of the [[Token_Property|Token Properties]] on a [[Token|Token]]. The type of the value returned depends on the delimiter parameter.

   The difference between this function and [[getPropertyNames|getPropertyNames()]] is that [[getPropertyNames|getPropertyNames()]] returns all the property names in lower case (see [http://forums.rptools.net/viewtopic.php?f=1&t=12563&p=148937&hilit=getPropertyNamesRaw#p148937 this forum thread] to get the reason why it was created). 

   |usage=
   <source lang="mtmacro" line>
   getPropertyNamesRaw()
   getPropertyNamesRaw(delim)
   getPropertyNamesRaw(delim, id)
   getPropertyNamesRaw(delim, id, mapname)
   </source>
   '''Parameters'''
   {{param|delim|The delimiter used to separate the values in the [[String_List|String List]], defaults to {{code|","}}. Returns a [[JSON_Array|JSON Array]] if set to {{code|"json"}}. }}
   {{param|id|The token {{code|id}} of the token which has its property names returned, defaults to the [[Current_Token|Current Token]]. {{TrustedParameter}} }}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}

   |example=
   To display the names of all of the [[Token_Property|properties]] on the current [[Token:token|token]] use.
   <source lang="mtmacro" line>
   [h: names = getPropertyNamesRaw()]
   [foreach(name, names, "<br>"): name]
   </source>

   |changes=
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}
   }}

Notes
=====

When token properties are created during campaign, they are persistent
in the MapTool campaign, regardless of whether they are editable in the
*Edit Token* window. In other words, even though a property is removed
from the campaign properties, it remains available in the MapTool code.
`getPropertyNamesRaw() <getPropertyNamesRaw>`__ will return *all* token
properties that exist or have ever existed in the particular campaign,
even if users cannot directly edit those properties (*i.e.*, they do not
appear in the token's properties when you double click on a token). To
get only properties that are currently visible and editable, use
`getAllPropertyNames() <getAllPropertyNames>`__.

`Category:Token Function <Category:Token_Function>`__ `Category:Property
Function <Category:Property_Function>`__
