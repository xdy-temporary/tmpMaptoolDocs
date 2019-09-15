.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getMaxRecursionDepth
   |version=1.4.0.2
   |description=
   Returns the max amount of recursive calls that are allowed. However The recursion depth of the parser is not quite straight forward, there are actually two different recursion depths that track two different types of recursive calls, you can have up to 150 of each, the getRecursionDepth() will return the greater of the two levels.

   |usage=
   <source lang="mtmacro" line>
   getMaxRecursionDepth()
   </source>

   |example=
   <source lang="mtmacro" line>
   [r: getMaxRecursionDepth()]
   </source>

   |also=
   {{func|getRecursionDepth}}, 
   {{func|setMaxRecursionDepth}}.

   }}

`Category:Loop and Recursion
limits <Category:Loop_and_Recursion_limits>`__
