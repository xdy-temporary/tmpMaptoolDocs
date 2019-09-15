.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setMaxRecursionDepth
   |version=1.4.0.2
   |description=
   Returns the current amount of recursive calls that are used.

   |usage=
   <source lang="mtmacro" line>
   setMaxRecursionDepth(depth)
   </source>
   Where 
   * ''depth'' is the new maximum allowed recursive calls. Note that the depth can never be lower then the default depth, which is 150, setting it lower will result in a depth of 150. Setting this value higher is obviously at your own risk as this has a serious impact on the stack. Note that this settings lasts only for the current session. 

   |example=
   <source lang="mtmacro" line>
   [h: setMaxRecursionDepth(200)]
   </source>

   |also=
   {{func|getRecursionDepth}},
   {{func|getMaxRecursionDepth}}.


   }}

`Category:Loop and Recursion
limits <Category:Loop_and_Recursion_limits>`__
