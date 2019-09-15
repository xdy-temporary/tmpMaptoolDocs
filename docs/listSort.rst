.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub}}

.. raw:: mediawiki

   {{MacroFunction
   |name=listSort
   |description=
   Returns a sorted list.

   |usage=
   <source lang="mtmacro" line>
   [listSort(list, sortType)]
   </source>
   The sortType determines the type of sort to use.
   If sortType is "A", normal alphabetic sorting is used, and "Monster11" comes before "Monster3". (Default behavior)
   If sortType is "N", the first number in each entry is effectively padded to 4 digits, so that "Monster3" comes before "Monster11".
   The sortType can have a second character of "+" or "-" to specify an ascending or descending sort.

   |example=
   <source lang="mtmacro" line>
   [h: UnsortedList = "Monster11,Monster3,Monster12,Monster66,Monster87,Monster71"]
   [h: SortedList = listSort(UnsortedList,'N')]

   Unsorted list: [r: UnsortedList]<br>
   Sorted list: [r: SortedList]
   </source>

   Returns:
     Unsorted list: Monster11,Monster3,Monster12,Monster66,Monster87,Monster71
     Sorted list: Monster3, Monster11, Monster12, Monster66, Monster71, Monster87

   }}

`Category:String List Function <Category:String_List_Function>`__
