.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=herolab.isMinion
   |trusted=true
   |version=1.5
   |description=
   Returns true if token is a Hero Lab ''minion'' character, such as an Eidolon or Familiar. Otherwise it returns false.

   |usage=
   <source lang="mtmacro" line>
   herolab.isMinion()
   herolab.isMinion(id)
   </source>

   '''Parameters'''
   {{param|id|The id of the token. Defaults to the Current Token.}}

   |example=
   Get the boolean value of the isMinion flag in the Hero Lab data.
   <source lang="mtmacro" line>
   [r: isMinion = herolab.isMinion()]
   </source>
   Returns:
   <source lang="mtmacro" line>
   0 or 1
   </source>
   This is the same as using the {{func|getInfo}} function and reading the {{code|isMinion}} field.
   <source lang="mtmacro" line>
   [h: info = herolab.getInfo()]
   [r: isMinion = json.get(info,"isMinion")]
   </source>
   Returns:
   <source lang="mtmacro" line>
   0 or 1
   </source>
   |also=
   [[Hero_Lab_Integration|Hero Lab Integration]]

   |changes=
   * '''1.5''' - Added to main MapTool build.
   }}

`Category:Hero Lab Function <Category:Hero_Lab_Function>`__
