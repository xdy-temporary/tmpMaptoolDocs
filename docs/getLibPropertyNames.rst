.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name= getLibPropertyNames
   |version=1.5.0
   |description=
   Returns a [[String_List|String List]] or [[JSON_Array|JSON Array]] containing the names of the [[Token_Property|Token Properties]] on a [[Library_Token|Library Token]]. The type of the value returned depends on the delimiter parameter.

   {{note|
   When token properties are created during campaign, they are persistent in the MapTool campaign, regardless of whether they are editable in the Edit Token window. In other words, even though a property is removed from the campaign properties, it remains available to macros.  '''getLibPropertyNames''' will return ''all'' token properties that exist or have ever existed in the particular campaign, even if users cannot directly edit those properties (''i.e.'', they do not appear in the token's properties when you double click on a token). To get only properties that are currently visible and editable, use {{func|getAllPropertyNames}}.
   }}

   |usage=
   <source lang="mtmacro" line>
   getLibPropertyNames()
   </source>
   <source lang="mtmacro" line>
   getLibPropertyNames(delim)
   </source>
   <source lang="mtmacro" line>
   getLibPropertyNames(id, delim)
   </source>
   '''Parameters'''
   {{param|delim|The delimiter used to separate the values in the [[String_List|String List]], defaults to {{code|","}}. Returns a [[JSON_Array|JSON Array]] if set to {{code|"json"}}. }}
   {{param|id|The token {{code|id}} of the token which has its property names returned, defaults to the [[Current_Token|Current Token]].  This parameter may be {{code|*}} or {{code|this}} to indicate the current Lib token that this macro is executing on. {{TrustedParameter}} }}

   |example=
   <source lang="mtmacro" line>
   [h: names = getLibPropertyNames()]
   [foreach(name, names, "<br>"): name]
   </source>

   <source lang="mtmacro" line>
   [h: names = getLibPropertyNames("Lib:some_lib_token")]
   [foreach(name, names, "<br>"): name]
   </source>

   |changes=

   }}

`Category:Token Function <Category:Token_Function>`__ `Category:Token
Library Function <Category:Token_Library_Function>`__ `Category:Property
Function <Category:Property_Function>`__
