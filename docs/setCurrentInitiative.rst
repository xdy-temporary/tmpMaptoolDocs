.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setCurrentInitiative
   |trsuted=true
   |description=
   Gives the [[Initiative:Initiative|Initiative]] to the [[Token|Token]] at the specified offset in the [[Iniatiative:Initiative_Panel|Initiative Panel]]. Offsets start at 0.  

   To clear, specify a number that is not a valid token offset, like -1.

   |usage=
   <source lang="mtmacro" line>
   [h: setCurrentInitiative(offset)]
   </source>

   |examples=
   Give Initiative to the 4th [[Token|Token]].
   <source lang="mtmacro" line>
   [h: setCurrentInitiative(3)]
   </source>
   Clear current initiative  (any number that is not a valid token offset will work).
   <source lang="mtmacro" line>
   [h: setCurrentInitiative(-1)]
   [h: setCurrentInitiative(999)]
   </source>

   }}

`Category:Initiative Function <Category:Initiative_Function>`__
