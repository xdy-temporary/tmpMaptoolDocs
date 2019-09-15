.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=eval
   |version=pre-1.3
   |description=
   Evaluates an expression in a string and returns the result. The string contains the same type of expression that is usually located between macro brackets (e.g '''{ }''' or '''[r: 2+2]'''). {{func|eval}} is commonly used to evaluate dynamically built {{func|input}} parameters, or dice expressions stored in token properties.

   For more complex evaluation functions, see {{func|evalMacro}} and {{func|execMacro}}.

   |usage=
   <source lang="mtmacro" line>
   eval(expr)
   </source>
   '''Parameter'''
   {{param|expr|A string containing the expression to be evaluated.}}

   |examples=
   <source lang="mtmacro" line>
   [r: eval("1+1")]
   </source>
   Returns {{code|2}}

   <source lang="mtmacro" line>
   [r: eval("3d6")]
   </source>
   Returns a random number from {{code|3}} to {{code|18}}.

   <source lang="mtmacro" line>
   [r: eval("TestVar = 2")]
   </source>
   Returns {{code|2}}

   <source lang="mtmacro" line>
   [h: TestVar = 2][r: eval("TestVar/2")]
   </source>
   Returns {{code|1}}


   '''Tip'''
   Since {{code|eval()}} only accepts strings as parameter and it happens quite often that you have either numbers or strings following code is a good method to make it work in any case.
   <source lang="mtmacro" line>
   [h: foo = eval(string(bar))]
   </source>
   |also=
   {{func|evalMacro}}, 
   {{func|execMacro}}

   }}

`Category:Miscellaneous Function <Category:Miscellaneous_Function>`__
