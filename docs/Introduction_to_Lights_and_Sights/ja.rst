.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{Languages|Introduction to Lights and Sights}}

{{#customtitle:はじめての照明と視界|はじめての照明と視界}}

照明とは、視界とは
==================

.. raw:: html

   <div style="color:gray">

MapTool offers three features that help to simulate the idea that when a
character is adventuring in an environment, they are not always granted
an "ominiscient view" of the entire area - they can't see through walls,
around corners, or into the depths of dark dungeons. This is a difficult
thing to simulate when playing face to face, but with a computer, it
becomes possible to restrict a character's vision to what they might
actually see - thus raising the tension and possibly the immersion of
the game. The three features that MapTool offers are **Sight**,
**Light**, and **Fog of War**.

.. raw:: html

   </div>

MapTool
はキャラクターが環境の中で冒険するとき、それを再現するのに役立つ3つの機能を提供する。キャラクターは必ずしも世界を見渡す「神の目」を持って要るとは限らない。彼らは壁を透視することはできず、曲がり角の先や暗闇の洞窟の深部を見通すこともできない。このことをテーブルの上で再現することは難しいが、コンピューターを使用すればキャラクターが実際に見ているであろう視覚を正確に再現することが可能になる。それゆえに、ゲームのより高い緊張感と集中力を得ることになるであろう。MapTool
の提供する3つの機能とは、\ **視界**\ 、\ **照明**\ 、そして\ **不明領域**\ のことだ。

視界（Sight）
-------------

.. raw:: html

   <div style="color:gray">

Sight is the ability for a `token <Token:token>`__ to "see" its
surroundings - in this case, what a player's token can "see" becomes
visible to the player on their instance of MapTool (the GM can always
see everything on the map; players, on the other hand, can be limited in
what they see by things like `Vision Blocking
Layers <Introduction_to_Vision_Blocking>`__, light, and `Fog of
War <Introduction_to_Fog_of_War>`__). This makes for a more immersive
game, as players will wonder "What's around that corner?" and, "I hope
my torch doesn't burn out...it's dark in this dungeon!"

.. raw:: html

   </div>

視界とは\ `トークンが周囲を見渡す能力のことだ <Token:token>`__\ 。この場合、「トークンの周囲を見る能力」というのは、そのトークンを扱うプレイヤーの
MapTool
上に表示されるということである（GMは常にマップ上の全ての物を見ることができる。一方のプレイヤーは\ `遮光域レイヤー <Introduction_to_Vision_Blocking/ja>`__\ 、照明、\ `不明領域などにより限られた範囲しか見ることができない <Introduction_to_Fog_of_War>`__\ ）。このことはゲームにより高い臨場感をもたらし、プレイヤー達も「曲がり角の先には何があるのだろう？」、「松明よ、燃え尽きないで…ダンジョンは真っ暗なんだ!」と驚きもひとしおだろう。

照明（Light）
-------------

.. raw:: html

   <div style="color:gray">

Light is a feature that allows tokens and objects to cast "light" over a
certain area, illuminating it. This means that in a dark dungeon,
torches on the walls can illuminate small areas of the dungeon
(removing/erasing any Fog of War that might cover that area) and be seen
by the players (in other words, the area illuminated by the light source
becomes visible to the players, assuming that the player's token has
sight, and there is no VBL in the way).

.. raw:: html

   </div>

照明とは、トークンやオブジェクトに周囲を照らす「光」を与える機能のことだ。壁に掲げられた松明はダンジョンの一部を照らし（灯りの照らす範囲の不明領域を取り除く）、その場所はプレイヤーに見えるようになる（つまり、プレイヤーのトークンが視界を持っており、遮光域が光を阻まないのであれば、光源に照らされた範囲をプレイヤーが見ることが可能になる）。

.. raw:: html

   <div style="color:gray">

Light is critical when a map is using "Night" mode for vision, since
without light, a token is stuck in the pitch black!

.. raw:: html

   </div>

照明は、マップの視覚モードを「夜」にした場合、非常に重要な物となる。照明が無ければ真っ暗闇の中で途方に暮れるしかない。

.. _不明領域fog_of_war:

不明領域（Fog of War）
----------------------

.. raw:: html

   <div style="color:gray">

Fog of War is a system that represents what a token has seen as it is
moved about the Map, and what part of the map or environment the token
can directly see at that time. Fog of War should **not** be confused
with shadows or darkness. You can have Fog of War on a Map that has no
light or vision mode active at all.

.. raw:: html

   </div>

不明領域とは、マップ上を探索する中でトークンが目にしてきたマップの一部や状況を再現するシステムだ。不明領域は影や暗部と違う物なので混同しないように。不明領域は照明や視覚モードを無効にしているマップに使用できる。

.. raw:: html

   <div style="color:gray">

When a token with sight "sees" into an area of Fog of War, the Fog is
erased, letting the player see the map that was hidden beneath the
opaque Fog of War. When an area that a token *has* seen is no longer
*directly* visible to the token, the opaque Fog of War (the "Hard Fog")
is replaced by a semitransparent Fog (called "Soft Fog"). This is a
visual reminder that the player *has* seen that area, but cannot see it
*right now.* Any token in the Soft Fog is hidden from the character just
as if it were in Hard Fog.

.. raw:: html

   </div>

不明領域のある部分をトークンが「見た」とき、その部分を覆っていた不明領域が取り払われて、隠されていたマップの一部がプレイヤーに見えるようになる。一度不明領域が取り払われたが、その後トークンが去って今は直接見ていない部分は、完全な不明領域（Hard
Fog）ではなく半透明の不明領域（Soft
Fog）に置き換える。これはプレイヤーが\ *既に見た*\ 部分を覚えておくためのもので、\ *今見ている*\ わけではない。半透明の不明領域内にいるトークンは、完全な不明領域にいるトークンと同じようにキャラクターからは見えなくなっている。

.. raw:: html

   <div style="color:gray">

**Remember**: *Fog of War simply indicates what area of the maps have
been directly seen by a token.*

.. raw:: html

   </div>

**大事なこと**\ ：\ *不明領域とはトークンが直接目にしていないマップの範囲のことを指す。（訳注：未踏か探索済みかは関係ないということ）*

.. raw:: html

   <div style="color:gray">

Fog of War is a sufficiently complex discussion on its own that - even
though it is intimately connected with light and sight - it deserves its
own brief, but separate, tutorial. Check out `Introduction to Fog of
War <Introduction_to_Fog_of_War>`__ to get details and screenshots on
using Fog of War in your games.

.. raw:: html

   </div>

不明領域とてもややこしく、「照明と視界」に深く関わっているが独立したチュートリアルがあるべきだろう。不明領域をゲームに取り入れるために詳しい内容を
`Introduction to Fog of War <Introduction_to_Fog_of_War>`__
から学ぶと良いだろう。

サンプル・ダンジョン
====================

.. figure:: samp-dungeon.png
   :alt: samp-dungeon.png

   samp-dungeon.png

.. raw:: html

   <div style="color:gray">

A sample dungeon is used for all of the screenshots and examples in this
tutorial (and in the `Introduction to Vision
Blocking <Introduction_to_Vision_Blocking>`__). A screenshot of the
sample dungeon is shown at right; you can also download the Campaign
File for this dungeon `here <here>`__.

.. raw:: html

   </div>

サンプル・ダンジョンは、このチュートリアルのスクリーンショットと実例で使うものだ（\ `はじめての遮光域でも使っている <Introduction_to_Vision_Blocking/ja>`__\ ）。サンプル・ダンジョンのスクリーンショットは右にある。また\ `ここからこのダンジョンのキャンペーンファイルをダウンロードすることもできる <here>`__\ 。

視界の種類と光源を設定する
==========================

.. raw:: html

   <div style="color:gray">

Both Sight Types and Light Sources are configured from the Campaign
Properties window, under the Sight and Light tabs. To open the Campaign
Properties dialog, go to **Edit > Campaign Properties.**

.. raw:: html

   </div>

視界の種類と光源は、いずれもキャンペーンプロパティ・ウィンドウの
Sight（視界）タブと
Light（光源）タブのもとで設定する。キャンペーンプロパティのダイアログを表示するには
**Edit → Campaign Properties** を選択する。

視界の種類
----------

.. figure:: cprops-sighttab.png
   :alt: cprops-sighttab.png

   cprops-sighttab.png

.. raw:: html

   <div style="color:gray">

The Sight Types tab lets you set up different kinds of "sight" (such as
low-light, or darkvision/infrared, or normal vision, and so forth).
MapTool has some default sight types set up when you first open it. If
you look at the sight tab, you'll see the following:

.. raw:: html

   </div>

視界の種類のタブではさまざまな種類の「視界」を設定できる（夜目、暗視、赤外線視覚、通常の視覚などなど）。MapTool
では始めからいくつかの視界を用意してある。Sight
タブには下記と同じものが用意されている：

| ``Conic Vision: cone arc=120 ``
| ``Normal Vision - Short Range: circle distance=10.0 ``
| ``Lowlight: circle x2 ``
| ``Darkvision: circle r60 ``
| ``Square Vision: square ``
| ``Normal: circle ``

.. raw:: html

   <div style="color:gray">

Each of those items defines a **Sight Type**. The sight type is defined
using a specific syntax, explained in the Campaign Properties window.
The most basic one is simply a shape, as in:

.. raw:: html

   </div>

各項目が **Sight
Type（視界タイプ）**\ の定義だ。視界タイプはキャンペーンプロパティ・ウィンドウ下部で説明されている専用の書式で記述する。最も基本的な設定は、次のように形だけを記述する：

``Normal: circle``

.. raw:: html

   <div style="color:gray">

This simply says that "normal sight is circular." There is no limit to
the range except the vision distance set on the *Map itself*, which
defaults to 1,000 units.

.. raw:: html

   </div>

この記述は「通常の視界を円形に設定」ということだ。視界の届く距離は
MapTool で設定されている距離制限までだ（初期値は 1,000 単位）。

.. raw:: html

   <div style="color:gray">

A more complex entry is the one for "Lowlight" sight:

.. raw:: html

   </div>

「Lowlight」の項目はもう少し複雑だ：

``Lowlight: circle x2``

.. raw:: html

   <div style="color:gray">

In this case, the vision name is **Lowlight**, and the shape is
circular. However, an additional option was added on the end - *x2*.
This is an option that interacts with *light sources*, multiplying their
effective radius by 2 for any token that has the Lowlight vision. So
where a token with Normal vision might see 20 units when using a torch,
a token with Lowlight vision can see *40* units.

.. raw:: html

   </div>

この場合は、視覚の名前は **Lowlight** で、形は円形。しかし行末に
「\ *x2*\ 」 が書き加えられている。これは *light sources（光源）*
に関連するオプションであり、夜目を持つトークンに対する照明は2倍の輝きを持つようになる。通常の資格を持つトークンが松明（torch）を灯すと20単位の距離を見通せるが、夜目を持つトークンは40単位を見通す。

.. raw:: html

   <div style="color:gray">

Looking at an even more complex entry, consider the one for
"Darkvision":

.. raw:: html

   </div>

「Darkvision」の項目はさらに複雑になる：

``Darkvision: circle r60``

.. raw:: html

   <div style="color:gray">

In this entry, there are four components.

.. raw:: html

   </div>

この記述は4つの部品で成り立っている。

.. raw:: html

   <div style="color:gray">

-  **Darkvision**: this is, of course, the *name* of the Sight Type (you
   could call it "Thermographic Vision" if you like). This name appears
   in the token configuration dialog when you want to activate token
   sight.
-  **circle**: this signifies the shape of the visual area, in this
   case, indicating that the visual area is circular; we've seen this
   before.
-  **r**: this is a code that signifies that this sight type has a
   "personal" light source - in other words, it is effectively a light
   source only *that token* can see. This is what makes this
   "darkvision," for instance - the token can see just fine in the dark,
   but that token's *allies* might be completely blind.
-  **60**: this is the range of the sight type, starting from the center
   of the token's square, and counted in "map units" (so if your map is
   5 units per cell, this will cover 12 map cells; if your map is 1 unit
   per square, this will cover 60 squares). Note that since range is
   measured from the *center* of the square or hex, many users add a
   fractional amount to the range so that the end of the range lines up
   nicely with a hex or square boundary.

.. raw:: html

   </div>

-  **Darkvision**\ ：これまでと同じように、視界タイプの\ *名前*\ だ（サーモビジョンと名付けることもできる）。ここでつけた名称は、トークンの視覚を有効にしたときにトークンの設定ダイアログに表示される。
-  **circle**\ ：前述の通り、視覚が届く範囲の形状であり、この場合は円形の範囲であることを表している。
-  **r**\ ：この視界が「個人的な」光源を持つことを表す符号。つまり、\ *このトークン*\ だけが見ることのできる光源を持つということだ。「Darkvision」を持つと、仲間達が真っ暗闇の中で何も見えないときでも、このトークン自身は問題なく見通せるようになる。
-  **60**\ ：この視界タイプの有効距離。トークンの中心から「マップで使用している単位」で測る（マス目ごとに5単位を設定しているのであれば、12マスになる）。多くのユーザーは、マス目やヘックスの\ *中心*\ から距離を測るので、範囲を示す円がぴったりとマス目にくっつくように割り算した値を足している。

.. raw:: html

   <div style="color:gray">

Configuring sight types is unique to the game being played, and so the
specifics of it need to be left to the campaign designer. However,
suffice it to say that Sight is a configurable option and offers a great
deal of flexibility.

.. raw:: html

   </div>

視界タイプの編集は使用するゲームのルールごとに異なるので、キャンペーンを構成するには視界の仕様が必要になるが、視界は柔軟に設定できる多くのオプションを備えているので問題なく構成できるだろう。

視界タイプの制限
~~~~~~~~~~~~~~~~

.. raw:: html

   <div style="color:gray">

Flexible as it is, there are a few limitations on Token Sight.

.. raw:: html

   </div>

トークンの視界は柔軟ではあるが、いくつかの制限もある。

.. raw:: html

   <div style="color:gray">

-  **One sight type at a time**: tokens can only have one kind of sight
   active at a time (a token cannot have Darkvision and Normal sight
   active simultaneously)
-  **Sight has no color**: sight types do not have colors of their own.
   Any color visible to the players will be based on the color of the
   light source, not the sight type (there is one exception to this,
   however: in `MapTool Preferences <MapTool_Preferences>`__, you can
   opt to have the vision color of the token match its
   `Halo <token.halo>`__ color)

.. raw:: html

   </div>

-  **1度に1視界タイプ**\ ：トークンが同時に持てる視界は1種類だけ（トークンは暗視と通常の視覚を同時有効にできない）。
-  **視界は無色**\ ：視界は色を持たない。プレイヤーが見ている色は、光源の色であり、視界タイプの色ではない（\ `MapTool
   の設定でトークンの <MapTool_Preferences>`__\ `Haloの色と同じ色を視覚の範囲に着色できるオプションがある <token.halo>`__\ 。これを設定している場合は例外である）。

光源
----

.. figure:: Cprops-lighttab.png
   :alt: Cprops-lighttab.png

   Cprops-lighttab.png

.. raw:: html

   <div style="color:gray">

The Light tab provides an interface very similar to the Sight tab - a
text window with a number of different items defined as a simple string
of text. The default MapTool campaign properties show the following
light sources:

.. raw:: html

   </div>

照明のタブは、視界のタブと同じような、いくつかの項目がテキストで定義されているテキストエリアがある。MapTool
のキャンペーンプロパティの初期設定では光源は次のようになっている：

| ``D20``
| ``----``
| ``Candle - 5 : 5 10#000000 ``
| ``Lamp - 15 : 15 30#000000 ``
| ``Torch - 20 : 20 40#000000 ``
| ``Everburning - 20 : 20 40#000000 ``
| ``Lantern, Hooded - 30 : 30 60#000000 ``
| ``Sunrod - 30 : 30 60#000000 ``
| ``Generic``
| ``----``
| ``5 : 5 ``
| ``15 : 15 ``
| ``20 : 20 ``
| ``30 : 30 ``
| ``40 : 40 ``
| ``60 : 60 ``

グループ
~~~~~~~~

.. raw:: html

   <div style="color:gray">

In the above default lights, there are two groups: D20 and Generic. A
group is defined by typing its name, and placing beneath it four hyphens
in a row: . Groups appear in the right-click menu on a token, and are
basically a way for you, as GM, to organize the different light sources
in your game.

.. raw:: html

   </div>

上記の標準の照明設定では、D20 と Generic
の二つのグループがある。グループを定義するには、まずグループの名称を書き、そのすぐ下の行にのように4つのハイフンを書く。グループは基本的には異なる光源を分かりやすく分類するために使うもので、トークンの右クリックメニューに表示される。

`Aura <Aura>`__ is not included by default and must be added manually.

`Aura <Aura>`__ は標準では含まれていないので自分で追加する必要がある。

光源の書式
~~~~~~~~~~

Beneath each group header are a list of light sources. The syntax for
these is very similar to the syntax for Sight Types, with a couple
exceptions. Let's look at the entry for Sunrod:

グループ見出しの次の行には、光源の一覧がある。この書式は例外はあるが視界タイプの書式とよく似ている。Sunrod（陽光棒）を例に解説してみよう：

``Sunrod - 30: 30 60#000000``

.. raw:: html

   <div style="color:gray">

There are three elements shown here:

.. raw:: html

   </div>

この項目は次の3つの要素から成り立つ：

.. raw:: html

   <div style="color:gray">

-  **Sunrod - 30**: the name of the light source; this is what appears
   in the right-click menu on a token, under the appropriate Light
   Source group
-  **30**: this is a light source radius of 30 units; the "first" radius
   of the light
-  **60#000000**: this is a *second* radius to the light, and a
   hexadecimal color code.

   -  **Light Source Radii**: A light source can have one or more radii,
      each of which can be set to a different color. In the sunrod
      example, the first radius has no color (or rather, it has the
      default color of white, which means that the area it covers is
      completely illuminated). The second radius (60) has the color
      #000000, which, when rendered by MapTool, makes a "dim light" area
      (translucent gray) from 30 units to 60 units. The overall effect
      is that from the center of the light source out to 30 units, the
      light is "bright," and everything is fully illuminated. From 30
      units to 60 units, the light is a big darker, and items in that
      area are less brightly lit.

.. raw:: html

   </div>

-  **Sunrod -
   30**\ ：光源の名称。この名称はトークンの右クリックメニューの中の、所属する光源グ
   ループの下に表示される。
-  **30**\ ：この数字は光源の半径が30単位であることを示す。照明の「最初」の半径だ。
-  **60#000000**\ ：これは照明の「二つ目」の半径と16進数の色コードだ。

   -  **光源の複数の半径**\ ：光源には複数の半径を持たせることができ、それぞれ異なる色を指定できる。こ
      の例では、最初の半径は色がない（厳密にいえば、標準色の白であり、照明がカバーする範囲は完全に照られるということだ）。二つ目の半径「60」は色コー
      ド「#000000」 を持ち、MapTool
      は30単位から60単位までを「薄暗い照明」の範囲（半透明の灰色）として描画する。全体の効果は光源の中心より30単位の「明るい光」が占め、そこにあ
      るものはすべて照らされる。30単位から60単位の範囲では、照明がかなり暗くなるので薄暗く照らされる。

.. raw:: html

   <div style="color:gray">

One element is left out here, which is the light source *shape.* Like
Sight Types, light sources can have shapes. The default shape is
circular, and so if you do not specify a shape, the light source will
default to circle-shaped. The other shapes are:

.. raw:: html

   </div>

上記に加えて、\ *形状*\ の要素がある。視界タイプと同じように、光源も\ *形*\ を選べる。標準の形状は円形なので、形状を指定しなけば円形になる。他の形状は次のとおり：

.. raw:: html

   <div style="color:gray">

-  **Cone**: create a conic area with a user-defined arc. This projects
   the light along the current facing of the token.
-  **Square**: this creates a square light area
-  `Aura <Aura>`__: this is a special light source, because while it is
   blocked by VBL and can cast colored light, it does not actually
   illuminate anything (therefore, an `aura <aura>`__ will not reveal
   hidden areas to a player, but it does act as a way to see how far
   from a token its aura extends).

.. raw:: html

   </div>

-  **Cone**\ ：ユーザーが定義した形状で、円錐状の範囲を作る。トークンの向いている方向に
   光を放つ。
-  **Square**\ ：正方形の照明を作る。
-  `Aura <Aura>`__\ ：
   これは特殊な光源であり、通常の照明と同じように遮光域に阻まれ、色をつけることができるが、実際には何も照らさない（そのため、\ `auraは隠されている部分を明らかにすることはないが <aura>`__\ 、トークンが放つオーラが
   どこまで伸びているかを視覚的に表すことができる）。

トークンやオブジェクトに視界と照明を設定する
--------------------------------------------

.. figure:: Token-config-sight.png
   :alt: Token-config-sight.png

   Token-config-sight.png

.. figure:: Token-config-light.png
   :alt: Token-config-light.png

   Token-config-light.png

.. raw:: html

   <div style="color:gray">

To give a token Sight and Light, do the following:

.. raw:: html

   </div>

トークンに視界と光源を設定する方法は次のとおり：

.. raw:: html

   <div style="color:gray">

#. Double-click on the token and go to the Config tab. There, check the
   Has Sight box, and select the appropriate sight type. Remember that a
   token can only have one type of sight active at a time.
#. Click **OK** to save the sight settings.
#. Right-click on the token, and go to Light Source. Navigate through
   the submenus until you can select a specific light source. The token
   now has a light source.

.. raw:: html

   </div>

#. トークンをダブルクックして、Config タブを開く。Has Sight
   のチェックボックスをチェックし、適切な視界タイプを選択する。トークンは一度に1種類の視界タイプしか持てないことを忘れないように。
#. **OK**\ をクリックして視界の設定を保存する。
#. トークンを右クリックし、光源を選択。サブメニューを開き、いずれかの光源を選択する。これでトークンは光源を持つようになる。

視覚モード
==========

.. figure:: Map-vision-mode.png
   :alt: Map-vision-mode.png

   Map-vision-mode.png

.. raw:: html

   <div style="color:gray">

Recent builds of MapTool introduced the concept of Vision Modes, which
let the GM dictate how vision and light will affect a given map. There
are three Vision Modes: **Off**, **Day**, and **Night**, each of which
alters the way in which light and vision interact for a token.

.. raw:: html

   </div>

最近ビルドされた MapTool
は、視覚と照明がマップにどのように影響を与えるかGMが指定できる、視覚モードの機能を取り入れた。視覚モードは
**Off（なし）**\ 、\ **Day（昼）**\ 、\ **Night（夜）**
の3つがあり、照明と視界がトークンに与える影響はそれぞれ異なっている。

.. raw:: html

   <div style="color:gray">

In the following discussion of vision modes, what is visible to the
player as they move their token is based on what is visible to the
*token itself*. Thus, if, under the proper settings, an enemy token is
visible to the player's token, the player will see it on the Map.
However, if that enemy token is *not* visible to the player's *token*,
it will not appear on the player's instance of MapTool.

.. raw:: html

   </div>

下記の視覚モードの説明では、プレイヤーがトークンを操作する際に何が見えるかは、トークンそのものから見えるものに基づいている。そのため、適切な設定のもとでは、敵のトークンがプレイヤーのトークンから見えるなら、プレイヤーはマップ上で敵のトークンを見ることができる。そして、敵のトークンがプレイヤーのトークンから見えないのであれば、MapTool
の画面に敵は表示されなくなる。

Off（なし）
-----------

.. raw:: html

   <div style="color:gray">

When Map Vision is set to "Off," Token vision settings are not taken
into account when displaying information to players: all things are
visible at all times, unless hidden beneath Fog of War.

.. raw:: html

   </div>

「Map →
Vision」の設定を「Off」にした場合、トークンの視覚の設定はプレイヤーに表示する情報に対して影響を与えない。不明領域の下にあるもの以外は全て表示される。

Day（昼）
---------

.. raw:: html

   <div style="color:gray">

In Day mode, light sources are not considered when evaluating token
vision and what lies inside the tokens visual range. Furthermore, no
part of the map is hidden from the players (that is, they will see the
entire map - not necessarily all the *tokens* on a map, but they will
see the layout of the entire dungeon, building, or area). Effectively,
the Day mode assumes that a bright sun is shining down on everything,
illuminating it all, and everything is visible unless blocked by VBL or
covered by Fog of War.

.. raw:: html

   </div>

昼のモードでは、トークンの視覚と視覚が届く距離を決める際に、光源は考慮されない。さらに、マップ上でプレイヤーに隠される場所はなくなる（つまり、マップの全てを見ることができる。全てといっても、必ずしもマップ上の全ての\ *トークン*\ が見えるとは限らないが、ダンジョンや建物の間取りや区画の配置などは見ることができる）。事実上、昼モードは太陽の光が全ての場所に降り注ぎ、全てを照らしているのと同じ状態であり、遮光域に阻まれていない限り、また不明領域に覆われていない限り、全てのものが表示される。

Night（夜）
-----------

.. raw:: html

   <div style="color:gray">

This mode incorporates Light Sources into the calculations, effectively
assuming that it is "night" in the game, and that without a light
source, the tokens are in a pitch-black environment and can see nothing.
If Fog of War is used with Night Mode, light sources will reveal areas
covered by Fog of War, assuming a token can see the light source and the
area is not blocked by VBL.

.. raw:: html

   </div>

このモードは計算に光源が組み込まれており、ゲーム内の「夜」を効果的に再現しており、暗闇の環境化にいる光源を持たないトークンは何も見えなくなる。夜モードで不明領域を使用すると、光源は不明領域に覆われている場所を明らかにし、トークンは光源で照らされ遮光域で阻まれていない場所を見ることができる。

視覚モードと不明領域
--------------------

.. raw:: html

   <div style="color:gray">

You can use Fog of War with any of the Vision modes: Off, Day, or Night.

.. raw:: html

   </div>

不明領域はどの視覚モード（なし、昼、夜）でも使える。

.. raw:: html

   <div style="color:gray">

-  When Map Vision is Off, Fog is removed to the extent of the token's
   sight (set using the Token Properties dialog). Soft Fog does not
   appear when using Off Mode, as tokens do not actually "see" anything
   in this mode. VBL works normally.
-  In Day Mode, the Fog will be removed out to the limit of the token's
   visual range (which, if you note when you create a map, defaults to
   1,000 units), and token vision is blocked by VBL. In this mode, Fog
   of War has both Hard and Soft Fog, as token vision is active.
-  In Night Mode, Fog of War (when removed) is cleared to the maximum
   radius of a token's light source (remember, though - the token must
   a) have sight, and b) have a light source - without a light source,
   the token can't see at all!). Thus, when using Fog of War and Night
   mode for vision, the fog will be removed only where the light source
   illuminates it. Soft Fog works in this mode just as it works in Day
   mode.

.. raw:: html

   </div>

-  マップの視覚モードが「Off」の場合、トークンの視界が広がる範囲の不明領域は取り除かれる（トークンプロパティ・ダイアログで設定）。「Off」モードでは、トークンが「実際に見ていない」場所に半透明の不明領域が表示されることはない。遮光域は通常通り機能する。
-  昼モードでは、不明領域はトークンの視覚の届く最大距離（マップ作成時に設定したものか、初期設定の1,000単位）まで取り除かれる。遮光域はトークン
   の視覚を遮る。トークンの視覚を有効にしたとき不明領域は完全なものと半透明なものがありうる。
-  夜モードでは、不明領域は光源の届く範囲まで取り除かれる（トークンは、視界を持ち、かつ光源を持っていなければならないことを忘れないように。光源を持たないトークンは何も見ることはできない!!）。そのため、不明領域と夜の視覚モードを使用する場合、不明領域が取り除かれる範囲は照明に照らされている場所だけである。半透明の不明領域は昼モードと同じように機能する。

ゲームでの視界と照明
====================

.. raw:: html

   <div style="color:gray">

Sight, Light, and Fog interact in a number of ways in-play. To start,
let's look at using Sight without Light or Fog of War. The examples
below will use the sample dungeon shown to the right. Note that the
sample dungeon uses `Vision
Blocking <Introduction_to_Vision_Blocking>`__, a feature of MapTool that
blocks the line of sight of a token (meaning you can use it to indicate
the placement of walls, pillars, and similar objects that would obstruct
a character's vision).

.. raw:: html

   </div>

視界、照明、不明領域はプレイ中にさまざまな方法で相互に関係し合う。まず、照明と不明領域のことは考えず、視界について説明していこう。下記の例では右のサンプルダンジョンを使用する。なお、このサンプルダンジョンはトークンの視線を遮る
MapToo
の\ `遮光域の機能を使っている <Introduction_to_Vision_Blocking>`__\ （遮光域は、壁や柱などキャラクターの視覚を遮るさまざまなものを再現する機能）。

視程
----

.. figure:: Nofog-sight-boundary.png
   :alt: Nofog-sight-boundary.png

   Nofog-sight-boundary.png

|Nofog-sight-boundvbl.png|\ を使ったマップでは視界の境界線は遮光域に沿って表示される。]]

.. raw:: html

   <div style="color:gray">

When you configure a token to have sight, when you hover your mouse
token over the token, MapTool will illustrate the limit of the token's
visual range with a white border (a circle if the sight type is
circular, or square if square, or a cone if it's cone shaped, etc.). The
screenshot to the right shows a PC token with the sight type "Normal -
Short Range" configured. Note the white circle indicating the boundary
of the token's vision.

.. raw:: html

   </div>

トークンが視界を持つように設定して、トークン上にマウスカーソルをかざした場合、MapTool
はトークンの視覚が届く範囲を白い境界線を使って表示する（視界タイプが円形なら円形、正方形なら正方形、円錐状であれば円錐状の形状で）。右のスクリーンショットには「Normal
- Short
Range」の視界タイプを持つPCトークンが表示されている。白い円はトークンの視程を表すものだ。

.. raw:: html

   <div style="color:gray">

In the first screenshot to the right, there is no VBL on the map, so the
token's visual range is unaffected. For a more practical illustration of
the "line of sight" boundary, consider the second screenshot, taken
using the same token, but on the dungeon map, which employs VBL along
the the walls of the dungeon. If you look closely, you'll see the white
boundary - however, instead of being circular, it is blocked in certain
areas by the VBL of the map, and thus has an irregular shape.

.. raw:: html

   </div>

最初のスクリーンショットでは、遮光域を使用していないマップであり、そのためトークンの視程に影響はない。二つ目のスクリーンショットでは、同じトークンを、壁に沿って遮光域を置いたダンジョン・マップの中で使い、より実用的な「視線」を表す境界線を実演したものだ。よく見ると、円形の境界線ではなく、遮光域を配置した個所に遮られいびつな形をした白い境界線が見えるはずだ。

視覚モードと視界
================

.. raw:: html

   <div style="color:gray">

As mentioned above, there are three vision modes - **Off**, **Day**, and
**Night**. Each setting affects how token vision is evaluated by
MapTool.

.. raw:: html

   </div>

前述のとおり、視覚モードには\ **Off**\ 、\ **Day**\ 、\ **Night**\ の3種類がある。それぞれ
MapTool がトークンの視界を演算する方法に影響を与える。

視覚モード「Off」のときの視界
-----------------------------

.. figure:: Nofog-visionoff-gmview.png
   :alt: Nofog-visionoff-gmview.png

   Nofog-visionoff-gmview.png

.. figure:: Nofog-visionoff-plyrview.png
   :alt: Nofog-visionoff-plyrview.png

   Nofog-visionoff-plyrview.png

.. raw:: html

   <div style="color:gray">

When Vision is set to **Off**, the token's sight settings are not taken
into account when deciding what to display to the player. Instead, the
player can look at all of the items and backgrounds on the map. VBL will
still block the "visual boundary", but it won't actually block vision in
any way - something on the far side of VBL from a token is still visible
on the player's screen.

.. raw:: html

   </div>

視覚モードを\ **Off**\ にした場合、プレイヤーが見える範囲を決定する際、トークンの視界の設定は考慮されない。プレイヤーはマップ上の全てのアイテムと背景を見ることができる。遮光域は「視程の境界線」を遮りはするが、実際のトークンの視覚を妨げることはない。遮光域を挟んでトークンの反対側にあるものは、プレイヤーの画面にしっかり表示される。

.. raw:: html

   <div style="color:gray">

The two screenshots to the right illustrate this: the top screenshot is
the GM's view of the screen, while the shot on the bottom is the
Player's view of the same map - note that they both see the same items.
The only items a player will not see are those items on the Hidden
layer, or those items that the GM has explicitly flagged as invisible to
players.

.. raw:: html

   </div>

右にある二つのスクリーンショットは次のことを表している。上のスクリーンショットはGM側の表示であり、下は同じマップのプレイヤー側の表示である。両者とも同じものが表示されことがわかるだろう。プレイヤーに表示されないものは、Hidden
レイヤーに配置されたアイテムか、GMが意図的に「プレイヤーに非表示にする」設定を行ったものだけである。

.. _視覚モードday昼の_ときの視界:

視覚モード「Day（昼）」の ときの視界
------------------------------------

.. figure:: Nofog-visionday-gmview.png
   :alt: Nofog-visionday-gmview.png

   Nofog-visionday-gmview.png

.. figure:: Nofog-visionday-plyrview.png
   :alt: Nofog-visionday-plyrview.png

   Nofog-visionday-plyrview.png

.. raw:: html

   <div style="color:gray">

When Vision is set to **Day**, the token's sight settings are take into
account when determining what objects and other tokens are visible to
the player. Light source settings are *not* taken into account. If an
object or token lies outside the player's token's vision, it will not be
visible to the player. Likewise, if an object or token lies beyond VBL
from the player token, it will not be visible.

.. raw:: html

   </div>

視覚モードを\ **Day（昼）**\ に設定した場合、オブジェクトや自分以外のトークンがプレイヤーに表示されるかどうか決定する際にトークンの視界の設定が影響を与える。光源の設定は影響を\ *与えない*\ 。プレイヤーのトークンの視覚の外側にあるオブジェクトやトークンは表示されない。同じように、遮光域の向こう側にあるオブジェクトやトークンも表示されない。

.. raw:: html

   <div style="color:gray">

The screenshots to the right show this (again, the top is the GM's view,
and the bottom is the Player view). Note that in the player view, the
Dragon and Hero token are not visible to the Elf token (the player
token), because they are hidden by VBL.

.. raw:: html

   </div>

右側のスクリーンショット（上：GM表示、下：プレイヤー表示）は以上のことを再現したものだ。プレイヤー表示では、ドラゴンとヒーローのトークンは遮光域に遮られているのでエルフのトークンから見えていないことが見て取れる。

.. _視覚モード_night夜の_ときの視界:

視覚モード 「Night（夜）」の ときの視界
---------------------------------------

.. figure:: Nofog-visionnight-gmview.png
   :alt: Nofog-visionnight-gmview.png

   Nofog-visionnight-gmview.png

.. figure:: Nofog-visionnight-plyrview.png
   :alt: Nofog-visionnight-plyrview.png

   Nofog-visionnight-plyrview.png

.. figure:: Nofog-visionnight-plyrview-candle.png
   :alt: Nofog-visionnight-plyrview-candle.png

   Nofog-visionnight-plyrview-candle.png

.. raw:: html

   <div style="color:gray">

When vision is set to **Night**, both the token's sight settings *and*
the token's light source setting is taken into account when determining
what the token is able to see. If a token lacks a light source, it will
be unable to see anything unless it has a sight type that indicates
*personal light* (in other words, a sight type like the "Darkvision"
type discussed previously) - in fact, the token itself will not be
visible to the player!

.. raw:: html

   </div>

視覚モードを\ **Night（夜）**\ に設定した場合、トークンの視界の設定とトークンの光源の設定は、トークンが何を見ることができるか決定する際に両者とも影響を与える。光源を持たないトークンは、\ *本人のみ有効な照明*\ （前述の「暗視」のような視界タイプのことだ）を持つ視界タイプを持っていない限り何も見ることができず、トークン自体もプレイヤーに表示されない。

.. raw:: html

   <div style="color:gray">

The screenshots to the right show Night-mode vision in effect. The top
screenshot is the GM view; the second two show the Player view *without*
a light source on the player's Elf token, and then with the "Candle - 5"
light source selected. There are several things to note about this:

.. raw:: html

   </div>

右のスクリーンショットは視覚モード「夜」の場合のものだ。上はGM側の表示のスクリーンショット。二つ目はプレイヤーのエルフ・トークンが照明を持っていない場合のプレイヤー側の表示。その下はエルフトークンに「Candle
-
5」の光源を設定したときのプレイヤー表示だ。このスクリーンショットには次にあげる良く見てもらいたいことがある：

.. raw:: html

   <div style="color:gray">

#. "Night" mode vision does not add "darkness" to the map in any visual
   way - it simply means that without a light source, tokens cannot see
   other tokens, objects, or themselves.
#. In the first Player screenshot, the player's Elf token is not visible
   in the lower left room of the dungeon - that's because the player's
   token doesn't have a light source, so it can't see - and therefore,
   the *player* can't see anything but the map background.
#. In the second Player screenshot, the Elf is now visible because it
   has a light source active. This light source means that the player
   can see out to the limit of its light source's area.

.. raw:: html

   </div>

#. 「夜」の視覚モードは視覚的にマップに「暗闇」を追加しているのではなく、単に光源がないため、他のトークン、オブジェクト、トークン自身を見ることができないということだ。
#. 1枚目のプレイヤー側のスクリーンショットでは、ダンジョンの左下にいるプレイヤーのエルフ・トークンは表示されていない。このトークンは照明を持っていないので何も見ることができない。そのため、\ *プレイヤー*\ もマップの背景以外は何も見ることができない。
#. 2枚目のプレイヤー側のスクリーンショットでは、照明の設定が有効になったのでエルフが見えるようになった。プレイヤーが光源の届く範囲まで見えるようになるために、この光源が重要な役目をはたしている。

.. raw:: mediawiki

   {{Languages|Introduction to Lights and Sights}}

`Category:MapTool <Category:MapTool>`__
`Category:Tutorial <Category:Tutorial>`__

.. |Nofog-sight-boundvbl.png| image:: Nofog-sight-boundvbl.png
