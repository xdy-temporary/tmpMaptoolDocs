.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=set
   |trusted=false
   |version=1.3b48
   |description=
   Sets the value of a variable.
   <p>
   This function is rarely used because a simple assignment to a variable name can be used instead.  However, using this function allows the first parameter to be a variable that identifies the variable name to be assigned.
   </p>
   |usage=
   <source lang="mtmacro" line>
   [h: set(varName, val)]
   </source>
   '''Parameters'''
   {{param|varName|Variable name or a string containing a valid variable name.}}
   {{param|val|The value to set the variable to.}}

   |example=
   A simple use:
   <source lang="mtmacro" line>
   [h: set("test", 33)]
   [r: test]
   </source>
   Returns 
       33

   A more sophisticated example that shows passing a string expression as the first parameter:
   <source lang="mtmacro" line>
   [h: var1="te"]
   [h: var2="st"]
   [h: set(var1+var2, 33)]
   [r: test]
   </source>
   Returns 
       33

   Both of the above examples are equivalent to:
   <source lang="mtmacro" line>
   [r: test = 33]
   </source>
   }}

`Category:Miscellaneous Function <Category:Miscellaneous_Function>`__
