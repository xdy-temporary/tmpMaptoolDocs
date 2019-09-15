.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=currentToken
   |version=1.3b48
   |description=Returns the id of the [[Current_Token|Current Token]]. In most cases this will return the same as [[Macros:Functions:getImpersonated|getImpersonated()]] function. The difference is when it is called in a {{roll|token}} or after a call to the  [[Macros:Functions:switchToken|switchToken()]] function, in both these cases it will return the id of the [[token|token]] being operated on, while [[Macros:Functions:getImpersonated|getImpersonated()]] will return the id of the [[impersonated_token|impersonated token]].

   |usage=
   <source lang="mtmacro" line>
   currentToken()
   </source>

   |changes=
   {{change|1.3b51|No longer a trusted function.}}

   }}

`Category:Token Function <Category:Token_Function>`__
