.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub}}

.. raw:: mediawiki

   {{MacroFunction
   |name=getStateImage
   |version=1.3b40
   |description=
   Gets the [[Asset_ID|asset id]] for the image of a state, the state must be one of the image types for this to work.

   |usage=
   <source lang="mtmacro" line>
   getStateImage(state)
   </source>
   <source lang="mtmacro" line>
   getStateImage(state, size)
   </source>
   '''Parameters'''
   * {{code|state}} - The name of the state which has its image asset returned.
   * {{code|size}} - The size that the state image will be resized to; this is the height of the final size.

   |example=
   To display the image for the "Dead" [[Token:state|token state]] use.
   <source lang="mtmacro" line>
   <img src='[r:getStateImage("Dead")]'></img>
   </source>

   }}

`Category:State Function <Category:State_Function>`__
