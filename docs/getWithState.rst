.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getWithState
   |trusted=true
   |version=1.3b48
   |description=
   Gets a list containing the ids of all the [[Token:token|token]]s on the current [[Map:map|map]] that have the specified [[Token:state|token state]] set. The type of the value returned depends on the delimiter parameter. 
   * If the delimiter is not specified then a [[Macros:string_list|string list]] is returned with the default value of {{code|","}} is used.
   * If the delimiter {{code|json}} then a [[JSON_Array|JSON Array]] is returned.
   * Otherwise a [[Macros:string_list|string list]] is returned with the delimiter passed in.
    

   |usage=
   <source lang="mtmacro" line>
   getWithState(state)
   getWithState(state, delim)
   </source>

   If {{code|delim}} is specified then it is used to separate the values in the list, if it is not specified then it defaults to {{code|","}}.

   |example=
   You can use the following code to print out the ids of all of the [[Token:token|token]]s on the current [[Map:map|map]] with the "Dead" [[Token:state|token state]] set.
   <source lang="mtmacro" line>
   [h: ids = getWithState("Dead")]
   [foreach(id, ids, "<br>"): id]
   </source>

   |changes=
   * '''1.3b49''' - Added {{code|json}} delimiter option.
   }}

`Category:Find Function <Category:Find_Function>`__ `Category:State
Function <Category:State_Function>`__ `Category:Token
Function <Category:Token_Function>`__
