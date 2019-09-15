.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getMacros
   |version=1.3b48
   |description=
   Returns a list of the labels of all of the [[Macro_Button|macro buttons]] on the [[Current_Token|Current Token]]. The type of the value returned depends on the delimiter parameter. 

   |usage=
   <source lang="mtmacro" line>
   getMacros()
   </source>
   <source lang="mtmacro" line>
   getMacros(delim)
   </source>
   <source lang="mtmacro" line>
   getMacros(delim, id)
   </source>
   '''Parameters'''
   {{param|delim|The delimiter used to separate the values in the  [[String_List|String List]], a JSON array is returned if {{code|"json"}} is specified as the delimiter. Defaults to {{code|","}} }}
   {{param|id|The token {{code|id}} of the token that the function is executed on. {{TrustedParameter}} }}

   |examples=
   To display all of the [[Macro_Button|macro button]] labels on the current [[Token|token]] use.
   <source lang="mtmacro" line>
   [h: macroLabels = getMacros()]
   [foreach(macro, macroLabels, "<br>"): macro]
   </source>

   |changes=
   {{change|1.3b49|Added {{code|json}} delimiter option.}}
   {{change|1.3b51|Added optional token {{code|id}} parameter.}}

   }}

`Category:Metamacro Function <Category:Metamacro_Function>`__
