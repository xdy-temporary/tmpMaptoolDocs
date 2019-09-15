.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=switchToken
   |trusted=true
   |version=1.3b48
   |description=
   Changes the [[Current_Token|Current Token]] for the remainder of the Macro.
   <p>In practice, "the remainder of the Macro" is the same as the variable scope. Thus, if a macro is running as a user defined function (see {{func|defineFunction}}  ) with a new scope, switchToken will only apply until the end of the current macro. Once control passes back to the calling macro, the [[Current_Token|Current Token]] reverts back to what it was before the external macro was called ( as a function ).
   If a {{func|defineFunction}} does not create a new variable scope for the called macro, then effects of switchToken persist when control passes back to the calling macro.</p>

   |usage=
   <source lang="mtmacro" line>
   switchToken(tokenId)
   </source>
   }}

`Category:Token Function <Category:Token_Function>`__
