.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{Languages|Introduction to Properties}}

{{#customtitle:はじめてのプロパティ|はじめてのプロパティ}}

.. _キャンペーンプロパティcampaign_properties:

キャンペーンプロパティ（Campaign Properties）
=============================================

.. raw:: html

   <div style="color:gray">

One of the most useful features in MapTool is the capability of
`tokens <Introduction_to_Tokens>`__ to carry around a set of
**Properties**, attached to that token, that can be manipulated by
macros and can be used to create quick displays of information.
Basically, token properties are like built-in character sheets.

.. raw:: html

   </div>

MapTool
の最も気の利いた機能の一つは、マクロで操作したり、情報のクイック表示を作成することが可能な\ **プロパティ**\ の集まりを\ `トークン自身に付属させ持ち歩かせることができることだ <Introduction_to_Tokens/ja>`__\ 。基本的にトークンのプロパティは
MapTool に組み込まれたキャラクター・シートのようなものだ。

.. raw:: html

   <div style="color:gray">

However, because they are so useful, the MapTool developers have created
many different ways to use them and manipulate them. This guide will
address creating Campaign Property Sets, setting them to have default
values, and using them to manipulate the Statsheet.

.. raw:: html

   </div>

ではあるが、便利な機能であるため MapTool
の開発陣はプロパティを使用したり操作したりする多くの異なる方法を作成してきた。このガイドでは、キャンペーンプロパティセット（Campaign
Property
Sets）を作ること、初期値を持つプロパティを作ること、作成したセットを使ってデータシート（Statsheet）を操作することに取り組む。

.. _サンプルルールセットまたは_mtrpg:

サンプルルールセット、または MTRPG
==================================

.. raw:: html

   <div style="color:gray">

In order to have useful examples as we move through this tutorial,
several MapTool users and contributors developed the `Sample
Ruleset <Sample_Ruleset>`__ -- a simple roleplaying game system
developed specifically to illustrate parts of MapTool. For this guide,
we're going to call these rules the MapTool RPG - or MTRPG for short,
and what we're going to do is create a new Campaign File and set up some
*campaign properties* that correspond to attributes of the MTRPG.

.. raw:: html

   </div>

このチュートリアルを案内する上で分かりやすい例を示すため、一部の MapTool
ユーザーと開発者は\ `サンプルルールセット <Sample_Ruleset>`__\ （特にMapToolの重要な要素を説明するために開発された簡単なロールプレイング・ゲーム・システム）を作り上げた。このガイドでは、このルールを
MapTool
RPG（もしくは略してMTRPG）と呼び、新しいキャンペーンファイルを作成し、MTRPGの特性に合う\ *キャンペーン・プロパティ*\ を設定していく。

キャンペーンプロパティウィンドウ
================================

.. figure:: Edit-campaign-props.png
   :alt: Edit-campaign-props.png

   Edit-campaign-props.png

.. raw:: html

   <div style="color:gray">

To get started with Campaign Properties, the first thing you'll need to
do is go to **Edit > Campaign Properties**, and open the Campaign
Properties window. In this window, you'll see several tabs and a whole
lot of information.

.. raw:: html

   </div>

まず、キャンペーンプロパティの作業を始めるために、\ **Edit → Campaign
Properties**
を選択し、キャンペーンプロパティウィンドウを開く。このウィンドウには、いくつかのタブと多くの情報がある。

.. raw:: html

   <div style="color:gray">

When you open up the **Campaign Properties** window, you'll see it has
six tabs. Briefly, they are:

.. raw:: html

   </div>

**キャンペーンプロパティ**\ のウインドウを開いときに6つのタブがあることに気付くだろう。それぞれのタブを簡単に説明しよう：

.. raw:: html

   <div style="color:gray">

-  **Token Properties**: this houses all the property sets that a token
   in the current campaign may have
-  **Repositories**: this is where you can designate an online
   "`repository <Introduction_to_Campaign_Repositories>`__" to hold
   campaign files, especially images, to improve load times and speed
   when you host or play an online game
-  **Sight**: this tab is where you configure the settings for vision in
   the current campaign
-  **Light**: this tab is where you configure light sources and auras
   for the current campaign
-  **States**: this tab lets you configure `token
   states <Token:state>`__ for the current campaign
-  **Bars**: this is where you configure `token bars <bar.name>`__ for
   the current campaign

.. raw:: html

   </div>

-  **Token
   Properties**\ ：キャンペーンで利用可能な全てのプロパティ・セットが収録されている。
-  **Repositories**\ ：キャンペーン・ファイル（特に、オンラインでのゲームを楽しむために読み込み時間を短縮するために）を取り入れるため、オンラインの「\ `リポジトリー <Introduction_to_Campaign_Repositories>`__\ 」を指定することができる。
-  **Sight**\ ：このタブで、現行のキャンペーンで使用する視覚の設定を編集する。
-  **Light**\ ：このタブで、現行のキャンペーンで使用する光源とオーラの設定を編集する。
-  **States**\ ：このタブで、現行のキャンペーンで使用する\ `トークン・ステータスを編集する <Token:state>`__\ 。
-  **Bars**\ ：ここでは、現行のキャンペーンで使用する\ `トークン・バーを編集する <bar.name>`__\ 。

.. raw:: html

   <div style="color:gray">

This guide will only address the first tab, **Token Properties**.

.. raw:: html

   </div>

このガイドでは、最初のタブ\ **Token Properties**\ だけに取り組む予定だ。

プロパティのタブ
================

.. figure:: Camp-props.png
   :alt: Camp-props.png

   Camp-props.png

.. raw:: html

   <div style="color:gray">

The first visible tab is the properties tab. This appears relatively
uncomplicated, but it's home to some really nifty potential. There are 3
text fields in this tab:

.. raw:: html

   </div>

最初に表示されるタブはプロパティのタブだ。ここに表示されているものは比較的単純なものであるが、出発点としてふさわしい要素を備えている。このタブには以下の3つのテキストフィールドが備わっている：

.. raw:: html

   <div style="color:gray">

-  Name: this is the name of the property set you're currently viewing.
   When you open the campaign properties window, this is blank.
-  Type: this column on the left side is not editable, but it will list
   the names of all the available property sets in the current campaign.
   If you have no campaign loaded, the only entry will be **Basic**
-  A large text area where you enter the properties for the current
   campaign. It will be blank when first loaded, but if you select a
   property set from the **Token Type** list on the left side, you will
   see the names and default values of the properties in that set.

.. raw:: html

   </div>

-  Name：現在表示しているプロパティ・セットの名称。キャンペーン・プロパティを開いたときは空白になっているはずだ。
-  Type：この左の列にあるものは編集することができないが、現行キャンペーンで使用可能な全てのプロパティ・セットの一覧が表示される。まだキャンペーンをロードしていなければ、ここには\ **Basic**\ だけが表示されている。
-  大きなテキストエリアは、現行キャンペーン用のプロパティを編集する場所だ。最初にロードしたとき、ここは空白であるが、左側の
   **Token Type**
   の一覧からプロパティ・セットを選択すると、そのセットの名前と初期値の一覧が表示されるであろう。

Type（種類）
------------

.. raw:: html

   <div style="color:gray">

In this field, you'll see the names of the different "Property Types"
(you can think of them as property *sets*) that are configured in the
current campaign. If you have no campaign loaded, the default property
set will be called *Basic*. The **Type** field is not directly editable
by the user.

.. raw:: html

   </div>

このフィールドには現行キャンペーン用に作成した異なるいくつかの\ *プロパティの種類*\ （プロパティ・\ *セット*\ とみなして構わない）が並ぶことになる。まだキャンペーンをロードしていないのであれば、標準のプロパティ・セットは\ *Basic*\ と呼ばれる。\ **Type**
フィールドはユーザーが直接編集することはできない。

Name（名称）
------------

.. raw:: html

   <div style="color:gray">

This is a simple text field where you can enter the name you want to
give the property set. This name will, when you update the set, appear
in the **Type** list to the left, and it becomes the name for that
particular set of properties. Names can be anything you like; many users
create sets called "NPC" for games where NPC stats and traits differ
from those of player characters, for example.

.. raw:: html

   </div>

これは単純なテキストフィールドであり、プロパティ・セットに付ける名称を入力することが可能だ。プロパティ・セットを更新する際、この名称が左側の\ **Type**\ の一覧に表示され、プロパティ・セットの固有名称となる。名称は自由に決めれば良い。例えば、多くのユーザーは、NPCの状態や特徴がプレイヤー・キャラクターと異なるゲーム用に、\ *NPC*\ という名称を付けてプロパティ・セットを作っている。

Properties（プロパティ）
------------------------

.. raw:: html

   <div style="color:gray">

This is where it gets funky. In this text area, you can create any and
every property you can think of, which can reflect every possible number
or statistic an RPG character might have (and many properties that they
don't have -- lots of users create properties that are useful for when
they write macros, but wouldn't appear on any character sheet!).

.. raw:: html

   </div>

こいつはなかなかイカしたものだ。このテキストエリアでは、君の思いつくあらゆるプロパティを作ることができ、RPGキャラクターで使用するような数値やデータを可能な限り再現することが可能だ。
(RPGキャラクターが持っていないプロパティを持つことも可能だ。ユーザーの多くは、マクロを記述するときに有用なプロパティを作るが、そういったプロパティはキャラクターシートには存在しないのが普通だ！）

プロパティの作成
================

初期値を持たないプロパティ
--------------------------

.. figure:: Basic-default-props.png
   :alt: Basic-default-props.png

   Basic-default-props.png

.. raw:: html

   <div style="color:gray">

If you look at `MTRPG's Primary
Attributes <Sample_Ruleset#Primary_Attribute>`__, you will see that
there are four separate attributes that are the basic attributes of a
character: *Strength*, *Dexterity*, *Intelligence*, and *Endurance*.
We're going to get rid of the default properties, and put new ones in
their place.

.. raw:: html

   </div>

`MTRPG's Primary Attributes（MTRPG
の主要な特性値）では <Sample_Ruleset#Primary_Attribute>`__\ 、キャラクターの基本的な特性である4つに分類された特性値、「
*Strength*\ 、\ *Dexterity*\ 、\ *Intelligence*\ 、\ *Endurance*\ 」を見ることができる。では始めからあるプロパティを取り除き、新しいプロパティを作り上げていこう。

.. raw:: html

   <div style="color:gray">

1. Go to **Edit > Campaign Properties**. You'll see in the left side,
under *Token Type*, that the only entry is "Basic." We're going to
create a new property set.

.. raw:: html

   </div>

1. **Edit → Campaign Properties** を開く。左側にある *Token Type* の下に
*Basic*
の項目だけがあるが確認できるだろう。ここでは新しいプロパティ・セットを作っていく。

.. raw:: html

   <div style="color:gray">

2. In the **Token Type** list on the left, select *Basic*. When you do
this, you'll see a whole bunch of properties with all kinds of symbols
like @, #, and so forth.

.. raw:: html

   </div>

2. **Token Type** の一覧から *Basic*
を選択する。すると、「@」や「#」などの記号を伴ったたくさんのプロパティが表示される。

.. raw:: html

   <div style="color:gray">

3. In the text area with all the properties, use your mouse to highlight
them all, and hit Delete on your keyboard. Go ahead - don't be shy!

.. raw:: html

   </div>

3.
テキストエリアのすべてのプロパティをマウスを使って選択し、キーボードの「Delete（削除）」を押す。遠慮は無用。やっちまえ！

.. raw:: html

   <div style="color:gray">

4. Leave the **Name** field alone - MapTools must always have a *Basic*
property set, so you can't change that name.

.. raw:: html

   </div>

4. **Name** フィールドだけはそのまま残す。MapTool は *Basic*
プロパティ・セットが必ず必要なので、この名称を変更することはできない。

.. figure:: Default-props-replaced.png
   :alt: Default-props-replaced.png

   Default-props-replaced.png

.. raw:: html

   <div style="color:gray">

5. In the text area below the **Name** field, enter the name of each of
the four Primary Attributes in MTRPG, like so:

.. raw:: html

   </div>

5. **Name**
フィールドの下にあるテキストエリアにMTRPGの4つの主要特性値を次のように入力する。

   | ``Strength``
   | ``Dexterity``
   | ``Intelligence``
   | ``Endurance``

.. raw:: html

   <div style="color:gray">

When done, your properties window should look like the screenshot on the
right.

.. raw:: html

   </div>

入力を終えたら、君のプロパティ・ウィンドウは右のスクリーンショットのようになっているはずだ。

.. raw:: html

   <div style="color:gray">

6. Once you've finished entering the properties you want, click the
button labeled **Update**. Don't panic! The properties will disappear,
but if you select the *Basic* list from the left, your properties will
reappear in the main text area.

.. raw:: html

   </div>

6. 必要なプロパティを入力し終えたなら、\ **Update**
ボタンをクリック。おっと驚かなくても大丈夫！プロパティは消え去るが、左の一覧から\ *Basic*
を選択すれば先程入力したプロパティが再びテキストエリアに表示される。

.. raw:: html

   <div style="color:gray">

7. Click **OK** to confirm all of your changes and close the **Campaign
Properties** window.

.. raw:: html

   </div>

7.
編集結果の確認と\ **キャンペーン・プロパティ''ウィンドウを閉じるため**\ OK'''をクリックする。

.. raw:: html

   <div style="color:gray">

8. Go to **File > Save Campaign As** and save your campaign as
**MTRPG.cmpgn**. You've now created a new campaign file, with a new set
of campaign properties.

.. raw:: html

   </div>

8. **File → Save Campaign As**\ を選択し、このキャンペーンを
**MTRPG.cmpgn**
として保存する。これで新しいキャンペーン・プロパティのセットを持つ、新しいキャンペーン・ファイルが出来上がった。

.. raw:: html

   <div style="color:gray">

When you create properties like this -- just listing the values one
after the other -- and then open a token, you will see that these
properties have no value. That does not mean that they are equal to
zero, or equal to a blank line - they literally have *no value*. This
doesn't mean much for most purposes, but it is an important distinction
in macro writing terms (in programming, there's a big difference between
a blank string, and an actually *empty* variable!).

.. raw:: html

   </div>

このようなプロパティ（順々に値が並んでいるような）を作りトークンを開くと、値がない同じプロパティを確認できる。値がないことはゼロや空白行ではなく、文字通り
*no value（値なし）*
という状態だ。これはほとんどの用途で意味を持たないが、マクロを記述するにあたり重要な違いとなる（プログラミングでは、空の文字列なのか、\ *空*\ の値なのかが大きな違いなんだ！）。

.. raw:: html

   <div style="color:gray">

Once properties are updated, all of the tokens on the map will be
updated with the new properties, and any new tokens you drop on the map
will "inherit" the properties you set up.

.. raw:: html

   </div>

プロパティを更新すると、マップ上のすべてのトークンは新しいプロパティに更新され、マップ上に新規に作られるトークンは君の作ったプロパティが「受け継がれて」いる。

.. raw:: html

   <div style="color:gray">

**NOTE**: Property names cannot have spaces in them - so if you have a
property called "Hit Points", you would need to enter it as *HitPoints*.

.. raw:: html

   </div>

**注**\ ：プロパティ名に空白を入れてはいけない。\ *Hit Points*
というプロパティを作るのであれば、\ *HitPoints*\ と入力する必要がある。

**訳注**\ ：日本語のプロパティ名も作れるようだが、マクロの利用などで問題がでる可能性がある。（未確認）

初期値を持つプロパティを作る
----------------------------

.. figure:: Newprops-defvalues.png
   :alt: Newprops-defvalues.png

   Newprops-defvalues.png

.. raw:: html

   <div style="color:gray">

Now, in MTRPG, the minimum value an attribute can have is 1. So, it
makes sense to set the *default value* of these properties to 1 (that
way, every new token will at least have the minimum value an attribute
can have). To do this:

.. raw:: html

   </div>

現在の MTRPT
では、特性値の最小値は1となっている。ということで、プロパティの「初期値」に1を設定するとは理にかなっている。（つまり、新しいトークンは少なくとも最小の特性値を持つようになるということだ）やりかたは次の通り：

.. raw:: html

   <div style="color:gray">

1. Open the Campaign Properties window.

.. raw:: html

   </div>

1. キャンペーンプロパティのウィンドウを開く

.. raw:: html

   <div style="color:gray">

2. Select the *Basic* property set.

.. raw:: html

   </div>

2. *Basic* プロパティ・セットを選択。

.. raw:: html

   <div style="color:gray">

3. In the Basic Properties set, edit your properties so they now read
(see the image, as well):

.. raw:: html

   </div>

3. Basic
プロパティ・セット内のプロパティを次のように編集する（画像を確認しても良い）：

   | ``Strength:1``
   | ``Dexterity:1``
   | ``Intelligence:1``
   | ``Endurance:1``

.. raw:: html

   <div style="color:gray">

4. Click **Update**.

.. raw:: html

   </div>

4. **Update**\ をクリック。

.. raw:: html

   <div style="color:gray">

By placing a colon at the end of the name of each attribute, and putting
the number 1 after the colon, you have instructed MapTool that the
default value for those properties is 1 (in other words, whatever value
you put after the colon becomes the *default value* for that property).
You'll note that at the bottom of the Token Properties tab there is a
key describing the various options you can set on a property.

.. raw:: html

   </div>

各特性名の末尾にコロンを置き、その直後に数字の1を記述することで、MapTool
にそれぞれの初期値が1であることを指示することになる（つまり、コロンの後に置いたものはなんであってもそのプロパティの\ *初期値*\ となる）。トークン・プロパティのタブの下部にある、プロパティに取り付け可能なさまざまな「Key」の説明の中に上記の内容があることに気付くであろう。

.. raw:: html

   <div style="color:gray">

Now, if you drag a new token onto the map and look at its properties
(double-click on the token and go to the Properties Tab in the **Edit
Token** dialog), you will see that the new token has the default values.

.. raw:: html

   </div>

その後、マップ上に新しいトークンをドラッグし、プロパティを確認する（トークンをダブルクリックして\ *'Edit
Token*\ ダイアログのプロパティタブを開く）と、この新しいトークンが初期値を持っていることが確認できるだろう。

.. raw:: html

   <div style="color:gray">

By the way: don't worry about any tokens you may have already set the
property values on - setting up or changing the default values will
*not* override the properties you've already set. MapTool is smart
enough to handle that.

.. raw:: html

   </div>

ちなみに：君が既にプロパティに値を設定したトークンのことは心配しなくて良い。初期値を作ったり変更したりしても既に値を設定したプロパティが「上書き」されることはない。MapTool
はこのあたりを賢く取り扱う。

データシート（Statsheet）にプロパティを表示する
-----------------------------------------------

.. figure:: Statsheet-props.png
   :alt: Statsheet-props.png

   Statsheet-props.png

.. raw:: html

   <div style="color:gray">

MapTool has a neat feature called the **Statsheet**, which is briefly
mentioned in the `Introduction to Tokens <Introduction_to_Tokens>`__ -
basically, it is an automatic popup that appears in the lower left
corner of the map, when you hover over a token.

.. raw:: html

   </div>

MapTool は **データシート（Statsheet）**
という素敵な機能を持っている。\ `はじめてのトークンで簡単に説明しているように <Introduction_to_Tokens/ja>`__\ 、基本的には、トークン上にカーソルをかざしたときにマップの左下隅に表れるものだ。

.. raw:: html

   <div style="color:gray">

You may be saying, "Wait...when I hover over my token, there's no
statsheet! Where is it?" The reason you don't see it yet is that the
Statsheet is governed by the Campaign Properties - it displays the
token's properties (along with a larger version of the token's image) -
but *only* when a couple requirements are met:

.. raw:: html

   </div>

君は「ちょっと待ってくれ。トークン上にカーソルを持っていってもデータシートは表示されないぞ！どこにあるんだ？」と言うに違いない。データシートが表示されないのは、データシートは「（より大きなトークン画像に沿って）トークンのプロパティを表示する」というものであるが、次の二つの条件を満たす必要があるからだ：

.. raw:: html

   <div style="color:gray">

-  The properties are set up to display on the statsheet; and
-  The properties that are displayed actually have a value

   .. raw:: html

      </div>

-  プロパティをデータシートに表示するように設定し、
-  プロパティに実際の値を与える

プロパティを表示するために必要なこと
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. figure:: Newprops-visible.png
   :alt: Newprops-visible.png

   Newprops-visible.png

.. raw:: html

   <div style="color:gray">

If you look at the bottom of the **Token Properties** tab in the
**Campaign Properties** dialog, you'll see a key showing how to set up a
property to display in the Statsheet. There are three display options,
each of which is indicated by putting a symbol in front of the property
name:

.. raw:: html

   </div>

**Campaign Properties** ダイアログの **'Token Properties**
のタブの下部を見れば、データシートにプロパティを表示する方法を記した記号一覧（Key）が確認できるはずだ。ここには3つの選択肢があり、それぞれ、シンボルをプロパティ名の先頭に置くよう示されている：

.. raw:: html

   <div style="color:gray">

#. **\***: an asterisk means "show this property on the statsheet"
#. **@**: means "only show this property to the owner of the token (and
   the GM)"
#. **#**: means "only show this property to the GM (not even the token
   owner can see it)"

   .. raw:: html

      </div>

#. **\***\ ：アスタリスクは「このプロパティをデータシートに表示する」という意味。
#. **@**\ ：「トークンの所有者（およびGM）にのみプロパティを表示する」という意味。
#. **#**\ ：これは「GMにのみプロパティを表示する（トークンの所有者であっても表示されない）」という意味。

.. raw:: html

   <div style="color:gray">

The asterisk is **required** for any stat to display at all - if you
don't have an asterisk first, it won't show no matter what else you put
on there. The @ and # symbols, on the other hand, are optional.

.. raw:: html

   </div>

アスタリスクはどのようにデータを表示するにしても\ **必須**\ であり、アスタリスクを付けなければ他の記号をおいても何も表示されない。アスタリスクと異なり、@
と # の記号は必須ではない。

.. raw:: html

   <div style="color:gray">

So, for our new game, we're going to set all of the properties to be
visible to everyone (by just using a star). To do this, open up your
properties, and edit them to look like this:

.. raw:: html

   </div>

というわけけで、新しいゲームでは全てのプロパティをみんなが見えるようにするつもりだ（アスタリスクを使って）。そのために、プロパティを開いて、次の
ように編集してくれ：

   | ``*Strength:1``
   | `` *Dexterity:1``
   | `` *Intelligence:1``
   | `` *Endurance:1``
   | 

.. raw:: html

   <div style="color:gray">

Now, when you hover over a token, you'll see the Statsheet pop up (see
the screenshot, above) with the values in the Strength, Dexterity,
Intelligence, and Endurance properties. Also, since even brand new
tokens have a default value, the Statsheet will appear for all tokens.

.. raw:: html

   </div>

これで、トークン上にカーソルをかざすと上のスクリーンショットのようにデータシートが表示されるだろう。データシートには特性値を伴った「Strength、Dexterity、Intelligence、Endurance」のプロパティが表示されているはずだ。これまでと同じように、新しく作られたトークンは初期値を持っているので、全てのトークンにデータシートが表示されるであろう。

短縮名
~~~~~~

.. figure:: Newprops-shortnames.png
   :alt: Newprops-shortnames.png

   Newprops-shortnames.png

.. raw:: html

   <div style="color:gray">

Sometimes, property names can get pretty long (or look unfriendly - no
spaces, and all that). MapTool lets you put a *Short Name* in for each
property. To do that, you just enter the short name in parentheses after
the property name, like so:

.. raw:: html

   </div>

ときどき、プロパティ名が長すぎるときがある（見づらく、スペースが足らなかったり他いろいろ）MapTool
では各プロパティに「短縮名」を設定することができる。これをするためには、括弧でくくった短縮名をプロパティの後ろに置くだけで良い。次のように：

   | ``*Strength(Str):1``
   | `` *Dexterity(Dex):1``
   | `` *Intelligence(Int):1``
   | `` *Endurance(End):1``
   | 

.. raw:: html

   <div style="color:gray">

These short names are displayed in the Statsheet instead of the full
name of the property

.. raw:: html

   </div>

ここで設定した短縮名はプロパティの長い名称の代わりにステータスシート上に表示される。

.. raw:: html

   <div style="color:gray">

**Short Names are for display purposes only - when referencing
properties in macros, you must use the full property name.**

.. raw:: html

   </div>

**短縮名は表示のためだけに使用される。マクロでプロパティを参照する場合は必ず本来の名称を使用すること。**

連動プロパティを作成する
------------------------

.. figure:: Newprops-derived.png
   :alt: Newprops-derived.png

   Newprops-derived.png

.. figure:: Statsheet-with-allnewprops.png
   :alt: Statsheet-with-allnewprops.png

   Statsheet-with-allnewprops.png

.. raw:: html

   <div style="color:gray">

Okay, now let's do something pretty cool. In a lot of roleplaying games,
there are character attributes that are derived from other stats - for
instance, in the *Savage Worlds* rules, your "Parry" stat is based on
your *Fighting* ability; likewise, in Dungeons & Dragons, your "Hit
Points" are derived partly from your "Constitution" score.

.. raw:: html

   </div>

よーし、次はとてもクールことをやってみよう。多くのRPGでは、キャラクターの特性値は他のデータと連動して導かれる。例えば、\ *Savage
Worlds* のルールでは、\ *Parry* の値は *Fighting*
の能力を基準にしている。同じようにダンジョンズ＆ドラゴンズでは、\ *ヒット・ポイント*\ は\ *【耐久力】*\ の値が部分的に関係している。

.. raw:: html

   <div style="color:gray">

Now, you could create these other derived attributes as separate
properties and manually enter the values in when you make a new token -
but how about we allow MapTool to calculate these derived values? That's
right - MapTool's campaign properties can not only be numbers and text,
but also calculations and equations based on other properties that the
token has.

.. raw:: html

   </div>

今のところ、君は連動プロパティ以外（個別のプロパティとトークン作成時に手動で値を入力するプロパティ）を作ることができるが、どのようにして値に連動する計算をすればよいのだろうか？MapTool
のキャンペーン・プロパティの値は数値やテキストだけではなく、トークンの持つ他のプロパティに基づく計算式や方程式でも構わない。

.. raw:: html

   <div style="color:gray">

In MTRPG, there are three *derived* stats: Hit Points, Armor, and
Movement. These stats have the short names "HP", "AR," and "MV." For
this example, we're going to set up *Hit Points* and *Movement* to be
calculated from existing properties. We'll leave Armor until later (it
takes a bit more complex a calculation to figure out the armor value,
and we're taking it slow).

.. raw:: html

   </div>

MTRPG では、3つの\ **連動**\ データがある： Hit
Points、Armor、Movement。各項目は短縮名「HP」、「AR」、「MV」を持つ。今回の例では、「Hit
Points」と「Movement」を他の値から算出するものを作ってみよう。Armor
については今後の課題にしてこう。（Armor
の値を導き出すのは少し複雑な計算になり、速度の低下を招くだろう。）

.. raw:: html

   <div style="color:gray">

First, we need to add properties for these three derived values:

.. raw:: html

   </div>

まず、この3つの連動する値を持つプロパティを追加しなければならない：

.. raw:: html

   <div style="color:gray">

1. Open up the Basic property set.

.. raw:: html

   </div>

1. Basic プロパティ・セットを開く。

.. raw:: html

   <div style="color:gray">

2. Beneath *Endurance*, enter the following:

.. raw:: html

   </div>

2. *Endurance* の下に次のように入力する：

   | ``*HitPoints(HP)``
   | `` *Armor(AR)``
   | `` *Movement(MV)``
   | 

.. raw:: html

   <div style="color:gray">

You'll notice at this point, we've set no default values. Don't hit
**Update** just yet - let's enter some macro code to create a derived
value.

.. raw:: html

   </div>

初期値を設定していないことに気付いただろうか。まだ **Update**
をクリックしないように。続いて連動する値を作るためにマクロコードを入力していこう。

.. raw:: html

   <div style="color:gray">

We can see from the `MTRPG <Sample_Ruleset>`__ rules that *Hit Points*
is equal to the value of *Endurance* multiplied by 6. Replicating this
calculation in the campaign properties is very simple. Edit the *Hit
Points* property to read:

.. raw:: html

   </div>

`MTRPG <Sample_Ruleset>`__ のルールを見ると、\ *Hit Points* は
*Enduarance*
を6倍したものだと書かれている。キャンペーン・プロパティでのこの計算手順は実に単純だ。\ *Hit
Points* のプロパティを次のように編集する：

   ``*HitPoints(HP):{Endurance * 6}``\ 

.. raw:: html

   <div style="color:gray">

What we've done here is enter a default value for the property
(remember, default values are whatever comes after the colon), and used
some `macro code <Introduction_to_Macro_Writing>`__ to instruct MapTool
to perform a calculation in order to find the value for the properties.
Two thing are happening here:

.. raw:: html

   </div>

ここでは、プロパティの初期値を入力（初期値はコロンの後に置くことを憶えているかな）し、MapTool
にプロパティの値を求めるために計算を実行することを命令する\ `マクロコードを使用する <Introduction_to_Macro_Writing>`__\ 、ということを行った。ここには2つの発見がある：

.. raw:: html

   <div style="color:gray">

#. We've enclosed the calculations in { }, which warns MapTool that the
   text enclosed inside the brackets is to be handled like a macro, and
   not just plain text
#. Inside the brackets, we've said, "Find the value of the *Endurance*
   property, multiply it by 6, and make that result the value of the
   *Hit Points* property"

.. raw:: html

   </div>

#. 計算式を { } で囲ってあり、これはMapTool
   に括弧の中のテキストは通常のテキストではなく、マクロのように扱うよう伝えるものだ。
#. 括弧の中では次のように述べている。「\ *Endurance*
   のプロパティの値を見つけ、6倍し、計算結果を *Hit Points*
   の値とするように」。

.. raw:: html

   <div style="color:gray">

Now, to handle the *Movement* attribute, our job is even simpler: we
need to instruct MapTool to get the value of the *Dexterity* property,
and assign that same value to the *Movement* property. To do so, edit
the Movement property to read:

.. raw:: html

   </div>

次は *Movement* を扱うが、この作業は実に単純だ：\ *Dexterity*
のプロパティの値を見つけ、同じ値を *Movement*
プロパティの値としてテイ要する必要がある。ではやってみよう。Movement
のプロパティを次のように編集する：

   ``*Movement(MV):{Dexterity}``\ 

作業を終えたなら、全体のプロパティセットは次のようになっていはずだ：

   | ``*Strength:1``
   | `` *Dexterity:1``
   | `` *Intelligence:1``
   | `` *Endurance:1``
   | `` *HitPoints(HP):{Endurance * 6}``
   | `` *Armor(AR)``
   | `` *Movement(MV):{Dexterity}``
   | 

.. raw:: html

   <div style="color:gray">

And when you hover your mouse over a token, the Statsheet should look
like the screenshot to the right. Remember, even though we've said that
*Armor* should be displayed on the statsheet, the statsheet only shows
properties that have a value - *Armor* is still empty, so it won't show
up until you give it a value.

.. raw:: html

   </div>

これでマウスカーソルをトークン上にかざすと、データシートには右のスクリーンショットの用に表示されるはずだ。\ *Armor*
プロパティはデータシート上に表示されべきと言ったが、データシートに表示されるは値を持つプロパティだけであることを忘れないように。\ *Armor*
はまだ空なので値を与えるまでは表示されない。

技術的な情報を少しばかり
========================

.. raw:: html

   <div style="color:gray">

A couple times in this guide and in other guides the token properties
have been described as "those properties that are *visible*" in this
campaign, or the properties set up "*for this campaign*." There's a
reason for phrasing it like this.

.. raw:: html

   </div>

トークンのプロパティに関するこのガイドと他のガイドでは次のように「このキャンペーンで表示されるプロパティ」や「このキャンペーンのために設定されたプロパティ」というように説明されている。このような言い回しをするには理由がある。

.. raw:: html

   <div style="color:gray">

See, a token - if you cut one open and looked at its inner workings - is
an XML file that contains a *ton* of information. It has information
about its image, its size, its vision, light, and shape, and - of course
- its properties. What's important to understand here is that the token
will remember not only the properties from the MTRPG, but if it was ever
saved as an **.rptok** file or brought in from another campaign file, it
will remember the properties from that campaign too. They won't be
visible, but they're stored in the token even so.

.. raw:: html

   </div>

トークンは大量の情報が詰まったXMLファイルだ。画像、トークンのサイズ、光源、形状、当然ながらトークンの持つプロパティといった情報を持っている。ここで理解するために重要なことは、トークンが記憶するのは
MTRG に由来するモノだけではなく、\ **.rptok**
ファイルとして保存されたものや他のキャンペーンファイルで作らたものであった場合、そのキャンペーンと同じものを記憶しているであろう、ということだ。それらは表示されはしないが、トークンの中に格納されている。

.. raw:: html

   <div style="color:gray">

So, in reality, a set of Campaign Properties really indicates those
properties that:

.. raw:: html

   </div>

実際には、キャンペーンプロパティのセットは現実に次にあげるプロパティのことを指す：

.. raw:: html

   <div style="color:gray">

-  You can see if you open up a token by double-clicking on it, and
-  You can directly edit by clicking in the cell next to them

.. raw:: html

   </div>

-  トークンをダブルクリックしてトークンを開いたときに表示されるもの、及び
-  プロパティ名に続くセルをクリックして直接編集できるもの

.. raw:: html

   <div style="color:gray">

This may sound like a recipe for disaster - what if you set up a
property that was already set up but is hidden? Fortunately, MapTool
will not, when running a macro, attempt to access any hidden properties
unless you *specifically* instruct it to do so, using two special macro
functions. So rest assured, you cannot accidentally access a property
that's not set up in the Campaign Properties.

.. raw:: html

   </div>

これは大惨事の原因のように思えるかもしれないが、君が既に設定済みであり表示されていないプロパティを設定した場合はどうなるのだろうか？幸いにも、マクロを実行する際、MapToolは表示されないプロパティへのアクセスを試みることはない。君が2つの特殊なマクロ関数を使って\ *明確に*\ そうするように指示しない限りは。安全のため、キャンペーンプロパティで設定されていないプロパティにうっかりアクセスすることはできないようになっている。

.. raw:: html

   <div style="color:gray">

In summary, if a Property Type (such as the default *Basic* property
type) has a property named **HP**, it will be stored in the token under
the XML name **HP**. If another property type (such as a user-defined
*Pathfinder* property type) also has a property named **HP**, they will
both be referencing the same data on the token. Modifying the value of
**HP** when the token is *Basic* and then changing the token
*Pathfinder* will show the same value for **HP**.

.. raw:: html

   </div>

手短に言えば、あるプロパティタイプ（標準の *Basic*
プロパティタイプとする）が **HP** という名のプロパティを持つ場合、それは
**HP**
というXMLの名前でトークンの中に格納されている。他のプロパティタイプ（ユーザーが定義した\ *Pathfinder*\ プロパティタイプとする）が同じように
**HP**
という名のプロパティを持つ場合、どちらもトークン上の同じデータを参照する。トークンが
*Basic* であるときに **HP** の値を修正し、トークンを *Pathfinder*
に切り替えると **HP** の値は同じものが表示される。

次のステップ
============

.. raw:: html

   <div style="color:gray">

MapTool supports very elaborate properties and derived properties, with
a number of math functions and operations. A couple of the most common
ones you might want to use are (the examples are not necessarily part of
MTRPG; they're just examples):

.. raw:: html

   </div>

MaptTool
はとても複雑なプロパティとたくさんの数学関数と演算能力を備えた連動プロパティをサポートしている。使ってみたくなるであろう機能の中でもっとも一般的なものを2、3紹介しよう（以下に上げる例はMTRPGのものとは限らず、ただの例である）：

.. raw:: html

   <div style="color:gray">

-  **Basic math operators**: addition (+), subtraction (-),
   multiplication (*), and division (/)

   -  **Example**: ``HitPoints: {Endurance * 6}``

-  **Rounding**: there are some *functions* to let you round numbers
   when you divide

   -  **Floor**: the floor() function rounds *down*. **Example**:
      ``HitPoints:{floor(Constitution / 2)}`` would divide Constitution
      by two, and round down
   -  **Ceiling**: the ceil() function works like floor(), but rounds
      up. **Example**: ``HitPoints:{ceil(Constitution/2)}``

.. raw:: html

   </div>

-  **基本的な数学の演算**\ ：足し算（+）、引き算（-）、掛け算（*）、割り算（/）

   -  **例**\ ：\ ``HitPoints: {Endurance * 6}``

-  **数値を丸める**\ ：割り算の際、数値を丸めるためにいくつかの\ *関数*\ がある。

   -  **切り捨てる**\ ：floor()
      関数は端数を切り捨てる。\ **例**\ ：\ ``HitPoints:{floor(Constitution / 2)}``
      Constitution を2で割り、端数を切り捨てる。
   -  **切り上げる**\ ：ceil() 関数は floor()
      と同様に機能するが端数を切り上げる。\ **例**\ ：\ ``HitPoints:{ceil(Constitution/2)}``

`Category:MapTool <Category:MapTool>`__
