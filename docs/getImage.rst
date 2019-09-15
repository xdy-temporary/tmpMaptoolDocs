.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getImage
   |version=1.3b48
   |description=Returns the [[asset_id|asset id]] for the image of a [[Token|Token]] or [[Image_Token|Image Token]]. 

   |usage=
   {{Clarify|There's no real parameter description.<br />
   Error handling on duplicates should be pointed out.}}
   <source lang="mtmacro" line>
   getImage(name)
   </source>

   '''Note:''' Token ID does NOT work, only token name works.

   Note that token images can be retrieved from ANY map (so they do NOT have to be on the current map).  If identical token names appear on multiple maps, it may be difficult (or impossible) to select a specific token image using this function.
   |example=
   To display the image from an [[Token:image_token{{!}}

image_token|Token:image token{{!}}image token]] called you can do the
following:

.. code:: mtmacro
   :number-lines:

   <img src="[r: getImage('image:Map')]"></img>

Alternatively this can be used to retrieve a normal token:

.. code:: mtmacro
   :number-lines:

   <img src="[r: getImage('Dragon')]"></img>

\|also=\ `getTokenImage <getTokenImage>`__ (which you can give the size
as parameter) }}

`Category:Miscellaneous Function <Category:Miscellaneous_Function>`__
