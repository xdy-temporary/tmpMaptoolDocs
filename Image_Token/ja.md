{{\#customtitle:画像トークン|画像トークン}}

画像トークン
------------

<div style="color:gray">
An image token is a [Token](Token "wikilink") whose name starts with the string “image:” -- case is not important. These [tokens](Token "wikilink") can appear on any [map](Map:map "wikilink") and you can use functions such as [getImage()](getImage "wikilink") to search through all of the [maps](Map:map "wikilink") to find the [token](Token "wikilink") and return the [asset id](Asset_ID "wikilink") for the [token](Token "wikilink")'s image. The [image token](Image_Token "wikilink") does not have to be owned by a player to be used but the [visible to player](Token:visible_to_player "wikilink") flag must be set. You can not have more than one [image token](Image_Token "wikilink") with the same name in a [campaign file](Campaign:campaign_file "wikilink").

</div>
画像トークンは“image:”の文字列で始まる名前を持つ[トークンのことだ](Token "wikilink")（大小文字は区別しない）。この[トークンはどの](Token "wikilink")[マップでも配置でき](Map:map "wikilink")、[getImage()のような全ての](getImage "wikilink")[マップからトークンを探し出し](Map:map "wikilink")、トークン画像の[アセットIDを返す関数を使える](Asset_ID "wikilink")。[画像トークンは](Image_Token/ja "wikilink")、プレイヤーが使用するにあたり所有権を設定する必要はないが、[プレイヤーに表示の設定を有効にしていなければならない](Token:visible_to_player "wikilink")。[キャンペーン・ファイルの中で同じ名前を持つ](Campaign:campaign_file "wikilink")[画像トークンを複数持つことはできない](Image_Token/ja "wikilink")。

<Category:Token>