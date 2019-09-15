.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=herolab.hasChanged
   |trusted=true
   |version=1.5
   |description=
   Returns a boolean value of true if the portfolio file has been modified compared to the current stored data on the token, otherwise returns false.

   |usage=
   <source lang="mtmacro" line>
   herolab.hasChanged()
   herolab.hasChanged(id)
   </source>
   See {{func|herolab.refresh}} to update the token's portfolio information.

   '''Parameters'''
   {{param|id|The id of the token. Defaults to the Current Token.}}

   |example=
   Determine if the associated Hero Lab portfolio has changed.
   <source lang="mtmacro" line>
   [r: isDirty = herolab.hasChanged()]
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
