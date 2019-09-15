.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=sendToBack
   |version=1.3b48
   |description=
   Adjust the z-order (or draw order) of the [[Token|Token]] so that it is drawn before all other [[Token|Token]]s on the same [[Map_Layer|Map Layer]], this has the effect of making the Token appear to be in back of the other [[Token|Token]]s as it will be obscured by other [[Token|Token]]s on the same [[Map_Layer|Map Layer]] in the same location.

   |usage=
   <source lang="mtmacro" line>
   sendToBack()
   sendToBack(id)
   sendToBack(id, mapname)
   </source>
   '''Parameter'''
   {{param|id|The token {{code|id}} or name of the token that has its z-order changed, defaults to the [[Current_Token|Current Token]]. {{TrustedParameter}} }}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}


   |examples=
   Sends the [[Current_Token|Current Token]] to the lowest z-order.
   <source lang="mtmacro" line>
   [h: sendToBack()]
   </source>

   Sends all of the selected tokens to the lowest z-order.
   <source lang="mtmacro" line>
   [h: tokens = getSelected()]
   [h, foreach(id, tokens, ""), code:
   {
       [h: sendToBack(id)]
   }]
   </source>

   |also=
   {{func|bringToFront}}

   |changes=
   {{change|1.3b51|Added {{code|id}} parameter option.}}
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}

   }}

`Category:Token Function <Category:Token_Function>`__
