.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=herolab.getMasterName
   |trusted=true
   |version=1.5
   |description=
   Get basic information about the Hero Lab data associated with this token. Returns a JSON object containing various metadata about the character.

   |usage=
   <source lang="mtmacro" line>
   herolab.getMasterName()
   herolab.getMasterName(id)
   </source>

   '''Parameters'''
   {{param|id|The token id of the token to name, defaults to the Current Token.}}

   |example=
   Get the Hero Lab Master character name associated with the character represented by the current token.
   <source lang="mtmacro" line>
   [h: myMaster = herolab.getMasterName()]
   [r: out = "My master's name is: " + myMaster]
   </source>
   Returns:
   <source lang="text" line>
   My master's name is: Fred
   </source>

   |also=
   [[Hero_Lab_Integration|Hero Lab Integration]]

   |changes=
   * '''1.5''' - Added to main MapTool build.
   }}

`Category:Hero Lab Function <Category:Hero_Lab_Function>`__
