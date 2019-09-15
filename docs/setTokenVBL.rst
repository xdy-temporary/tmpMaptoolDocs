.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setTokenVBL
   |proposed=false
   |trusted=true
   |version=1.4.1.6
   |description=Sets the VBL of a token to that given in the JSON object parameter.

   |usage=
   <source lang="mtmacro" line>
   setTokenVBL(vbl, id)
   </source>

   This function is used to attach the TOKEN VBL passed in as a JSON object to a token.  The JSON object may be be created by calling {{func|getTokenVBL}} on a different token and may also be used with {{func|drawVBL}} or {{func|eraseVBL}}.

   Token VBL moves with the token, can be set under the VBL tab on the token edit menu and is colored YELLOW. Normal VBL is static, can be created with the VBL drawing tools or with the use of VBL functions and is colored BLUE.

   '''Parameters'''
   {{param|vbl|A JSON object containing the {{code|vbl}} to be added to the token.  Use {{func|getTokenVBL}} to get VBL from another token. }}
   {{param|id|OPTIONAL: The token {{code|id}} of the token for which you want to set this setting, defaults to the [[Current_Token|Current Token]]. }}

   ''Example: Transfer VBL from one Token to another''<source lang="mtmacro">
   [h: vbl = getTokenVBL("Door, Steel")]
   [h: setTokenVBL(vbl, "Door, Wood")]
   </source><br />

   ''Example: Erase VBL from Token''<source lang="mtmacro">
   [r: finalVblData = "{'shape':'none'}"]
   [r: setTokenVBL(finalVblData)]
   </source><br />

   |also=
   [[Introduction_to_Vision_Blocking|Introduction to Vision Blocking]], {{func|getTokenVBL}}, {{func|drawVBL}}, {{func|eraseVBL}}
   }}

`Category:Miscellaneous Function <Category:Miscellaneous_Function>`__
`Category:VBL Function <Category:VBL_Function>`__
