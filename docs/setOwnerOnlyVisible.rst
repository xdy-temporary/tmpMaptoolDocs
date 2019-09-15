.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub|Examples of usage.}}

.. raw:: mediawiki

   {{MacroFunction
   |name=setOwnerOnlyVisible
   |trusted=true
   |version=1.3b74
   |description=
   Sets the [[Visible_to_Owners_Only|Visible to Owners Only]] flag on a [[Token|Token]] if the value passed in is non-zero({{true}}), otherwise resets it to {{false}}. 

   |usage=
   <source lang="mtmacro" line>
   setOwnerOnlyVisible(visible)
   </source>
   <source lang="mtmacro" line>
   setOwnerOnlyVisible(visible, id)
   </source>
   '''Parameters'''
   {{param|visible|The state of owner only visibility, {{true}} or {{false}}.}}
   {{param|id|The token {{code|id}} of the token which has its owner only visibility set, defaults to the [[Current_Token|Current Token]].}}

   |also=
   [[setVisible|setVisible()]], [[getOwnerOnlyVisible|getOwnerOnlyVisible()]]

   }}

`Category:Token Function <Category:Token_Function>`__
