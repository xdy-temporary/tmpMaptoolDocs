.. contents::
   :depth: 3
..

{{#customtitle:画像トークン|画像トークン}}

画像トークン
============

.. raw:: html

   <div style="color:gray">

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

.. raw:: html

   </div>

画像トークンは"image:"の文字列で始まる名前を持つ\ `トークンのことだ <Token>`__\ （大小文字は区別しない）。この\ `トークンはどの <Token>`__\ `マップでも配置でき <Map:map>`__\ 、\ `getImage()のような全ての <getImage>`__\ `マップからトークンを探し出し <Map:map>`__\ 、トークン画像の\ `アセットIDを返す関数を使える <Asset_ID>`__\ 。\ `画像トークンは <Image_Token/ja>`__\ 、プレイヤーが使用するにあたり所有権を設定する必要はないが、\ `プレイヤーに表示の設定を有効にしていなければならない <Token:visible_to_player>`__\ 。\ `キャンペーン・ファイルの中で同じ名前を持つ <Campaign:campaign_file>`__\ `画像トークンを複数持つことはできない <Image_Token/ja>`__\ 。

`Category:Token <Category:Token>`__
