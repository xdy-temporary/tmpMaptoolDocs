.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=herolab.getImage
   |trusted=true
   |version=1.5
   |description=
   Returns the asset id of the image retrieved from a Hero Lab file for a Token.

   |usage=
   <source lang="mtmacro" line>
   herolab.getImage(index)
   herolab.getImage(index, id)
   </source>

   '''Parameters'''
   {{param|index|The index of the image you wish to retrieve.}}
   {{param|id|The token id of the token to name, defaults to the Current Token.}}

   Hero Lab can store 0 to n images for a given character. The index is the order Hero Lab stores the images (not the display order in Hero lab). Index always starts at 0.

   |example=
   Get an image asset ID from an image in a Hero Lab file and use that to set a token portrait image.
   <source lang="mtmacro" line>
   [portraitImage = herolab.getImage(0)]
   [setTokenImage(portraitImage)]
   </source>
   Returns:
   <source lang="mtmacro" line>
   Asset ID of requested image.
   </source>

   |also=
   [[Hero_Lab_Integration|Hero Lab Integration]]

   |changes=
   * '''1.5''' - Added to main MapTool build.
   }}

`Category:Hero Lab Function <Category:Hero_Lab_Function>`__
