.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=transferVBL
   |proposed=false
   |trusted=true
   |version=1.4.2.0
   |description=
   Directly transfers VBL from token to the VBL layer if true; otherwise, it transfers from the VBL layer to the token.

   |usage=
   <source lang="mtmacro" line>
   transferVBL(value)
   transferVBL(value, delete)
   transferVBL(value, id)
   transferVBL(value, delete, id)
   </source>

   This function can be used to transfer TOKEN VBL to NORMAL VBL or vice versa. Token VBL moves with the token, can be set under the VBL tab on the token '''Edit...''' menu, and is colored YELLOW.  Normal VBL is static, can be created with the VBL drawing tools, or with the use of VBL functions and is colored BLUE.

   '''Parameters'''
   {{param|value|The value of the setting to set:
   ** {{code|0}} transfer normal (blue) VBL to token (yellow) VBL}}
   ** {{code|1}} transfer token (yellow) VBL to normal (blue) VBL
   {{param|delete|Defines if the transferred VBL is deleted from the source.}}
   {{param|id|OPTIONAL: The token {{code|id}} of the token for which you want to set this setting, defaults to the [[Current_Token|Current Token]].}}

   |examples=
   ''Example: Transfer VBL from Token to Map''
   <source lang="mtmacro">
   [h:transferVBL(1, "Dragon")]
   [h:transferVBL(0)]
   </source>

   ''Example: Transfer VBL from Map to current Token''
   <source lang="mtmacro">
   [h:transferVBL(0)]
   </source>

   ''Example: Clear VBL from Token after transfer since 1.5.1''
   <source lang="mtmacro">
   [h:transferVBL(1, 1)]
   </source>

   ''Example: Clear VBL from Token after transfer before 1.5.1''
   <source lang="mtmacro">
   [h:transferVBL(1)]
   [h: finalVblData = "{'shape':'none'}"]
   [h: setTokenVBL(finalVblData)] 
   </source>

   |changes=
   {{change|1.5.0|new delete parameter}}

   |also=
   [[Introduction_to_Vision_Blocking|Introduction to Vision Blocking]], {{func|eraseVBL}}, {{func|drawVBL}}, {{func|setTokenVBL}}
   }}

`Category:Miscellaneous Function <Category:Miscellaneous_Function>`__
`Category:VBL Function <Category:VBL_Function>`__
