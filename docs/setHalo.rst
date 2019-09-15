.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setHalo
   |version=1.3b49
   |description=
   Sets the [[Halo|Halo]] color of a [[Token|Token]].

   |usage=
   <source lang="mtmacro" line>
   setHalo(color)
   </source>
   <source lang="mtmacro" line>
   setHalo(color, id)
   </source>
   '''Parameters'''
   {{param|color|The color to set the [[Halo|Halo]] to, valid values are:
   ** {{code|"Black"}}
   ** {{code|"Green"}}
   ** {{code|"Yellow"}}
   ** {{code|"Orange"}}
   ** {{code|"Red"}}
   ** {{code|"Cyan"}}
   ** {{code|"Magenta"}}
   ** {{code|"White"}}
   ** A hexadecimal color value in the format {{code|"#RRGGBB"}}
   ** {{code|"None"}} }}
   {{param|id|The token {{code|id}} of the token that has its [[Halo|Halo]] set by this function. {{TrustedParameter}} }}

   |examples=
   To remove the [[Halo|Halo]] from the [[Current_Token|Current Token]].
   <source lang="mtmacro" line>
   [h: setHalo("None")]
   </source>

   To set the [[Halo|Halo]] for the [[Current_Token|Current Token]] to red.
   <source lang="mtmacro" line>
   [h: setHalo("Red")]
   </source>

   To set the [[Halo|Halo]] from the [[Current_Token|Current Token]] to a custom color
   <source lang="mtmacro" line>
   [h: setHalo("#33AAFF")]
   </source>

   |also=
   [[Halo|Halo]],
   [[getHalo|getHalo()]]

   |changes=
   {{change|1.3b51|Added {{code|id}} parameter option.}}
   }}

`Category:Token Function <Category:Token_Function>`__
