.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=json.count
   |version=1.3b53
   |description=
   Returns the number of occurrences of a value in a [[JSON_Array|JSON Array]]. If the value does
   not occur in the [[JSON_Array|JSON Array]] then {{code|-1}} is returned. The index for the [[JSON_Array|JSON Array]]
   starts at {{code|0}}.

   |usage=
   <source lang="mtmacro" line>
   json.count(array, value)]
   </source>
   <source lang="mtmacro" line>
   json.count(array, value, start)]
   </source>
   '''Parameters'''
   {{param|array|The [[JSON_Array|JSON Array]] to search.}}
   {{param|value|The value to count the occurrences of.}}
   {{param|start|The index to start searching from, if not specified it defaults to {{code|0}}.}}

   |example=
   Find the number of occurrences of {{code|1}}:
   <source lang="mtmacro" line>
   [r: json.count("[1,2,3,1,1,3]", 1)]
   </source>
   Returns {{code|3}}

   Find the number of occurrences of {{code|1}}, starting at index {{code|1}}:
   <source lang="mtmacro" line>
   [r: json.count("[1,2,3,1,1,3]", 1, 1)]
   </source>
   Returns {{code|2}}

   |also=
   {{func|json.contains}}

   }}

`Category:JSON Function <Category:JSON_Function>`__
