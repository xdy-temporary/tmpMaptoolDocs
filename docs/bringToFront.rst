.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=bringToFront
   |version=1.3b48
   |description=
   Adjust the z order (or draw order) of the [[Token|Token]] so that is is drawn after all other [[Token|Token]]s on the same [[Map_Layer|Map Layer]], this has the effect of making the [[Token|Token]] appear to be in front of the other [[Token|Token]]s as it will obscure other [[Token|Token]]s on the same [[Map_Layer|Map Layer]] in the same location.

   |usage=
   <source lang="mtmacro" line>
   bringToFront()
   bringToFront(id)
   bringToFront(id, mapname)
   </source>
   '''Parameter'''
   {{param|id|The token {{code|id}} or name of the token to effect, defaults to the [[Current_Token|Current Token]]. {{TrustedParameter}} }}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}


   |examples=
   <source lang="mtmacro" line>
   <!-- Make sure that we are visible above all other tokens on the same layer -->
   [h: bringToFront()]
   </source>


   <source lang="mtmacro" line>
   <!-- The Hero of the piece should always stand out -->
   [h: bringToFront("Hero")]
   </source>

   |also=
   [[sendToBack|sendToBack()]]

   |changes=
   {{change|1.3b51|Added {{code|id}} parameter option.}}
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}
   }}

`Category:Token Function <Category:Token_Function>`__
