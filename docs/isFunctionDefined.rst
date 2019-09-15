.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub}}

.. raw:: mediawiki

   {{MacroFunction
   |name=isFunctionDefined
   |version=1.3b51
   |description=
   Checks if a function has been defined using [[defineFunction|defineFunction()]]. Returns {{code|true}}({{code|1}}) if it has, or {{code|false}}({{code|0}}) if it has not.  Returns '2' if the entered function is a built-in MapTool function rather than a user-defined function.

   |usage=
   <source lang="mtmacro" line>
   isFunctionDefined(name)
   </source>

   |examples=
   <source lang="mtmacro" line>
   [r: isFunctionDefined("fizzlegwip")]
   </source>
   Returns 0.

   <source lang="mtmacro" line>
   [h: defineFunction("myNewFunction", "myMacro@token")]
   </source>
   <source lang="mtmacro" line>
   [r: isFunctionDefined("myNewFunction")]
   </source>
   Returns 1.

   <source lang="mtmacro" line>
   [r: isFunctionDefined("input")]
   </source>
   Returns 2.

   |also=
   [[defineFunction|defineFunction()]], [[arg|arg()]], [[argCount|argCount()]]

   }}

`Category:User Defined Function <Category:User_Defined_Function>`__
