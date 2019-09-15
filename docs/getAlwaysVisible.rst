.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getAlwaysVisible
   |version=1.4.2.0
   |description=
   Returns the value of the corresponding setting for the token. '''Always Visible''' is a VBL setting which can be found in the '''Edit...''' menu of the token under the VBL tab. 

   |usage=
   <source lang="mtmacro" line>
   getAlwaysVisible([id])
   </source>

   '''Parameters'''
   {{param|value|The value of the setting to set, {{code|true}}({{code|1}}) or {{code|false}}({{code|0}}).}}
   {{param|id|OPTIONAL: The token {{code|id}} of the token for which you want to set this setting, defaults to the [[Current_Token|Current Token]]. {{TrustedParameter}} }}

   |example=
   <source lang="mtmacro" line>
   The Always Visible setting for Dragon is currently set to: [r: getAlwaysVisible("Dragon")]
   [h, token("Dragon"): isVisible = getAlwaysVisible()]
   </source>
   }}

`Category:VBL Function <Category:VBL_Function>`__
