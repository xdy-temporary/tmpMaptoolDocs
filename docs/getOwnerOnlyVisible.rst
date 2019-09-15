.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub|Examples of usage.}}

.. raw:: mediawiki

   {{MacroFunction
   |name=getOwnerOnlyVisible
   |version=1.3b74
   |description=
   Returns {{true}} if the [[Token:Visible_to_Owners_Only|Visible to Owners Only]] flag is set on a [[Token|Token]] otherwise returns {{false}}. 

   |usage=
   <source lang="mtmacro" line>
   getOwnerOnlyVisible()
   </source>
   <source lang="mtmacro" line>
   getOwnerOnlyVisible(id)
   </source>
   '''Parameter'''
   {{param|id|The token {{code|id}} of token that has its player visibility checked, defaults to the [[Current_Token|Current Token]]. {{TrustedParameter}} }}

   |also=
   [[getVisible|getVisible()]], [[setOwnerOnlyVisible|setOwnerOnlyVisible()]]

   }}

`Category:Token Function <Category:Token_Function>`__
