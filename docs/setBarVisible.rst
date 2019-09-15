.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setBarVisible
   |version=1.3b46
   |description=
   Sets if the specified [[Token:bar|bar]] for the [[Current_Token|Current Token]] is visible or not. If the value is non zero then the [[Token:bar|bar]] is visible, if it is 0 it is not visible.

   |usage=
   <source lang="mtmacro" line>
   setBarVisible(name, value)
   </source>

   |examples=
   Make "health" [[Token:bar|bar]] for the [[Current_Token|Current Token]] visible.
   <source lang="mtmacro" line>
   [h: setBarVisible("health", 1)]
   </source>

   Hide "health" [[Token:bar|bar]] for the [[Current_Token|Current Token]].
   <source lang="mtmacro" line>
   [h: setBarVisible("health", 0)]
   </source>
   }}

`Category:Bar Function <Category:Bar_Function>`__
