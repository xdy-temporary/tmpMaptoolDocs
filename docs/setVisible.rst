.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub|Examples of usage.}}

.. raw:: mediawiki

   {{MacroFunction
   |name=setVisible
   |trusted=true
   |version=1.3b40
   |description=
   Sets the [[Visible_to_Players|Visible to Players]] flag on a [[Token|Token]] if the value passed in is non-zero({{true}}), otherwise resets it to {{false}}. The [[Visible_to_Players|Visible to Players]] flag has two meanings, on a normal [[Token|Token]] players will only be able to see the [[Token|Token]] if it is set (when all other things like [[Fog_of_War|Fog of War]] etc are taken into account). If it is a [[Library_Token|Library Token]] then it determines if players can call [[:Category:Macro|:Category:Macro]]s using the [[Macros:Branching_and_Looping|[macro(...): ...]]] roll option.

   |usage=
   <source lang="mtmacro" line>
   setVisible(visible)
   </source>
   <source lang="mtmacro" line>
   setVisible(visible, id)
   </source>
   '''Parameters'''
   {{param|visible|The state of visibility, {{true}} or {{false}}.}}
   {{param|id|The token {{code|id}} of the token which has its player visibility set, defaults to the [[Current_Token|Current Token]].}}

   |also=
   [[getVisible|getVisible()]]

   |changes=
   {{change|1.3b51|Added {{code|id}} parameter option.}}

   }}

`Category:Token Function <Category:Token_Function>`__
