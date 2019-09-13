{{\#customtitle:ライブラリトークン|ライブラリトークン}}

<div style="color:gray">

Introduced in MapTool version b46, the Library Token is a special token
type that acts as a library of properties and trusted macros that may be
accessed and called by other macros.

</div>

MapToolバージョンb46で導入された、ライブラリトークンはプロパティと他のマクロにアクセスし実行可能な承認マクロを収蔵する特殊なトークン種別である。

## ライブラリトークンの命名

<div style="color:gray">

All library tokens must have a name in the format "Lib:*name*", to
indicate that they are to serve as a Library Token and not a "normal"
token. Example library token names might be:

</div>

ライブラリトークンの名前は必ず「Lib:*名前*」の書式であり、このトークンがライブラリトークンであり通常のトークンではないことを示している。ライブラリトークン名の例は次の通り：

  - Lib:test
  - Lib:combat
  - Lib:gamemaster

## ライブラリトークンを作成する

<div style="color:gray">

To create a Library Token, do the following:

</div>

ライブラリトークンを作成するには、次の手順になる：

<div style="color:gray">

1.  Drag a new token on to one of the maps in your campaign.
2.  Rename it with a name in the format **Lib**:*name* (*e.g.*,
    **Lib:DnD**, **Lib:GameRules**, etc.).
3.  Right click on the token and make sure that **Visible to Players**
    is checked.
4.  Double-click on it, and go to the **Ownership** tab. Make sure that
    ***nothing*** is checked.
5.  Set the token type to NPC (upper right corner of the Token
    Configuration dialog).

</div>

1.  キャンペーンのマップ上にトークンを配置する。
2.  名前を**Lib**:*name*の書式に変更する（例：**Lib:DnD**、**Lib:GameRules**など）。
3.  トークン上で右クリックし、**プレイヤーに表示**が有効になっていることを確認する。
4.  トークンをダブルクリックし、**Ownership**タブを開く。いずれのチェックボックスも***無効になっている***ことを確認する。
5.  トークン・タイプをNPCに設定する。（トークン設定ダイアログの右上）

<div style="color:gray">

After that, you have a Library Token. Note that you cannot have two
library tokens with the same name in the same campaign (even if they're
on different maps\!).

</div>

以上でライブラリトークンの完成だ。同一キャンペーン内で、同じ名前持つライブラリトークンを複数持つことができないことを覚えておくように。（それぞれが違うマップにあっても、だ！）

<div style="color:gray">

Once again, the requirements are:

</div>

しつこいようだが、必要条件を挙げておく：

<div style="color:gray">

  - The library token must be visible to players (make sure Visible to
    Players is set in the right-click context menu). The library token
    need not be on the "Token" layer (you can keep it on the "Hidden"
    layer to hide it from players, although "Visible to Players" must
    still be set to true).
  - The library token must have a name in the format "Lib:*name*"
  - The library token must be present on *only one* map in the campaign
    file.
  - The library token **may not** be owned by any players (it's best not
    to be owned by ANYONE\!)

</div>

  - ライブラリトークンはプレイヤーに表示していなければならない（右クリックメニューの「プレイヤーに表示（Visible to
    Players）が有効になっていることを確認）。ライブラリトークンは「トークン・レイヤー」にある必要はない（「Hidden」レイヤーに置くことでプレイヤーから隠すことは可能だが、それでも「プレイヤーに表示」は有効にしておかなければならない）。
  - ライブラリトークンは「Lib:*名前*」の書式でなければならない。
  - ライブラリトークンはキャンペーン・ファイルに*ひとつだけ*存在することができる。
  - ライブラリトークンはどのプレイヤーも**所有権を持たないほうが良い**（『誰も』所有権を持たないほうが良い！）。

## ライブラリトークンと承認マクロ

<div style="color:gray">

In addition to the above requirements if you want players to be able to
run any macro that calls a function designated as a trusted function the
following requirement must also be met.

</div>

<div style="color:gray">

1.  The library token must *not* be owned by any players (in the
    Ownership tab of the Edit Token dialog, make sure that no boxes are
    checked)

</div>

上記の必要条件に加えて、プレイヤーが承認関数として指定された関数を呼び出すマクロを実行できるようにする必要がある場合、上記の条件に加えて次の条件も満たしている必要がある。

1.  ライブラリトークンはどのプレイヤーも*所有権を持ってはならない*（トークン編集ダイアログのOwnershipタブにあるチェックボックスがすべて無効になっていることを確認）。

<div style="color:gray">

Multiple library tokens may exist in the same campaign provided no two
library tokens have the same token name.

</div>

複数のライブラリトークンはそれぞれが異なる名前を持っている限りキャンペーン内で共存できる。

## ライブラリトークンマクロ

<div style="color:gray">

Library token macros are created and edited like macros on any token.
Macros on a library token may be called using the
[\[MACRO():](Macros:Branching_and_Looping#MACRO_Option "wikilink")\]
roll option. Since Library token macros are trusted, they may perform
operations not available to regular tokens.

</div>

ライブラリトークン・マクロはトークンのマクロと同じように記述する。ライブラリトークンのマクロはロール・オプション：[\[MACRO():](Macros:Branching_and_Looping/ja#MACRO_Option "wikilink")\]を使用することが多い。ライブラリトークンマクロは承認されるので、通常のトークンがなしえない操作を行うことができる。

## ライブラリトークンプロパティー

<div style="color:gray">

Library token properties can be accessed by using the  function. Note
that default property values do **NOT** work using that function.

</div>

ライブラリトークンのプロパティーは関数：を使用してアクセス可能だ。標準のプロパティ値はこの関数を使っても**機能しない**ことに注意。

[Category:Token](Category:Token "wikilink")