.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=json.get
   |version=1.3b49
   |description=
   Returns the value in a [[JSON_Array|JSON Array]] at the specified index, returns a slice of a [[JSON_Array|JSON Array]] from the specified indexes, or returns the value from [[JSON_Object|JSON Object]] for the specified key.

   |usage=
   <source lang="mtmacro" line>
   json.get(array, index)
   </source>
   <source lang="mtmacro" line>
   json.get(array, start, end)
   </source>
   <source lang="mtmacro" line>
   json.get(object, key, key, ...)
   </source>
   '''Parameters'''
   {{param|array|The [[JSON_Array|JSON Array]] to retrieve the element from.}}
   {{param|index|The numerical index of the element you want returned.}}
   {{param|start|The starting index of the element you wish the slice to begin at.}}
   {{param|end|The ending index of the element you wish the slice to end at.}}
   {{param|object|The [[JSON_Object|JSON Object]] to retrieve the element from.}}
   {{param|key|The name of a field that should be returned. This parameter can exist more than once, if it does then a [[JSON_Object|JSON Object]] is returned with all the specified elements.}}

   When extracting slices: Negative numbers can be used as the offsets from the end of the array, {{code|-1}} is the last element in the array, {{code|-2}} is the second to last, and so on.  If the {{code|end}} index is smaller than the {{code|start}} index then the array slice is returned in reverse.  This does not work for single indices, so if you want to retrieve a single index, say the last one in an array, you do that like this: json.get(array, -1,-1). This way you take a ''slice'' of 1 index. To get the last element you thus need to do: json.get(json.get(array, -1,-1),0) as you get a ''slice'' and you want an ''element''.

   |examples=
   <source lang="mtmacro" line>
     a) [h: jo = json.fromStrProp("a=1; b=44; cat=meow")] [r: json.get(jo, "b")] <br>
     b) [h: jo = json.fromStrProp("a=1; b=44; cat=meow")] [r: json.get(jo, "XX")] <br>
     c) [h: jo = json.fromStrProp("a=1; b=44; cat=meow")] [r: json.get(jo, "cat", "a")] <br>
     d) [h: jo = json.fromStrProp("a=1; b=44; cat=meow")] [r: json.get(jo, "b", "XX")] <br>
     e) [h: ja = json.fromList("1,44,meow")] [r: json.get(ja, 1)] <br>
     f) [h: ja = json.fromList("1,44,meow")] [r: json.get(ja, 2)] <br>
     g) [h: ja = json.fromList("1,44,meow")] [r: json.get(ja, 1, 2)] <br>
     h) [h: ja = json.fromList("1,44,meow")] [r: json.get(ja, 0, -1)] <br>
     i) [h: ja = json.fromList("1,44,meow")] [r: json.get(ja, 2, 0)] <br> 
     j) [h: ja = json.fromList("1,44,meow")] [r: json.get(ja, -1, 0)] <br>
     ERROR a) [h: ja = json.fromList("1,44,meow")] [r: json.get(ja, -1)] <br>
     ERROR b) [h: ja = json.fromList("1,44,meow")] [r: json.get(ja, 3)] <br>
     
   </source>

   Returns
     a) 44 -- a value
     b)    -- empty string "", as XX does not exist
     c) {"cat":"meow","a":1} -- a JSON object
     d) {"b":44,"XX":""} -- a JSON object
     e) 44 -- a value
     f) meow -- a value
     g) [1,44,"meow"] -- an array slice of 0..2  
     h) ["meow",44] -- an array slice from 2..1 
     i) [1,44,"meow"] -- an array slice from 0..end
     j) ["meow",44] -- an array slice from end..1

     ERROR a) -- java.lang.ArrayIndexOutOfBoundsException, can't use negatives with a single index param (works OK with slices). 
     ERROR a) -- java.lang.ArrayIndexOutOfBoundsException, the last valid index is 2
   |changes=
   {{change|1.3b51|Added ability to return [[JSON_Array|JSON Array]] slices.}}
   {{change|1.3b51|Added ability to return [[JSON_Object|JSON Object]]s of select fields from other [[JSON_Object|JSON Object]]s.}}

   }}

`Category:JSON Function <Category:JSON_Function>`__
