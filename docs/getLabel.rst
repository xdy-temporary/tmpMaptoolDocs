.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub|Examples of usage.}}

.. raw:: mediawiki

   {{MacroFunction
   |name=getLabel
   |version=1.3b48
   |description=
   Returns the [[Token_Label|Token Label]] for a specific [[Token|Token]].

   |usage=
   <source lang="mtmacro" line>
   getLabel()
   </source>
   <source lang="mtmacro" line>
   getLabel(id)
   </source>
   '''Parameter'''
   {{param|id|The token {{code|id}} of the token that has its [[Token_Label|Token Label]] returned, defaults to the [[Current_Token|Current Token]]. {{TrustedParameter}} }}

   |also=
   {{func|setLabel}}

   |changes=
   {{change|1.3b51|Added {{code|id}} parameter option.}}

   }}

`Category:Token Function <Category:Token_Function>`__
