.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub|Examples of usage.}}

.. raw:: mediawiki

   {{MacroFunction
   |name=getVisible
   |version=1.3b40
   |description=
   Returns {{true}} if the [[Token:visible_to_players|visible to players]] flag is set on a [[Token|Token]] otherwise returns {{false}}. The [[Token:visible_to_players|visible to players]] flag has two meanings, on a normal [[Token|Token]] players will only be able to see the [[Token|Token]] if it is set (when all other things like [[Map:Fog_of_War|Fog of War]] etc are taken into account). If it is a [[Library_Token|Library Token]] then it determines if players can call Macros using {{roll|macro}}.

   |usage=
   <source lang="mtmacro" line>
   getVisible()
   </source>
   <source lang="mtmacro" line>
   getVisible(id)
   </source>
   '''Parameter'''
   {{param|id|The token {{code|id}} of token that has its player visibility checked, defaults to the [[Current_Token|Current Token]]. {{TrustedParameter}} }}

   |also=
   [[setVisible|setVisible()]]

   |changes=
   {{change|1.3b51|No longer a trusted function, added {{code|id}} parameter option.}}

   }}

`Category:Token Function <Category:Token_Function>`__
