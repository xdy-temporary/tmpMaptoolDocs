.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=isTrusted
   |version=1.3b48
   |description=
   Returns 1 if this is running as a [[Macros:TrustedMacros|trusted macro]] or 0 if it is not.

   |usage=
   <source lang="mtmacro" line>
   isTrusted()
   </source>

   |example=
   <source lang="mtmacro" line>
   [r, if(isTrusted()): "I can run the trusted functions! yay!"]
   </source>
   }}

`Category:Metamacro Function <Category:Metamacro_Function>`__
`Category:Permission Function <Category:Permission_Function>`__
