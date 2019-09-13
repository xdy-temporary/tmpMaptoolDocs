{{\#customtitle:はじめての遮光域|はじめての遮光域}} __TOC__

## 遮光域（Vision Blocking）

<div style="color:gray">

In MapTool, [tokens](Token:token "wikilink") can be given
[sight](Introduction_to_Lights_and_Sights "wikilink"), which lets the
program model vision and lighting in-game. In other words, when you
configure the token with vision, it can then "see" other tokens and
areas of the map. In addition, MapTool provides for
[lighting](Introduction_to_Lights_and_Sights "wikilink") - so a token
can "see" only to the extent of its light source (or nearby light
sources) - and Vision Blocking, which lets you establish boundaries to
the token's visual range (so you can indicate where the walls are in a
dungeon, for instance).

</div>

MapTool
では、[トークンにプログムラムがゲーム内での視覚と照明を再現した](Token:token "wikilink")[視界を与えることができる](Introduction_to_Lights_and_Sights "wikilink")。つまり、トークンが視覚を持つように設定することで、他のトークンやマップの範囲を「見る」ことが可能となる。さらに、MapTool
は照明の機能（トークンは光源の及ぶ範囲や光源の近くでなければ「見る」ことはできない）と遮光域の機能（トークンの視程を遮る境界を設置できる。この機能によりダンジョンの壁を再現することが可能だ）を備えている。

<div style="color:gray">

This introductory element will briefly review the Vision Blocking Layer
tools in MapTool (sometimes also called *topology* tools), and how to
use them to create a sample dungeon environment. Remember, Vision
Blocking is intimately connected to the **Sight**, **Light**, and **Fog
of War** features of MapTool, so once you've read this tutorial, go
check out the [Introduction to Lights and
Sights](Introduction_to_Lights_and_Sights "wikilink") and see how it all
works together\!

</div>

このガイドでは MapTool
の遮光域レイヤー・ツール（*地形学*ツールとも言う）について簡単に紹介し、この機能を使いサンプルのダンジョンの環境を作る方法を紹介する。重要なことだが、遮光域機能は**視界（Sight）**、**照明（Light）**、**不明領域（Fog
of War）**の各機能と密接に関係している。理解を深めるために [Introduction to Lights and
Sights](Introduction_to_Lights_and_Sights "wikilink") を併せて読むことをお勧めしよう\!

### 手始めにマップを用意する

![samp-dungeon.png](samp-dungeon.png "samp-dungeon.png")

<div style="color:gray">

To start off, we'll need a map of a dungeon. Somewhere suitably
subterranean and dank, full of twisty little passages, all alike.

</div>

さて、はじめる前に我々にはマップが必要だ。じめじめとしていて、何か出そうで、くねくねとした小さな通路に満ちあふれた、何の変哲も無いソレが転がってないだろうか？

<div style="color:gray">

Well, maybe we won't get too crazy with the mazes of twisty passages.
Created using an [awesome
tileset](http://forums.rptools.net/viewtopic.php?f=34&t=7418) created by
Jonathan Roberts (Torstan on the [RPTools
Forums](http://forums.rptools.net)), the map shown to the right will be
used for the examples in this introductory tutorial.

</div>

まあ、別にアホほど曲がりくねった迷路を探す必要はない。右に見えるマップをこのチュートリアルの実例として使用していこう。このマップは
Jonathan Roberts ([RPTools Forums](http://forums.rptools.net) では Torstan
として出会える）の作った[見事なタイルセット](http://forums.rptools.net/viewtopic.php?f=34&t=7418)を使って作り上げたものである。

## 遮光域ツールを有効にする

![Vbl-toolbar-btn.png](Vbl-toolbar-btn.png "Vbl-toolbar-btn.png")

![Vbl-tools.png](Vbl-tools.png "Vbl-tools.png")

<div style="color:gray">

To activate the Vision Blocking Tools, click on the "Eye" icon in the
MapTool toolbar. (eye icon screenshot). When you do so, a new set of
buttons will appear - these are the various Vision Blocking drawing
tools you can use. If you hover over them, a tooltip will pop up
explaining what each one does. From left to right, they are:

</div>

遮光域ツールを有効にするには、MapTool
のツールバーにある「目」のアイコンをクリックする（スクリーンショット参照）。そうすることで、新しいボタンの集まりが表示される。このボタンの集まりは遮光域を描画するためのさまざまなツールだ。ボタンの上にマウスカーソルをかざすことでそれぞれの機能を説明するツールチップが表示される。各ボタンは左からそれぞれ：

<div style="color:gray">

  - **Draw a Rectangular VBL**: this creates solid rectangular areas
    that block vision (these are generally called Vision Blocking
    Layers, or "VBL" for short). . Tokens outside the area cannot see
    into it or through it; tokens inside the area cannot see anything at
    all (it is solid and opaque).
  - **Draw a Hollow Rectangular VBL**: this, as it implies, creates
    hollow VBL - if a token is *inside* the area, they will see
    everything inside it, but will not be able to see *beyond* the
    boundary; for tokens outside the VBL area, they will see everything
    outside, but cannot see *into* the rectangular area.
  - **Draw a Circular VBL**: like the rectangular one, this creates a
    circular (in reality, a polygon approximating a circular area;
    actual circular curves are performance-intensive\!) VBL
  - **Draw a Hollow Circular VBL**: behaves like the hollow rectangle
  - **Draw Closed Poly Line VBL**: this lets you draw an arbitrary
    polygonal shape using line segments, and when finished, closes it
    and makes a solid VBL out of it. To start the polyline shape,
    left-click on the map, and draw the first segment. To attach the
    next segment, *right-click* and move the mouse to create the next
    line segment. When finished with the full shape, left-click to close
    it.
  - **Draw Poly line VBL**: as above, but creates a hollow polygon

</div>

  - **長方形遮光域を描画**：視覚を遮る塗りつぶされた長方形（遮光域と呼ばれている物）を
    描画する。この範囲の外側にいるトークンは範囲の内側や向こう側は見えない。範囲の内側にいるトークンは何も見えなくなる（この中は不透明で隙間なく塗りつぶされている）
  - **枠状の長方形遮光域を描画**：遮光域の囲いを描画する。描画された範囲の*内側*にいるトークンは内側にあるものをどれでも見ることができるが、境界線を越えた向こう側は見ることができない。遮光域の外側にいるトークンは、外側にあるものを見ることができるが、長方形の内側を見ることはできない。
  - **円形遮光域を描画**：長方形の物と同様であるが、こちらは円形の遮光域（正確には、円に近似する多角形である。正確な円は処理速度に影響してしまう\!）を描画する。
  - **枠状の円形遮光域を描画**：円形であることを除いて「塗りつぶされてない長方形の遮光域」と同じ物だ。
  - **多角遮光域を描画**：直線を繋いで自由な多角形を描画し、描き終えると図形を閉じて塗りつぶされた遮光域を作る。多角形を描き始めるにはマップ上で左クリックをし、最初の線分を描画する。次の直線を繋げて描画するには*右クリック*して次の線分を描画するためにマウスを動かす。多角形が完成したら左クリックして図形を閉じる。
  - **折れ線遮光域を描画**: 上記と同じだが、枠線のみの遮光域を描画する。

### 模範的な使い方

<div style="color:gray">

Vision blocking and vision processing is processor-intensive, and
overuse of (or overly-complex) VBL can cause serious performance issues
with MapTool - slowdowns, inability to navigate a map, and so forth.
Some rules of thumb:

</div>

遮光域と視覚は処理速度に影響を与え、遮光域を過度に使用すること（又は過度な複雑に使うこと）は MapTool
に処理速度の低下、マップの制御不能など、さまざまな不具合を引き起こすことになる。次のことを守っていればまず大丈夫だろう：

<div style="color:gray">

1.  **Use square VBL wherever possible** - and minimize the use of
    circular or highly irregular VBL
2.  **Use solid VBL wherever possible** - this prevents gaps between
    polylines, which can be performance hogs. Instead, cover the map
    with VBL, and cut out the areas that the tokens should be able to
    see.
3.  **Use as little VBL as necessary to get the effect you seek** - make
    it efficient\!
4.  It is frequently a good idea to set up a vision boundary at the
    edges of the play area on your map - maps in MapTool are
    theoretically infinitely sized, but if your tokens are going to be
    only in the dungeon area, there's no reason for MapTool to have to
    be calculating what they see all the way out to the edge of the
    universe.

</div>

1.  **可能な限り長方形の遮光域を用いる** - 円形や複雑な形状の遮光域の使用は最小限にとどめる。
2.  **可能な限り塗りつぶされた遮光域を用いる** -
    線と線の間に生じる隙間は処理速度に大きな影響を与えるが、こうすることで防ぐことが可能だ。むしろマップを遮光域で覆いつくし、トークンが動き回る範囲だけ切り取るようにすべきだ。
3.  **狙った効果を再現するのに必要な最低限の数だけ遮光域を使用する** - 無駄なく効率的に\!
4.  マップの中でゲームで使う範囲を遮光域で囲むことは、よく使われるよく有る冴えたやり方だ。理論上、MapTool
    のマップは無限の広さを持っているが、結局のところ君のトークンはダンジョンに潜ってしまうので、世界の果てまでの視覚計算をする必要はどこにもないのだ。

<div style="color:gray">

These will help keep performance from bogging down. You *can* use the
other kinds of VBL, but simply be aware of how complex your vision
blocking setup is getting.

</div>

以上のことは煩わしい処理落ちを防ぐ助けとなるだろう。君はあらゆる種類の遮光域を*使用することができる*が、構築した遮光域の複雑さには気をつけるように。

## サンプルマップに遮光域レイヤーを配置する

<div style="color:gray">

Now, to add some vision blocking to the map. We will use a recommended
technique, which is to cover the entire map with a solid block of VBL,
and then "cut out" of that block the areas that the players will see.

</div>

ではマップに遮光域を追加してみよう。ここでは、マップ全体を塗りつぶされた遮光域で覆い、プレイヤーが探索する予定の範囲を「くり抜く」、という推奨された方法を使用する。

### ダンジョン全体を塗りつぶされた遮光域で覆う

![Vbl-map-zoomed-extents.png](Vbl-map-zoomed-extents.png
"Vbl-map-zoomed-extents.png")

![Vbl-createsolidvbl.png](Vbl-createsolidvbl.png
"Vbl-createsolidvbl.png")

<div style="color:gray">

1.  Zoom the map so you can see the whole thing.
2.  Select the Draw a Rectangular VBL button.
3.  Left-Click to place the upper-left corner of the solid VBL. Do not
    hold down the left-mouse button.
4.  Drag the mouse to define the size of the VBL. You'll see it traced
    out in a transparent red color as you drag.
5.  Click the left mouse button again to place the lower-right corner of
    the VBL. The VBL will turn blue (if you go to the toolbar and select
    one of the other tools on the left side - switching off the VBL
    tools - the blue VBL indicators will disappear. They are only
    visible when the VBL tools are active).

</div>

1.  全体が見渡せるまでマップの表示を縮小する
2.  「長方形遮光域を描画（Draw a Rectangular VBL）」のボタンを選択
3.  塗りつぶされた遮光域の左上角に当る地点を左クリック。マウスの左ボタンは押したままにせず離す。
4.  マウスを動かして遮光域のサイズを決定する。マウスの移動に従い半透明の赤い長方形が描かれていくはずだ。
5.  遮光域の右下角に当る地点でマウスを左クリック。遮光域は青色に着色されるはずだ。（ここでツールバーの左側から他のツールを選ぶと、遮光域ツールが非表示になり、青い遮光域レイヤーが消えたように見える。遮光域の図形は遮光域ツールが有効な時のみ表示される）

![Vbl-complete-cover.png](Vbl-complete-cover.png
"Vbl-complete-cover.png")

<div style="color:gray">

You've now covered the entire map with VBL. If a token was placed
outside that area, and had a "sight" setting active, it would not be
able to see into that area.

</div>

これでマップ全体を遮光域で覆いつくした。「視界」の設定を有効にしてトークンをこの遮光域の外側に配置した場合、この範囲の中を見ることはできなくなる。

### 遮光域の塗りつぶしから表示する範囲をくり抜く

![Vbl-erasingvbl.png](Vbl-erasingvbl.png "Vbl-erasingvbl.png")

<div style="color:gray">

Now, we cut out the rooms. This process is a bit trickier - to keep the
VBL efficient, make sure you get the edges lined up as best you can and
you don't leave any narrow gaps or thin lines of VBL between rooms (a
trick to doing this is in the instructions below). For this part, I will
be clearing all VBL, out to the outer walls. We will work on the
interior walls later.

</div>

次は部屋をくり抜いていこう。この行程は少しばかりコツが要る。遮光域の効率を保つため、可能な限り最良の稜線を引いているか、部屋と部屋の間に細い隙間や遮光域の細い線が残っていないか確認すること（上手くやるコツは後述）。この行程では、外周の壁に沿って内側の遮光域を取り除く予定だ。内部の壁に付いては後ほど案内しよう。

<div style="color:gray">

1.  Zoom the map until you are comfortable with the zoom level.
2.  Select the Draw a Rectangular VBL tool.
3.  Hold down the Shift key, and left-click to mark the upper-left
    corner of the area of VBL you want to erase. A white, transparent
    box will follow the mouse cursor (if it's not white, you forgot to
    hold shift\!)
4.  Drag the mouse until you've reached where you want the lower-right
    corner of the cleared area to be, and left-click. The blue VBL will
    disappear. You have now erased the VBL for that area, and tokens in
    that area would be able to see (their vision would be blocked, of
    course, once it reached any VBL\!).
5.  Repeat this process for the rest of the rooms, tunnels, and so
    forth.

</div>

1.  作業しやすい大きさになるようマップを拡大する。
2.  「長方形遮光域を描画（Draw a Rectangular VBL）」ツールツールを選択。
3.  シフトキーを押しながら、消去したい遮光域の左上角に当る部分をクリックする。マウスの動きに伴い半透明の白い矩形が描画される。（シフトキーを押し忘れ
    ていると白くならない\!）
4.  消去したい範囲の右下角までマウスを動かし、左クリックすると、青い遮光域が消去される。この範囲の遮光域がなくなったので、ここに配置したトークンはこの場所を見ることができるようになる（もちろん、遮光域の向こう側を見ることはできない）。
5.  まだ残っている部屋やトンネルなどを、同じ作業を繰り返して作っていく。

![Vbl-erased.png](Vbl-erased.png "Vbl-erased.png")

<div style="color:gray">

Afterwards, you'll have a large blue area, with the dungeon "cut out"
inside it.

</div>

作業を終えると、ダンジョン型に「くり抜かれた」大きな青い図形が出来上がる。

<div style="color:gray">

**TIP**: if you hold down Ctrl while you trace your VBL, it will snap to
the gridlines of the map. This is very useful for aligning VBL. I used
this technique to erase the VBL on the sample map, because it makes the
VBL align easily and squarely on the dungeon walls.

</div>

**ヒント**：遮光域を編集するときにCTRLキーをを押すことでマップのグリッドに吸着するようになる。この機能は遮光域をきれいに描くのにとても役に立つ。このテクニックは遮光域をダンジョンの壁に沿って簡単に四角くくり抜ことができるので、前述のサンプルマップで遮光域をくり抜くのに使用している。

### 室内の遮光域

![Vbl-polyline-wall.png](Vbl-polyline-wall.png "Vbl-polyline-wall.png")

<div style="color:gray">

Finally, we will put VBL on the interior walls. This will make it so
that the walls *inside* the dungeon block vision too.

</div>

最後に、室内の壁に遮光域を作ろう。これでダンジョン内の壁が視覚を妨げるようになる。

<div style="color:gray">

1.  Zoom the map to focus on a particular wall.
2.  Select the "Draw Polyline VBL" tool.
3.  Hold down Ctrl, and left-click on the map to place the beginning of
    the line segment. I recommend starting the line somewhere in the
    solid VBL, so that there are no gaps at the edges of the walls.
4.  Drag the mouse to draw the line segment. (in the screenshot, the
    line segment is the thin red line inside the yellow circle; the
    yellow circle was drawn on the screenshot to show you where the
    polyline is - it's not part of the VBL process)
5.  Left-click to place the end of the line segment. The red line will
    turn blue, indicating that there is VBL now on that wall.
6.  Repeat the process for the other walls, until you are satisfied.

</div>

1.  作業対象の壁が中心になるようにマップを拡大する。
2.  「折れ線遮光域の描画（Draw Polyline VBL）」ツールを選択。
3.  マップ上の線分を引き始める場所をCTRLキーを押しながら左クリック。壁の付け根に隙間が生じないように遮光域の塗りつぶされたところから線を引き始めると良いだろう。
4.  マウスを動かし線分を描く。（スクリーンショットでは、黄色い丸の中の赤い細線。黄色い丸は折れ線を示すためにスクリーンショット上に描かれた物で、遮光域を描く作業中に表示されるわけではない）
5.  線分の終点にする場所を左クリック。赤かった線はお会い線に替わり、壁の遮光域を表している。
6.  あとは満足のいくまで壁を描く作業を繰り返す。

### 遮光域とオブジェクト

<div style="color:gray">

There are lots of objects in a dungeon that can block vision - doors,
pillars, piles of rubble, chests...you name it. It is possible to draw
VBL anywhere on a map - however, at this time, VBL is not linked to
particular objects. This means that you can't, for instance, put VBL on
a door and have it "open" with the door when your players open it. You
can simulate this by deleting the VBL that crossed the doorway, but you
can't have the VBL automatically move with an object.

</div>

ダンジョンの中には、扉、柱、瓦礫の山、宝箱、など数え上げればきりがないほど視覚を遮るオブジェクトが山ほどある。マップ上に遮光域を描けば視覚を遮ることはできるが、現状では遮光域はオブジェクトに連動していない。つまり、扉の上に遮光域を置いてもプレイヤーが扉を開けると同時に遮光域を動かすことはできないということだ。扉の入口に重なる遮光域を消すことで再現することはできても、オブジェクトの移動に併せて遮光域を自動的動かすことはできないのだ。

<div style="color:gray">

You'll have to experiment with the VBL for the objects in your dungeon,
but here are some tips:

</div>

いずれダンジョンの中でオブジェクト用の遮光域を作らざるを得なくなるであろうが、いくつか参考となるコツを教えよう：

<div style="color:gray">

  - **Doors**: for doors, if they are closed, simply draw the VBL along
    the wall in which the door sits. When (if) the door is ever opened,
    you can rotate the door object, and use Solid Rectangular VBL to
    erase the vision blocking layer that covered the doorway (remember,
    hold down Shift to erase VBL). Make sure to use *solid* VBL - if you
    use a hollow rectangle, it will only erase where the hollow
    rectangle's boundary intersects the other VBL.

</div>

  - **扉**：扉の場合、閉じているのであれば単に壁に沿って扉がある部分に遮光域を描けば良い。扉が開けられたのであれば、扉のオブジェクトを回転させ、塗りつぶし長方形遮光域を使って扉の入口に当る部分にある遮光域を消去すれば良い（遮光域を消すにはシフトキーを押すことを忘れないように）。枠状の長方形遮光域のを使うと枠線が他の遮光域と重なる部分だけが消去されて使い物ならないので、*塗りつぶし*遮光域を使うよう気をつけてくれ。

![Vbl-drawx.png](Vbl-drawx.png "Vbl-drawx.png")

<div style="color:gray">

  - **Pillars, statues, and standing objects**: remember that, when you
    use VBL, the tokens cannot see into or through it at all (and,
    because of this, the *players* won't see anything covered by or
    hidden inside VBL on their screens). If you want the players to be
    able to see some of an object - like a large pillar - one of the
    recommended tricks is to draw an "X" on the pillar using poly line
    VBL (instead of covering the whole pillar with a circular or
    rectangular solid VBL. Using an X means that the players can see
    some of the pillar, depending on where their tokens are. It makes
    for a much nicer look. If you look at the screenshot, you'll see an
    "X" drawn using VBL on top of one of the barrels.

</div>

  - **柱、石像など柱状のオブジェクト**：遮光域を使用時、トークンは遮光域の中も向こう側も見ることができない（そのため*プレイヤー*の画面上でも遮光域で隠されたり妨げられているものを見ることはできない）ことを覚えているだろうか。プレイヤーにあるオブジェクトを見せようとしたとき（例えば大きな柱）、（柱を囲うように円形や長方形の塗りつぶし遮光域を使う替わりに）折れ線遮光域を使い柱の上に「×」印を描くことをおすすめする。「×」印を使うことで、トークンの場所により形は変わるがプレイヤーは柱の一部を見ることができる。これならいくらかマシな表示であろう。スクリーンショットをよく見たのなら、1つの樽の上に「×」印の遮光域が描かれていることに気付くだろう。

## 遮光域の制限

<div style="color:gray">

The Vision Blocking Layer in MapTool is a tool for helping to simulate
what a character can see during a game. However, it does have
limitations, and doesn't "completely simulate vision" or anything like
that. We touched on one limitation earlier, the fact that VBL cannot be
attached to specific objects, and so if you open a door that is covered
by VBL - the door object might move, but the VBL stays put. Here are a
couple other limitations of the current (as of MapTool 1.3.b56) Vision
Blocking Tools.

</div>

MapTool
の遮光域レイヤーはゲームの中でキャラクターの視界を再現するツールだ。しかし、制限が有り、視覚を完全に再現するものではない。これまでに制限の1つに触れた。特定のオブジェクトに遮光域を付属させることはできない。そのため、遮光域に妨げられている扉を明けた場合、扉のオブジェクトは動かせても、遮光域はその場にとどまったままである。以下に遮光域ツールの現在の制限（MapTool
1.3.b56）を上げておく：

<div style="color:gray">

  - **Vision Blocking is Binary**: VBL in MapTool is on or off. There is
    no "partially transparent" or "one way" VBL in the current version
    of MapTool.
  - **Vision Blocking is Total**: Related to the above, VBL blocks all
    forms of vision. There are no vision types currently that can see
    through VBL.
  - **Vision Blocking has no Elevation**: VBL cannot at this point be
    given a particular height - it stretches to infinity, up and down,
    and so there's no way to set up VBL so a tall character can see
    "over" it

</div>

  - **遮光域はオン／オフいずれか**：MapToolの遮光域は「ある」か「ない」かだ。「半透明」や「一方通行」の遮光域は現状の
    MapTool には存在しない。
  - **遮光域は全て遮る**：上記に関連するが、遮光域は全ての種類の視覚を遮る。いかなる種類の視覚も現状の MapTool
    では遮光域を見通すことはできない。
  - **遮光域は高度を持たない**遮光域は特定の高さを持たない。つまり上にも下にも無限の長さを持っており、背の高いキャラクターが遮光域の向こう側を「見渡せる」ようにすることはできない。

[Category:MapTool](Category:MapTool "wikilink")
[Category:Tutorial](Category:Tutorial "wikilink")