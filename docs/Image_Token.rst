.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub}}

.. _image_token:

Image Token
===========

An image token is a `Token <Token>`__ whose name starts with the string
"image:" -- case is not important. These `tokens <Token>`__ can appear
on any `map <Map:map>`__ and you can use functions such as
`getImage() <getImage>`__ to search through all of the
`maps <Map:map>`__ to find the `token <Token>`__ and return the `asset
id <Asset_ID>`__ for the `token <Token>`__'s image. The `image
token <Image_Token>`__ does not have to be owned by a player to be used
but the `visible to player <Token:visible_to_player>`__ flag must be
set. You can not have more than one `image token <Image_Token>`__ with
the same name in a `campaign file <Campaign:campaign_file>`__.

`Category:Token <Category:Token>`__
