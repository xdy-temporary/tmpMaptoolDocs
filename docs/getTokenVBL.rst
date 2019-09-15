.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getTokenVBL
   |proposed=false
   |trusted=true
   |version=1.4.1.6
   |description=Gets the VBL attached to a token as a JSON object.

   |usage=
   <source lang="mtmacro" line>
   getTokenVBL(id)
   </source>

   This macro function is used used to get a JSON object describing the TOKEN VBL attached to a token.  The returned JSON object can then be used with {{func|setTokenVBL}}, {{func|drawVBL}}or {{func|eraseVBL}}.

   Token VBL is attached to and moves with the token.  It can  be set (or cleared) under the VBL tab on the Edit Token dialog and is colored YELLOW. Normal VBL is static, can be created with the VBL drawing tools or with the use of VBL functions and is colored BLUE.

   '''Parameters'''
   {{param|id|OPTIONAL: The token {{code|id}} of the token for which you want to get the VBL. Defaults to the [[Current_Token|Current Token]]. }}

   ''Example:''<source lang="mtmacro">
   [h: vbl = getTokenVBL("Door, Steel")]
   [h: setTokenVBL(vbl, "Door, Wood")]
   </source><br />

   |also=
   [[Introduction_to_Vision_Blocking|Introduction to Vision Blocking]], {{func|setTokenVBL}}, {{func|drawVBL}} or {{func|eraseVBL}}
   }}

`Category:Miscellaneous Function <Category:Miscellaneous_Function>`__
`Category:VBL Function <Category:VBL_Function>`__
