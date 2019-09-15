.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getSpeechNames
   |version=1.3b48
   |description=
   Returns a list containing the [[Token:speech|speech]] names of the [[Current_Token|Current Token]]. The type of the value returned depends on the delimiter parameter. 
   * If the delimiter is not specified then a [[Macros:string_list|string list]] is returned with the default value of {{code|","}} is used.
   * If the delimiter {{code|json}} then a [[JSON_Array|JSON Array]] is returned.
   * Otherwise a [[Macros:string_list|string list]] is returned with the delimiter passed in.
    

   |usage=
   <source lang="mtmacro" line>
   getSpeechNames()
   getSpeechNames(delim)
   </source>
   {{code|delim}} is the delimiter used to separate the values in the  [[Macros:string_list|string list]] which defaults to {{code|","}} if not specified.

   |example=
   To display the names of all of the [[Token:speech|speech]] values for the [[Current_Token|Current Token]] use.
   <source lang="mtmacro" line>
   [h: names = getSpeech()]
   [foreach(name, names, "<br>"): name]
   </source>

   |changes=
   * '''1.3b49''' - Added {{code|json}} delimiter option.
   }}

`Category:Token Function <Category:Token_Function>`__ `Category:Speech
Function <Category:Speech_Function>`__
