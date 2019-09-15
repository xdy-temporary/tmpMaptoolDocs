.. contents::
   :depth: 3
..

.. raw:: mediawiki

   |name=add
   |trusted=false
   |version=1.3.b48
   |description=Adds number and/or strings together. If all of the arguments to the function are numbers then a numeric addition is performed, if any of the arguments are strings then all of the arguments are concatenated as a string.

   |usage=
   <source lang="mtmacro" line>
   [h: result = add(val1, val2, ...)]
   [h: result = sum(val1, val2, ...)]
   [h: result = concat(val1, val2, ...)]
   </source>

   |examples=
   ====Numbers====
   <source lang="mtmacro" line>
   [r: add(1,4)]
   </source>
   Returns:<source lang="mtmacro" line start=2>5</source>


   ====Strings====
   <source lang="mtmacro" line>
   [r: add("Mary", "had", "a", "little", "lamb")]
   </source>
   Returns:<source lang="mtmacro" line start=2>"Maryhadalittlelamb"</source>


   ====Numbers and Strings====
   <source lang="mtmacro" line>
   [r: add(1,"4")]
   </source>
   Returns:<source lang="mtmacro" line start=2>"14"</source>


`Category:Mathematical Function <Category:Mathematical_Function>`__
`Category:String Function <Category:String_Function>`__
