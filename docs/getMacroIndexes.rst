.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub|Examples of usage.}}

.. raw:: mediawiki

   {{MacroFunction
   |name=getMacroIndexes
   |version=1.3b48
   |description=Returns a list of the [[macro_buttons|macro buttons]] on the [[Current_Token|Current Token]] that have the specified label. The type of the value returned depends on the delimiter parameter. 

   |usage=
   <source lang="mtmacro" line>
   getMacroIndexes(label)
   </source>
   <source lang="mtmacro" line>
   getMacroIndexes(label, delim)
   </source>
   <source lang="mtmacro" line>
   getMacroIndexes(label, delim, id)
   </source>
   '''Parameters'''
   {{param|label|The label for the macro buttons to return.}}
   {{param|delim|The delimiter used to separate the values in the [[String_List|String List]] which defaults to {{code|","}} if not specified. This function returns a [[JSON_Object|JSON Object]] if {{code|"json"}} is specified.}}
   {{param|id|The token {{code|id}} of the token that the function is executed on. {{TrustedParameter}} }}

   |changes=
   {{change|1.3b49|Added {{code|"json"}} delimiter option.}}
   {{change|1.3b51|Added {{code|id}} parameter option.}}
   }}

`Category:Metamacro Function <Category:Metamacro_Function>`__
