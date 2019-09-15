.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getVisibleTokens
   |version=1.3b49
   |description=
   Returns a [[Macros:string_list|string list]] or [[JSON_Array|JSON Array]] of [[Glossary#Token_Id|token id]]s for the [[Token:token|token]]s that are ''visible'' to the player. The type of the value returned depends on the delimiter parameter.
   * If the delimiter is not specified then a [[Macros:string_list|string list]] is returned with the default value of {{code|","}} is used.
   * If the delimiter {{code|json}} then a [[JSON_Array|JSON Array]] is returned.
   * Otherwise a [[Macros:string_list|string list]] is returned with the delimiter passed in.
    
   <!-- The above 'nbsp' is needed to close the DIV -->
   |usage=
   <source lang="mtmacro" line>
   getVisibleTokens()
   </source>
   <source lang="mtmacro" line>
   getVisibleTokens(delim)
   </source>

   |examples=
   <source lang="mtmacro" line>
   [h: tokens = getVisibleTokens()]
   </source>


   <source lang="mtmacro" line>
   [h: tokens = getVisibleTokens("json")]
   </source>

   |changes=
   {{change|1.3b51|No longer a trusted function.}}

   }}

`Category:Find Function <Category:Find_Function>`__ `Category:Token
Function <Category:Token_Function>`__
