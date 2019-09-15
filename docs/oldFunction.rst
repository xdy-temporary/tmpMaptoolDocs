.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=oldFunction
   |version=1.3b51
   |description=
   If a user-defined function redefines a standard MapTool function or another user-defined function -- for instance, a user defines a function called {{code|eval()}}, redefining the standard MapTool {{func|eval}} -- {{func|oldFunction}} can be used in the user-defined function to call the original function. When a user-defined function redefines an existing function, it keeps track of the function that it redefined. Due to this tracking, it is possible to redefine a function multiple times and {{func|oldFunction}} will always reference the previous function in the chain.

   '''Note:''' Do not rely on a specific order in the function chain unless you are sure that the functions will be redefined in that order. Calls to {{func|defineFunction}} within [[onCampaignLoad|onCampaignLoad]] macros on different [[Library_Token|Library Token]]s are not executed in any standard order.

   |usage=
   <source lang="mtmacro" line>
   oldFunction(SPECIAL)
   </source>
   '''Parameter'''
   {{param|SPECIAL|oldFunction supports the same parameters as the function that it is referencing.}}

   |example=
   Within a user-defined function named {{code|eval()}}, {{func|oldFunction}} is used to call the standard MapTool {{func|eval}} function.
   <source lang="mtmacro">
   [h, if ( arg(0) == 0 ), code:
   {
       [h: macro.return = 0]
   };{
       [h: macro.return = oldFunction( arg(0) ) ]
   }]
   </source>
   By having access to the original function definition, this example is able to provide custom or standard return values when called.

   |also=
   {{func|defineFunction}}

   }}

`Category:User Defined Function <Category:User_Defined_Function>`__
