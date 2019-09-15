.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setMaxLoopIterations
   |version=1.4.0.2
   |description=
   Sets the max amount of loops (in {{roll|count}}, {{roll|foreach}}, {{roll|for}}, {{roll|while}}) that are allowed. The current allowed max is 10,000 and this is also the minimum. Note that this settings lasts only for the current session. 

   |usage=
   <source lang="mtmacro" line>
   setMaxLoopIterations(numLoops)
   </source>
   Where 
   * ''numLoops'' is the new maximum allowed iterations, this value cannot be lower than 10,000

   |example=
   <source lang="mtmacro" line>
   [r: setMaxLoopIterations()]
   </source>

   |also=
   {{func|getMaxLoopIterations}}.

   }}

`Category:Loop and Recursion
limits <Category:Loop_and_Recursion_limits>`__
