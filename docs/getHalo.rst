.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getHalo
   |version=1.3b49
   |description=Gets the color value of a token's [[Halo|Halo]]. The value returned is a string that represents the hexadecimal value of the color of the [[Halo|Halo]] in the format {{code|"#RRGGBB"}} or {{code|"None"}} if the token has no [[Halo|Halo]].

   |usage=
   <source lang="mtmacro" line>
   getHalo()
   </source>
   <source lang="mtmacro" line>
   getHalo(id)
   </source>
   '''Parameter'''
   {{param|id|The token {{code|id}} of the token which has its halo color returned, defaults to the [[Current_Token|Current Token]]. {{TrustedParameter}} }}

   |example=
   The following example will display the text "Halo Color Text" in the color of the [[Current_Token|Current Token]]'s [[Halo|Halo]].
   <source lang="mtmacro" line>
   <span style="color:[r: getHalo()]">Halo Color Text</span>
   </source>

   |also=
   [[Halo|Halo]],
   [[setHalo|setHalo()]]

   |changes=
   {{change|1.3b51|Added {{code|id}} parameter option.}}
   }}

`Category:Token Function <Category:Token_Function>`__
