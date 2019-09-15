.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setAlwaysVisible
   |version=1.4.2.0
   |description=
   Turns the corresponding setting for the token on or off.  '''Always Visible''' is a VBL setting which can be found in the '''Edit...''' menu of the token under the VBL tab. 

   |usage=
   <source lang="mtmacro" line>
   setAlwaysVisible(value, [id])
   </source>

   '''Parameters'''
   {{param|value|The value of the setting to set, {{true}} or {{false}}.}}
   {{param|id|OPTIONAL: The token {{code|id}} of the token for which you want to set this setting, defaults to the [[Current_Token|Current Token]]. {{TrustedParameter}} }}

   |example=
   <source lang="mtmacro" line>
   [h: setAlwaysVisible(1)]
   [h: setAlwaysVisible(0, "Dragon")]
   </source>
   }}

`Category:VBL Function <Category:VBL_Function>`__
