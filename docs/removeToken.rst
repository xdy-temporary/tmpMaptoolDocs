.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub}}

.. raw:: mediawiki

   {{MacroFunction
   |name=removeToken
   |trusted=true
   |version=1.3b51
   |description=
   Removes a token from the current map.

   |usage=
   <source lang="mtmacro" line>
   removeToken(id)
   </source>
   '''Parameter'''
   {{param|id|The id of the token to remove.}}

   One caveat, you can remove the impersonated token in a macro but if you do so you must make sure not to use any macro functions that refer to the deleted token or you will cause errors.

   }}

`Category:Token Function <Category:Token_Function>`__
