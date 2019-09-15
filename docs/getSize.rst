.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub|Examples of usage.}}

.. raw:: mediawiki

   {{MacroFunction
   |name=getSize
   |version=1.3b48
   |description=
   Returns the [[Size|Size]] of a [[Token|Token]].

   The sizes returned are:
   * {{code|Fine}}
   * {{code|Diminutive}}
   * {{code|Tiny}}
   * {{code|Small}}
   * {{code|Medium}}
   * {{code|Large}}
   * {{code|Huge}}
   * {{code|Gargantuan}}
   * {{code|Colossal}}
    

   |usage=
   <source lang="mtmacro" line>
   getSize()
   getSize(id)
   getSize(id, mapname)
   </source>
   '''Parameter'''
   {{param|id|The token {{code|id}} of the token which has its [[Size|Size]] returned, defaults to the [[Current_Token|Current Token]]. {{TrustedParameter}} }}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}

   * Note that if the token is in native or free size, the value returned will be an empty string: ""

   |also=
   [[setSize|setSize()]]

   |changes=
   {{change|1.3b51|Added {{code|id}} parameter option.}}
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}

   }}

`Category:Token Function <Category:Token_Function>`__
