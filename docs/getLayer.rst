.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub|Examples of usage.}}

.. raw:: mediawiki

   {{MacroFunction
   |name=getLayer
   |version=1.3b48
   |description=
   Returns the [[Map_Layer|Map Layer]] that a [[Token|Token]] is on.

   The [[Map_Layer|Map Layer]] will be one of:
   * {{code|TOKEN}}
   * {{code|GM}} also known as Hidden
   * {{code|OBJECT}}
   * {{code|BACKGROUND}}
    

   |usage=
   <source lang="mtmacro" line>
   getLayer()
   getLayer(id)
   getLayer(id, mapname)
   </source>
   '''Parameter'''
   {{param|id|The token {{code|id}} of the token which has its [[Map_Layer|Map Layer]] returned, defaults to the [[Current_Token|Current Token]]. {{TrustedParameter}} }}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}

   |also=
   [[setLayer|setLayer()]]

   |changes=
   {{change|1.3b51|Added {{code|id}} parameter option.}}
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}

   }}

`Category:Token Function <Category:Token_Function>`__
