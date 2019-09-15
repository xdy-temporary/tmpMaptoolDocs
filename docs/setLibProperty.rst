.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setLibProperty
   |version=1.3b48
   |description=
   Sets the [[Token:token_property|Token Property]] on a [[Token:library_token|Library Token]]. if the name of the [[Token:library_token|Library Token]] is not specified then the [[Token:token_property|Token Property]] is set on the [[Token:library_token|Library Token]] that the macro is running from.

   |usage=
   <source lang="mtmacro" line>
   setLibProperty(name, value)
   setLibProperty(name, value, libName)
   </source>

   |examples=
   Set a property on the [[Token:library_token|Library Token]] that the macro is running from.
   <source lang="mtmacro" line>
   [h: setLibProperty("defaultStrength", 10)]
   </source>

   Set a property on a specifig [[Token:library_token|Library Token]].
   <source lang="mtmacro" line>
   [h: setLibProperty("defaultStrength", 10, "Lib:Character")]
   </source>

   Known Bug: note that using setLibProperty during onCampaignLoad and not being on the map where the lib resides, will result in a duplicate of that lib on the current map!

   }}

`Category:Property Function <Category:Property_Function>`__
`Category:Token Library Function <Category:Token_Library_Function>`__
