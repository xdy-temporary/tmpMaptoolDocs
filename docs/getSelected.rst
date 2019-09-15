.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getSelected
   |version=1.3b48
   |description=
   Returns a list containing the ids of the selected [[Token:token|token]]s on the current [[Map:map|map]]. The type of the value returned depends on the delimiter parameter. 
   * If the delimiter is not specified then a [[Macros:string_list|string list]] is returned with the default value of {{code|","}} is used.
   * If the delimiter {{code|json}} then a [[JSON_Array|JSON Array]] is returned.
   * Otherwise a [[Macros:string_list|string list]] is returned with the delimiter passed in.
    

   |usage= 
   <source lang="mtmacro" line>
   getSelected()
   getSelected(delim)
   </source>
   {{code|delim}} is the delimiter used to separate the values in the  [[Macros:string_list|string list]] which defaults to {{code|","}} if not specified.

   |example=
   To display the ids of all of the selected [[Token:token|token]]s on the current [[Map:map|map]] use.
   <source lang="mtmacro" line>
   [h: ids = getSelected()]
   [foreach(id, ids, "<br>"): id]
   </source>

   |changes=
   {{change|1.3b49|Added {{code|json}} delimiter option.}}
   {{change|1.3b51|No longer a trusted function.}}

   }}

`Category:Token Function <Category:Token_Function>`__
