.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=json.indexOf
   |version=1.3b53
   |description=
   Returns the index of the first occurrence of a value in the [[JSON_Array|JSON Array]]. If the value does not exist in the [[JSON_Array|JSON Array]] then {{code|-1}} is returned. All [[JSON_Array|JSON Array]] indexes start at {{code|0}}.

   |usage=
   <source lang="mtmacro" line>
   json.indexOf(array, value)
   </source>
   <source lang="mtmacro" line>
   json.indexOf(array, value, start)
   </source>
   '''Parameters'''
   {{param|array|The [[JSON_Array|JSON Array]] to search.}}
   {{param|value|The value to find the index of in the [[JSON_Array|JSON Array]].}}
   {{param|start|The index to start searching from, if not specified it defaults to {{code|0}}.}}

   |examples=
   Find the index of the first occurrence of {{code|1}}:
   <source lang="mtmacro" line>
   [r: json.indexOf("[1,2,3,1,1,3]", 1)]
   </source>
   Returns: {{code|0}}

   Find the index of the first occurrence of {{code|1}}, starting at index {{code|1}}:
   <source lang="mtmacro" line>
   [r: json.count("[1,2,3,1,1,3]", 1, 1)]
   </source>
   Returns: {{code|3}}

   Find the index of the first occurrence of {{code|2}}, starting at index {{code|2}}:
   <source lang="mtmacro" line>
   [r: json.count("[1,2,3,1,1,3]", 2, 2)]
   </source>
   Returns: {{code|-1}}

   |also=
   {{func|json.count}}

   }}

`Category:JSON Function <Category:JSON_Function>`__
