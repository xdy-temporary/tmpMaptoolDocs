.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub|Examples of usage.}}

.. raw:: mediawiki

   {{MacroFunction
   |name=setLabel
   |version=1.3b48
   |description=
   Sets the [[Token_Label|Token Label]] of a specific [[Token|Token]]. 

   |usage=
   <source lang="mtmacro" line>
   setLabel(label)
   </source>
   <source lang="mtmacro" line>
   setLabel(label, id)
   </source>
   '''Parameters'''
   {{param|label|The string that the [[Token_Label|Token Label]] is set to.}}
   {{param|id|The token {{code|id}} of the token that has its label set, defaults to the [[Current_Token|Current Token]]. {{TrustedParameter}} }}

   |also=
   {{func|getLabel}}

   |changes=
   {{change|1.3b51|Add {{code|id}} parameter option.}}

   }}

`Category:Token Function <Category:Token_Function>`__
