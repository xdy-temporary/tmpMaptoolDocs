.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getPCNames
   |trusted=true
   |version=1.3b48
   |description=Returns a list containing the names of the [[Token:PC_token|PC token]]s on the current [[Map:map|map]]. The type of the value returned depends on the delimiter parameter. 
   * If the delimiter is not specified then a [[Macros:string_list|string list]] is returned with the default value of {{code|","}} is used.
   * If the delimiter {{code|json}} then a [[JSON_Array|JSON Array]] is returned.
   * Otherwise a [[Macros:string_list|string list]] is returned with the delimiter passed in.
    

   |usage=
   <source lang="mtmacro" line>
   getPCNames()
   getPCNames(delim)
   </source>
   {{code|delim}} is the delimiter used to separate the values in the  [[Macros:string_list|string list]] which defaults to {{code|","}} if not specified.

   |example=
   To display the names of all of the [[Token:PC_token|PC token]]s on the current [[Map:map|map]] use.
   <source lang="mtmacro" line>
   [h: names = getPCNames()]
   [foreach(name, names, "<br>"): name]
   </source>

   |changes=
   * '''1.3b49''' - Added {{code|json}} delimiter option.

   |also=
   {{roll|foreach}}
   }}

`Category:Token Function <Category:Token_Function>`__
