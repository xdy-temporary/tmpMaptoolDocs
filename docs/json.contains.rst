.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=json.contains
   |version=1.3b49
   |description=
   Returns {{true}} if the [[JSON_Object|JSON Object]] contains the specified key, or if the [[JSON_Array|JSON Array]] contains the specified value.

   |usage=
   <source lang="mtmacro" line>
   json.contains(object, key)
   </source>
   <source lang="mtmacro" line>
   json.contains(array, value)
   </source>
   '''Parameters'''
   {{param|object|The [[JSON_Object|JSON Object]] to test for the key.}}
   {{param|key|The key to check the object for.}}
   {{param|array|The [[JSON_Array|JSON Array]] to test for the value.}}
   {{param|value|The value to check the array for.}}

   |examples=
   Check if the [[JSON_Object|JSON Object]] {{code|a}} contains the key {{code|"b"}}:
   <source lang="mtmacro" line>
   [h:a=json.fromStrProp("a=1;b=44;c=12")]
   [json.contains(a,"b")]
   </source>
   Returns {{true}}

   Check if the [[JSON_Object|JSON Object]] {{code|a}} contains the key {{code|"z"}}:
   <source lang="mtmacro" line>
   [h:a=json.fromStrProp("a=1;b=44;c=12")]
   [json.contains(a,"z")]
   </source>
   Returns {{false}}

   Check if the [[JSON_Array|JSON Array]] {{code|a}} contains the value {{code|"b"}}:
   <source lang="mtmacro" line>
   [h:a=json.fromList("1,b,3,d")]
   [json.contains(a,"b")]
   </source>
   Returns {{true}}

   |also=
   {{func|json.type}}

   |changes=
   {{change|1.3b51|Added ability for function to work with [[JSON_Array|JSON Array]]s.}}

   }}

`Category:JSON Function <Category:JSON_Function>`__
