.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub}}

.. raw:: mediawiki

   {{RollOption
   |name=for
   |version=1.3.b46
   |description=Executes a statement for a number of iterations based on a start and end value.

   |usage=
   <source lang="mtmacro" line>
   [for(var, start, end): body]
   </source>
   <source lang="mtmacro" line>
   [for(var, start, end, stepsize): body]
   </source>
   <source lang="mtmacro" line>
   [for(var, start, end, stepsize, separator): body]
   </source>
   '''Parameters'''<br>
   The {{code|var}} variable counts from {{code|start}} towards {{code|end}} during the loop, and the optional {{code|stepsize}} (default {{code|+1}}) is added to {{code|var}} at each iteration.  Note that in the standard incrementing usage with a {{code|stepsize}} of {{code|1}}, the {{code|body}} does not execute when {{code|var}} reaches {{code|end}}. <br>
   Note that {{code|stepsize}} must be integer and not 0. Floating values will be rounded down.<br>
   {{code|list_separator}} default value is {{code|","}}. Some examples of other useful separators: ''nothing'' {{code|""}}, ''space'' {{code|" "}} and ''break'' {{code|"<br>"}}.


   |examples=
   <source lang="mtmacro" line>
   [for(i,0,10): "i is now " + i]
   </source>
   Counts up from 0 to 9.

   <source lang="mtmacro" line>
   [for(i,10,0,-2): "i is now " + i]
   </source>
   Counts down even numbers from 10 to 0.

   |also=
   {{roll|foreach}},
   [[Introduction_to_Macro_Loops|Introduction to Macro Loops]]

   |changes=
   {{change|1.3b54|Changed the comparison operator when comparing the {{code|var}} to {{code|end}} when determining whether to continue executing a new iteration.  In version 1.3b53 and earlier, on each iteration it compared if {{code|var}} was less than or equal to {{code|end}}.  As of version 1.3b54, it is now comparing if {{code|var}} is less than {{code|end}}.}}
   }}

`Category:Roll Option <Category:Roll_Option>`__ `Category:Looping Roll
Option <Category:Looping_Roll_Option>`__
