.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub|Expanded examples of usage.}}

.. raw:: mediawiki

   {{MacroFunction
   |name=getMacroButtonIndex
   |version=1.3b50
   |description=
   Returns the index of the [[Token|Token]] macro button that was clicked on. The macro button must have the auto-execute check box selected. If the macro is not running from a [[Token|Token]] macro button then {{code|-1}} is returned.

   |usage=
   <source lang="mtmacro" line>
   getMacroButtonIndex()
   </source>

   |example=
   <source lang="mtmacro" line>
   [h: ind = getMacroButtonIndex()]
   </source>
   If the macro is not run from an auto-execute macro button on a [[Token|Token]], {{code|ind}} is set to {{code|-1}}. Otherwise {{code|ind}} is set to a non-negative number which is the index of the button.

   |also=
   {{func|getMacroIndexes}}

   }}

`Category:Metamacro Function <Category:Metamacro_Function>`__
