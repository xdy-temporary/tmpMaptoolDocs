.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=json.fromList
   |version=1.3b49
   |description=
   Returns a [[JSON_Array|JSON Array]] from a [[String_List|String List]]. 

   |usage=
   <source lang="mtmacro" line>
   json.fromList(strList)
   </source>
   <source lang="mtmacro" line>
   json.fromList(strList, delim)
   </source>
   '''Parameters'''
   {{param|strList|The [[String_List|String List]] that is converted to a [[JSON_Array|JSON Array]].}}
   {{param|delim|The delimiter used in the [[String_List|String List]], defaults to {{code|","}}.}}

   |example=
   <source lang="mtmacro" line>
   [r:json.fromList("a,1,g,4")]
   </source>
   Returns {{code|["a",1,"g",4]}}

   |also=
   {{func|json.toList}}

   }}

`Category:JSON Function <Category:JSON_Function>`__
