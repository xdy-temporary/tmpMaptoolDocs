.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=herolab.refresh
   |trusted=true
   |version=1.5
   |description=
   Refresh the Hero Lab data associated with this token. This will update the statblock and stored images.  

   |usage=
   <source lang="mtmacro" line>
   herolab.refresh()
   herolab.refresh(id)
   </source>
   This function will also refresh the token's images (just like when the token is created). The token's base Image from the first image in Hero Lab, the token's Portrait from the second image in Hero Lab, and the tokens' Handout image from the 3rd image in Hero Lab.

   '''Parameters'''
   {{param|id|The id of the token. Defaults to the Current Token.}}

   It will return a 1 if successful, otherwise it will return a 0.

   |example=
   Get the boolean value of the refresh flag in the Hero Lab data.
   <source lang="mtmacro" line>
   [r: success = herolab.refresh()]
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
