.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=json.intersection
   |version=1.3b53
   |description=
   Returns a [[JSON_Array|JSON Array]] with the intersection of all of the [[JSON_Object|JSON Object]] keys or [[JSON_Array|JSON Array]] values.  A value or key only appears in the output if it exists in all input arrays or objects.

   This function is useful for removing Token IDs from a saved list which have been deleted from the map by eliminating them using this function, the saved array and {{func|getTokens}}.

   |usage=
   <source lang="mtmacro" line>
   json.intersection(array, array, ...)
   </source>
   <source lang="mtmacro" line>
   json.intersection(object, object, ...)
   </source>
   '''Parameters'''
   {{param|array|A [[JSON_Array|JSON Array]] used in the intersection.}}
   {{param|object|A [[JSON_Object|JSON Object]] used in the intersection.}}

   |examples=
   <source lang="mtmacro" line>
     [h: array1 = json.append("",1,2,3,4)]
     [h: array2 = json.append("",3,4,5,6)]
     [r: json.intersection(array1,array2)]
   </source>

   Returns:
    "[3,4]"



   <source lang="mtmacro" line>
     [h: arrayOfSelectedNames = getSelectedNames("json")]
     [h: arrayOfNamesOnMap = getTokenNames("json")]
     [r: json.intersection(arrayOfSelectedNames,arrayOfNamesOnMap)]
   </source>

   Input:
    arrayOfSelectedNames = ["Alexander","Josh"]
    arrayOfNamesOnMap = ["Kevin","Josh","Alexander"]

   Returns:
    ["Alexander","Josh"]

   |also=
   {{func|json.difference}}

   }}

`Category:JSON Function <Category:JSON_Function>`__
