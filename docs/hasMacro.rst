.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=hasMacro
   |version=1.3b48
   |description=
   Returns {{true}} if a [[Macro_Button|macro button]] with the specified label exists on the [[Current_Token|Current Token]].

   |usage=
   <source lang="mtmacro" line>
   hasMacro(label)
   </source>
   <source lang="mtmacro" line>
   hasMacro(label, id)
   </source>
   '''Parameters'''
   {{param|label|The label of the macro to check for.}}
   {{param|id|The token {{code|id}} of the token that the function is executed on. {{TrustedParameter}} }}

   |changes=
   {{change|1.3b51|Added optional token {{code|id}} parameter.}}
   }}

`Category:Metamacro Function <Category:Metamacro_Function>`__
