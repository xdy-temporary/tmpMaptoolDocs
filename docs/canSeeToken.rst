.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=canSeeToken
   |version=1.3b77
   |description=
   Returns a json array of the points visible on the target token from the source token as an enumerated list.  Default source is [[Current_Token|Current Token]].  The enumerated list will contain zero to five of the following values:
   *TOP_RIGHT
   *BOTTOM_RIGHT
   *TOP_LEFT
   *BOTTOM_LEFT
   *CENTER

   When a token is not visible, an empty json array is returned: '[]'

   |usage=
   <source lang="mtmacro">
   canSeeToken(target)
   canSeeToken(target, source)
   canSeeToken(target, source, mapname)
   </source>
   '''Parameters'''
   {{param|target|Either the token ID or name of the target token.}}
   {{param|source|Either the token ID or name of the source, i.e. viewing token.}}
   {{param|mapname|The name of the map to find the two tokens.  Defaults to the current map.}}

   |example=

   <source lang="mtmacro" line>
   <!-- Dragon token partially hidden by VBL from current token. -->
   [r: canSeeToken("Dragon")]
   <!-- Troll token completely hidden from Elf token. -->
   [r: canSeeToken("Troll","Elf")]
   <!-- Troll token visible to Hero token. -->
   [r: canSeeToken("Troll","Token")]

   </source>
   Returns:
   <source lang="javascript">
   ["TOP_LEFT", "TOP_RIGHT", "CENTER"]
   []
   ["TOP_LEFT", "BOTTOM_LEFT", "TOP_RIGHT", "BOTTOM_RIGHT", "CENTER"]
   </source>

   |also=


   |changes=
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}
   }}

`Category:Sight Function <Category:Sight_Function>`__ `Category:Token
Function <Category:Token_Function>`__
