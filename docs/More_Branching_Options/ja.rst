.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{Languages|More Branching Options}}

{{#customtitle:続・分岐オプション|続・分岐オプション}}

はじめに
========

.. raw:: html

   <div style="color:gray">

This is a guide to the "advanced" macro branching option, .

.. raw:: html

   </div>

これはマクロの分岐オプションの中でも「高度」な 　についてのガイドだ。

.. _macro_他のマクロを実行する:

MACRO: 他のマクロを実行する
===========================

.. raw:: html

   <div style="color:gray">

One of the best practices when you write macros - especially when they
become complex - is to keep them streamlined and lean, and only have
them do what they need to do - for instance, if you have a macro that
adds a skill to a token, it doesn't need to be the same macro that
checks to see if an attack hits, or records damage taken. It just adds
skills.

.. raw:: html

   </div>

マクロを書くとき、特に複雑なものを書くときに一番いいのは、すっきりと簡潔なものにして、必要以外の処理だけに絞ることだ。例えば、トークンに技能を与えるマクロを既に持っているとしたら、、攻撃の命中判定やダメージ・トークンを記録するといった機能をそのマクロに追加するべきではない。技能だけにするのだ。

.. raw:: html

   <div style="color:gray">

Writing macros this way - each macro doing something relatively small -
is a good way to keep yourself organized and keep your macros clear (it
also makes them easier to fix if something goes wrong!). What's more, it
helps keep your memory use lower, so you don't get run into `stack
overflow errors <Stack_Size>`__ or, more commonly, slow macros.

.. raw:: html

   </div>

こういう、つまり比較的小さな機能のみを持つようにするやり方は、中身を理解しやすいし、見通しもよくなる（し、何かおかしなことが起こったときに修理もしやすい）。さらに、メモリの使用量も減らせるから、\ `stack
overflow
errorsや <Stack_Size>`__\ 、よくある実行速度の低下を起こさないで済む。

.. raw:: html

   <div style="color:gray">

But if you do this, how can you make one macro run based on another one
- surely, you don't want to have to hit each button every time something
happens, right? Enter the roll option.

.. raw:: html

   </div>

だが、これを実践するためには複数のマクロを連携させる必要があるが、それはどうやったらできるだろうか？
当然だが何か起こるたびに自分でいちいちボタンを押すなんてごめんだよね？
そこで ロール・オプションの出番だ。

どんなことをするのか？
----------------------

.. raw:: html

   <div style="color:gray">

The roll option is they way you can have one macro - the *calling* macro
- trigger another macro, which we call the *called* macro. The *calling*
macro can send some information to the *called* macro, where that
information will be handled and processed and probably changed, and
then, if you like, the *called* macro can send some information back to
the caller.

.. raw:: html

   </div>

.. raw:: mediawiki

   {{roll|macro}}

ロール・オプションは、あるマクロ（\ *呼び出し側*\ ）が別のマクロ（\ *呼び出され側*\ ）のマクロを起動できるようにする。\ *呼び出し側*\ マクロは\ *呼び出され側*\ マクロに情報を送り、その\ *呼び出され側*\ マクロでこの情報を処理し、だいたいは編集して、それからもし必要なら\ *呼び出され側*\ から\ *呼び出し側*\ に別の情報を送り返す。

どうしてそんなものを使わなきゃならないの？
------------------------------------------

.. raw:: html

   <div style="color:gray">

Where this comes in handy is in three circumstances: first, when you
have some operation that you're always doing, but you have several
different ways that it might come up. Second, if you have a macro that
*everyone* uses. The second, and more powerful use, is when you want to
manipulate another token besides your own - then you frequenly need to
use *called* macros, because there are some things only a *called* macro
can do!

.. raw:: html

   </div>

このオプションが便利なのは以下の三つの場合だ：
第一に、通常行っている処理とは別の処理を時々やらなければならない場合。第二に、\ *みんなで使う*\ マクロが欲しいとき。第三に、この中でも一番強力な使い道だが、自分自身以外の複数のトークンを操作したいとき、だ。この場合、\ *呼び出され側*\ のマクロを頻繁に使うことになる。なぜなら、\ *呼び出され側*\ のマクロにしかできないことがあるからだ。

複数箇所から共通の処理を呼び出す
--------------------------------

.. raw:: html

   <div style="color:gray">

Let's look at the first benefit: take, for example, a macro that applies
damage to a token in accordance with the `Sample
Ruleset <Sample_Ruleset>`__ (in other words, it looks at a token's
properties, and then deducts damage from the token's property). How many
ways can you think a token might get damaged?

.. raw:: html

   </div>

第一の利点について見てみよう。例として、\ `Sample
Ruleset <Sample_Ruleset>`__
に合わせてトークンにダメージを与えるマクロを考えてみる（つまり、トークンの属性値を参照し、そのトークンの属性値からダメージ分を減らすマクロだ）。そのトークンがダメージがどれほど沢山のパターンでダメージを受ける可能性があるか分かるかな？

.. raw:: html

   <div style="color:gray">

#. It could get damaged by an attack from an enemy
#. It could get damaged by an attack from a friend (accidental or
   otherwise)
#. It could get damaged by falling
#. It could be damaged by a trap

.. raw:: html

   </div>

#. 敵の攻撃
#. 味方の攻撃（事故だったり、そうでなかったり）
#. 落下
#. 罠

.. raw:: html

   <div style="color:gray">

All kinds of ways. Now, suppose you have three macro to handle damage.
These macros are called **Enemy Attack**, **Friendly Fire**, and
**Environmental Damage**. Each of these causes a token's to be reduced,
but each also has some special processing to determine *just how much*
HP reduction takes place (it's not important what the special processing
is at the moment).

.. raw:: html

   </div>

ありとあらゆるパターンがありうる。さて、ダメージを扱うマクロを三つ持っているとしよう。このマクロはそれぞれ\ **Enemy
Attack**\ 、\ **Friendly Fire**\ 、\ **Environmental
Damage**\ と呼ばれている。それぞれのマクロはどれも対象となるトークンの
を減らすが、\ *どれだけ減らすか*\ はマクロごとに別の特別の処理を持っている（この特別な処理の中身は、今は重要ではない）。

.. raw:: html

   <div style="color:gray">

So you have three macros, but each has a common element: they all in the
end reduce the token's . Consider a couple alternatives - you can:

.. raw:: html

   </div>

三つのマクロがあるが、共通の要素を持っている。そのどれもが最後にはトークンの
を減らすということだ。いくつか選択肢を考えてみよう。こういうことが考えうる：

.. raw:: html

   <div style="color:gray">

#. Write each macro separately, including the calculations to reduce ;
   or
#. Write a fourth macro, containing just the calculations to reduce ,
   and have the three damage handler macros *call* that fourth to handle
   the final calculations.

.. raw:: html

   </div>

#. それぞれ を減らす部分を含むマクロを別々に書く
#. 単に
   を減らすだけの第四のマクロを書き、ダメージを扱うその他三つのマクロからこの第四のマクロを
   *呼び出し*　て、最終的な計算を行う

.. raw:: html

   <div style="color:gray">

The advantages of the first option are that you only need to write three
macros, and you're done. On the other hand, what if you realize you made
a mistake in your damage macro? You then have to edit it in three
places. In the second option, you only edit one copy of the damage
macro.

.. raw:: html

   </div>

最初の選択肢の利点は、マクロの数が三つで済むことだ。だが、逆に考えると、もしそのマクロに何かの間違いがあることに気づいたらどうなるだろうか？
書き直すべき箇所が三ヶ所あることになる。二番目の選択肢では、ダメージを与えるマクロだけを修正すればいい。

みんながやる作業
----------------

.. raw:: html

   <div style="color:gray">

Building on the example above, if you have a whole bunch of macros that
everyone uses (perhaps everyone needs to have a way to attack, to
defend, and to take and heal damage), you can create a single set of
macros that everyone simply *calls*, rather than duplicating every macro
on every token, every time you need a new token on the map.

.. raw:: html

   </div>

上の例に基づいてマクロを作っていくと、みんなで使うようなマクロ（攻撃、防御、ダメージを受ける、ダメージから回復するなどは誰もが使うだろう）が沢山あった場合、みんなが\ *呼び出し*\ て使うマクロが一そろいあればよくて、新しいトークンがマップ上に生まれるたびにそこに全てのマクロをコピーしなくて済む。

.. raw:: html

   <div style="color:gray">

So, for example, you may want to build a "library" of macros to handle
your game (whatever game it happens to be), and then create a single set
of macros on your tokens that do nothing but *call* macros in the
library.

.. raw:: html

   </div>

そんなわけで、あなたは自分のゲーム用の「ライブラリ」を作ろうと思うかも知れない（どんなゲームかはさておき）。そしてそれから、自分のトークンを作って、ライブラリ上のマクロを\ *呼び出す*\ マクロだけを載せておくのだ。

.. raw:: html

   <div style="color:gray">

You'll note that it doesn't mean you have fewer macros overall - every
token still needs a set of macros to call on the library; however, it
*does* mean that your actual complex macros (the ones that took you a
long time to write) are all in one place, and you only need to alter
**one** copy in order to fix an error. If you'd copied the entire macro
set to every token, you'd have to fix *every single token* one at a time
to fix any mistakes you made.

.. raw:: html

   </div>

必ずしもマクロの総数が減らせるとは限らないということに気づいた人もいるだろう。それぞれのトークンにはライブラリを呼び出すためのマクロが必要だ。だが、あなたが（手間隙かけて）作る本当に複雑な部分のマクロは\ *一ヶ所にまとめておく*\ ことができるのだ。そしてエラーがあったなら、その\ **一ヶ所**\ を修正するだけで済む。もし全てのトークンにありとあらゆるマクロをコピーしておくのだとしたら、エラーを修正するには\ *一つ残らず全てのトークン*\ を修正しなければならないのだ。

他のトークンに対する操作と、信頼されたマクロ
--------------------------------------------

.. raw:: html

   <div style="color:gray">

Generally, when a token runs a macro, or calls a macro, the macro
assumes that all properties and variables it needs to use apply to the
token *running* the macro. So if Bork the Brave calls a macro in a macro
library, that library macro is going to assume that it needs to do its
thing on Bork the Brave.

.. raw:: html

   </div>

一般に、トークンがマクロを実行したり呼び出したりするときには、実行に必要な属性値や変数はそのマクロを実行しているトークン上にあるものと想定している。従って、勇者ボークがマクロ・ライブラリの中のあるマクロを呼び出した場合、そのマクロは勇者ボーク上のものに対して処理を行うものと考える。

.. raw:: html

   <div style="color:gray">

However, sometimes Bork the Brave does *not* want this - maybe Bork the
Brave just whacked a troll with his sword, and wants the damage to be
applied to the troll (and, by extension, most definitely does *not* want
the damage applied to himself!). He's going to want a macro that will
affect the *troll's* token, not his own.

.. raw:: html

   </div>

しかし、勇者ボークにとってそれでは\ *都合が悪い*\ 場合もある。おそらく、勇者ボークは一匹のトロールを剣でぶん殴って、そのダメージをトロールに適用して欲しいのかも知れない（だから、そのダメージが自分に対して適用されるなんてことは\ *絶対あって欲しくない*\ はずだ！）。彼に必要なのは、自分のではなく、\ *トロールの*\ トークンに対して効果を及ぼすようなマクロのはずだ。

.. raw:: html

   <div style="color:gray">

As it turns out, however, there are some things, as mentioned, that a
regular old macro on a player token simply can't do. For instance, a
macro on a player token can't go and determine what an NPC token's
properties are. It's simply not permitted to access another token. I
think you'll agree this is a good way to go - you may not want players
being able to see property values on an NPC. Furthermore, a player token
macro can't *change* values on another token. Nobody wants the players
to be able to, for instance, reduce an enemy's armor value to zero just
before making an attack.

.. raw:: html

   </div>

さて、ここで問題になるのは、これまでも言ってきたとおり、プレイヤー・トークンに載っている昔ながらのマクロでは、これができないのだ。例えば、プレイヤー・トークン上のマクロは
NPC
トークンの属性値を操作できない。他のトークンへのアクセスは許されていないのだ。この事自体には納得してもらえると思う。プレイヤーたちに
NPC
の属性値を見られては困るからだ。さらに言えば、プレイヤー・トークンのマクロは他のトークンの値を\ *変更する*\ ことはできない。NPC
に攻撃をかける前にそいつの装甲値をゼロに下げられるようでは困るからだ。

.. raw:: html

   <div style="color:gray">

But still, we want to be able to do *some* things to other tokens,
right? In response to that, the concept of **trusted macros** was
developed. Trusted macros are simply macros that can perform certain
functions unavailable to other macros, such as the functions that
manipulate token properties *other than* the ones on the token who
called the macro.

.. raw:: html

   </div>

だが、そうは言っても、他のトークンに対して\ *多少*\ 何かをしたいよね？
その対応として\ **信頼されたマクロ**\ の概念が考案された。信頼されたマクロとは、そのマクロを呼び出したトークン\ *以外の*\ トークンの属性値を操作するなどの、他のマクロにはできないことが可能なマクロのことだ。

どうやって使うの？
------------------

.. raw:: html

   <div style="color:gray">

.. raw:: mediawiki

   {{roll|macro}}

is a roll option, so, like other roll options you've seen, it is put at
the beginning of a line and ends with a colon. The essential format of
the roll option is:

.. raw:: html

   </div>

.. raw:: mediawiki

   {{roll|macro}}

はロール・オプションなので、これまで見てきた他のロール・オプションと同じように、行の先頭に置き、最後はコロンで終わる。の基本書式は以下の通り：

.. raw:: html

   <div style="color:gray">

..

   .. code:: mtmacro

      [MACRO("macroName@Lib:token"): macro_arguments]

.. raw:: html

   </div>

..

   .. code:: mtmacro

      [MACRO("マクロ名@Lib:token"): マクロの引数]

.. raw:: html

   <div style="color:gray">

In the above example, there are several parts:

.. raw:: html

   </div>

上の例の中にあるパーツは以下の通りだ：

.. raw:: html

   <div style="color:gray">

-  The opening and closing square brackets (**[ ]**), which surround
   *all* macro commands in MapTool
-  The word "MACRO" (it does not have to be capitalized; that's done to
   keep it noticeable!), which is just the name of this particular roll
   option
-  *macroName*: this is the name of the macro you wish to call
-  @: this is used in the same sense as in an email address - it means
   "at"
-  **Lib:token**: this is the `Library Token <Library_Token>`__ that
   contains the macro you wish to call. Library tokens are a complex
   subject, but you can think of them as a single token that holds a
   "library" of macros, that can be called by other tokens or call each
   other.
-  **macro_arguments**: an *argument* is a programming term for
   information that you send to a function (or in this case, a macro)
   that you want the function to *do* something to. If you had a
   function that added two numbers together, the numbers you send to it
   would be the "arguments" to that function.

.. raw:: html

   </div>

-  MapToolが持つ\ *あらゆる*\ コマンドを囲む、一組の大カッコ（\ **[
   ]**\ ）
-  "MACRO"
   というワード（大文字でなくても構わない。目立つようにこうしてあるだけだ）。これはこのロール・オプションの名前だ。
-  *マクロ名*\ ： これはあなたがこのマクロにつけた名前だ。
-  @：　これはメールアドレスと同じ使い方だ。意味は「at（＝～の場所の）」だ。
-  **Lib:token**\ ： これは呼び出したいマクロを持つ\ `Library
   Tokenだ <Library_Token>`__\ 。ライブラリ・トークンは複雑だが、複数のマクロの「ライブラリ」を持つ一つのトークンと見なすことができる。このトークンは他のトークンを呼び出したり、逆に他のトークンから呼び出されたりできる。
-  **マクロの引数**\ ：
   *引数*\ はプログラミングの用語で、何か仕事をさせたい関数（ここではマクロ）にあなたが与える情報のことだ。例えば二つの数を足し合わせる関数があるとしたら、あなたがその関数に与える二つの数が、その関数の「引数」ということになる。

.. raw:: html

   <div style="color:gray">

So in the command above, you've said "run the macro called *macroName*
at the library token *Lib:token*, and send it *macro_arguments* to work
on." The programming jargon for what you've just done is "calling a
macro," or "creating a macro call."

.. raw:: html

   </div>

そんなわけで、上に挙げたコマンドの例では、「ライブラリ・トークン\ *Lib:token*\ の中にある\ *マクロ名*\ というマクロを実行しろ。そのマクロには\ *マクロの引数*\ を与えろ」と指示したことになる。プログラミング用語ではこれを、「マクロの呼び出し」とか、「マクロ呼び出しの生成」と呼ぶ。

.. raw:: html

   <div style="color:gray">

The next section will have some actual examples to help you get a grasp
of using .

.. raw:: html

   </div>

次では の使い方を理解するためにいくつか実例を挙げてみる。

引数と戻り値を扱う
------------------

.. raw:: html

   <div style="color:gray">

In programming terms, a function is a set of commands that *receives*
arguments (described briefly above), does some processing on those
arguments, and then *returns* a value to the place from where it was
called. The macro roll option is not technically a function, but when it
is used, the process is mostly similar: it calls on another macro, sends
it arguments, and that other macro *may* - if you write the macro so
that it does - return a value to the calling macro.

.. raw:: html

   </div>

プログラミング用語で言う関数とは、上で簡単に述べたようにいくつかの引数を\ *受け取り*\ 、その引数について何らかの処理をして、それから呼ばれた場所に値を\ *返す*\ もののことだ。マクロのロール・オプションは厳密には関数ではないが、使い方はほぼ同じだ。他のマクロを呼び出し、引数を与える。その呼び出されたマクロは（あなたがそのように書いておけば）呼び出したマクロに値を返す\ *ことがある*\ 。

.. raw:: html

   <div style="color:gray">

When you call a macro, you can send it any variable, string, or number
as an argument (in other words, you can replace *macro_arguments* with a
variable, a string, or a number, which is sent to the called macro). For
example, let us assume the following:

.. raw:: html

   </div>

マクロを呼び出す場合には、好きな変数、文字列、数値を引数にすることができる（つまり、\ *マクロの引数*\ と書いてある部分は、変数、文字列、数値に好きに置き換えることができ、それが呼び出すマクロに渡される）。例えば、こういう例を考えてみよう：

.. raw:: html

   <div style="color:gray">

-  There is a `Library Token <Library_Token>`__ called "'Lib:MT''' which
   has a macro called **Use Power**.
-  You have a token for Bork the Brave, which has a macro called
   **Shield Bash**. This is one of Bork's powers.
-  You want to send the name of the power to **Use Power**, which will
   run the standard procedures to resolve the use of a power.

.. raw:: html

   </div>

-  **Lib:MT**\ という名前の\ `Library
   Tokenがあり <Library_Token>`__\ 、その中には\ **Use
   Power**\ というマクロがあるとする。
-  勇者ボークのトークンがあって、そのトークンは\ **Shield
   Bash**\ というマクロを持っている。これはボークのパワーの一つだ。
-  **Use
   Power**\ マクロに対してパワーの名前を渡したい。このマクロはパワーの使うときの標準処理を行ってくれる。

.. raw:: html

   <div style="color:gray">

To have Bork's macro trigger the **Use Power** macro on **Lib:MT**, you
would create a macro called "Shield Bash", which contained the following
command:

.. raw:: html

   </div>

ボークのマクロが **Lib:MT**\ の\ **Use
Power**\ マクロを呼び出すには、以下のコマンドを持つ\ **Shield
Bash**\ マクロを作成しなければならない。

.. raw:: html

   <div style="color:gray">

..

   .. code:: mtmacro

      [macro("Use Power@Lib:MT"): "Shield Bash"]

.. raw:: html

   </div>

..

   .. code:: mtmacro

      [macro("Use Power@Lib:MT"): "Shield Bash"]

.. raw:: html

   <div style="color:gray">

So, that's great. You've sent this information off to the macro **Use
Power**. But...how does **Use Power** recognize what you sent it?

.. raw:: html

   </div>

よろしい。これでマクロ\ **Use
Power**\ に情報を渡すことができた。ところで…\ **Use
Power**\ マクロの方はこの情報をどういうふうに認識するのだろうか？

.. _特殊変数_macro.args:

特殊変数 *macro.args*
~~~~~~~~~~~~~~~~~~~~~

.. raw:: html

   <div style="color:gray">

Whenever you create a macro call and execute it, a special variable
called is created. This variable is visible (that is, can be accessed,
changed, or read) only by the macro being called, and it contains
whatever you substituted in for *macro_arguments*. So, in our example
above, is equal to "Shield Bash". So, for example, in the macro **Use
Power**, you might have a line that says:

.. raw:: html

   </div>

マクロを呼び出すと、という特殊変数が生成される。これは呼び出された側のマクロだけから見える（つまり、アクセス、変更、読み出しが可能な）変数で、\ *マクロの引数*\ の部分に入れたものがすべて格納されている。だから上の例で言うなら、
は"Shield Bash"と等しいことになる。なので、例えば、\ **Use
Power**\ マクロの中にはこういう部分があるはずだ：

.. raw:: html

   <div style="color:gray">

..

   .. code:: mtmacro

      [h:powerName = macro.args]

.. raw:: html

   </div>

..

   .. code:: mtmacro

      [h:powerName = macro.args]

.. raw:: html

   <div style="color:gray">

What that line says is, "in this macro, take the value of , and assign
it to the variable ." From then on out, the variable will have the value
"Shield Bash" (if we continue our example from above). Note that you
don't *have* to do this - you can also just refer to wherever you need
to.

.. raw:: html

   </div>

ここでは、「このマクロでは、の値を読み出し、これを変数に代入しろ」と言っていることになる。これ以降、変数は"Shield
Bash"という値を取る（上の例のままになっていれば、だが）。なお、必ずしも\ *この通りにしなくても良い*\ という点には注意。必要ならどこででも
を参照していい。

.. raw:: html

   <div style="color:gray">

The macro being called can then use this special variable like any other
variable - it can read it, it can change it, it can add it to something
- anything you would do with a variable. You could even ignore it!

.. raw:: html

   </div>

ここで、呼び出されたマクロは他の変数と全く同じように
を使うことができる。読み出しても、変更しても、他の何かと連結させてもいい。他の変数に出来ることなら何でもしていい。何なら全く使わなくても構わないんだ。

.. raw:: html

   <div style="color:gray">

Of course, if you've sent information in one direction - from the caller
to the callee, so to speak - what if you need to send information the
other way (in other words, *return* a value)?

.. raw:: html

   </div>

もちろんこの情報は、呼び出し側から呼び出される側への一方通行になる。では、その反対方向に情報を渡したい（つまり、値を\ *返したい*\ ）ときにはどうしようか？

.. _特殊変数_macro.return:

特殊変数 *macro.return*
~~~~~~~~~~~~~~~~~~~~~~~

.. raw:: html

   <div style="color:gray">

In the macro that is being called, you can do a lot of processing on the
variable . You can output text to chat and update token properties,
even. But you migh also want the results of all that processing to be
sent *back* to the calling macro - maybe you use it to create *part of*
a string, and you need to send that piece back to be assembled into the
final output you want to send to chat.

.. raw:: html

   </div>

呼び出され側のマクロの中では、
にさまざまな処理を加えることができる。テキストをチャットに出力し、トークンの属性値を更新したりも。だが、関数の中で行われた処理の結果を呼び出し側のマクロに送り\ *返し*\ たりもしたいんじゃないだろうか。おそらく、それを文字列の\ *一部*\ として組み込み、最後にチャットに出力するようにするのに使えるだろう。

.. raw:: html

   <div style="color:gray">

In that case, you can assign whatever value you want to send back to the
variable , which will be sent back to the calling macro. Assume, then,
that the macro **Use Power** creates a variable called that needs to be
sent *back* to Bork's macro **Shield Bash** before it finishes. To do
this, somewhere at the end of **Use Power**, you'd add this line:

.. raw:: html

   </div>

この場合、返したい値をに代入すればうまくいく。この変数は呼び出し側のマクロに返されるのだ。では、\ **Use
Power**\ マクロがという変数を生成したとして、それを戦士ボークの\ **Shield
Bash**\ マクロへ、それが実行を終える前に返さなければならないのだと考えよう。これを行うには、\ **Use
Power**\ マクロのどこかにこういう部分を追加する必要があるだろう：

.. raw:: html

   <div style="color:gray">

..

   .. code:: mtmacro

      [h:macro.return = powerResultText]

.. raw:: html

   </div>

..

   .. code:: mtmacro

      [h:macro.return = powerResultText]

.. raw:: html

   <div style="color:gray">

You've said in that line that the special variable will be equal to
whatever is set to, and **Shield Bash** can then use the variable for
further processing.

.. raw:: html

   </div>

ここで、特殊変数の値は と同じになる。そして\ **Shield
Bash**\ マクロはこのを使って処理を続けることができるのだ。

二つのマクロを並べて見てみる
----------------------------

.. raw:: html

   <div style="color:gray">

The examples below are the two macros discussed above, side by side, to
illustrate the use of macro calls and the and variables. Make sure to
check out the `Sample Ruleset <Sample_Ruleset>`__ if you're not familiar
with some of the various game terms. Also, note that these are not
*complete* macros that include all of the possible classes and powers in
the game, but a sampling to illustrate the use of .

.. raw:: html

   </div>

以下の例はこれまでに述べてきた二つのマクロだ。マクロの呼び出しや、二つの変数
と を説明するために二つ並べておいた。
もしまだゲームの用語に不慣れなら、\ `Sample
Rulesetで確認してほしい <Sample_Ruleset>`__\ 。また、ここにあるのは、ゲーム内に登場するすべてのクラスやパワーを網羅したマクロの\ *完成品*\ ではなく、の説明のためのサンプルだという点に留意してほしい。

.. raw:: html

   <div style="color:gray">

===================================================================================== =================================================================================
Shield Bash Macro                                                                     Use Power Macro
===================================================================================== =================================================================================
.. code:: mtmacro                                                                     .. code:: mtmacro
   :number-lines:                                                                        :number-lines:
                                                                                     
   <!-- Call the Use Power macro -->                                                     <!-- Receive macro arguments -->
                                                                                         [h:powerName = macro.args]
   [MACRO("Use Power@Lib:MT"): "Shield Bash"]                                        
                                                                                         <!-- Do a switch to find the power's Attack Bonus -->
   <!-- Receive the variable macro.return after Use Power has finished processing.-->    [h,switch(powerName):
                                                                                         case "Sword": attackBonus = 2;
   [h:hitValue = macro.return]                                                           case "Bow":  attackBonus = 0;
                                                                                         case "Shield Bash": attackBonus = -1;]
   <!-- Use IF to check the value of hitValue, and choose an option -->              
                                                                                         <!--Make the Attack Roll-->
   [h,if(hitValue == 1),CODE:                                                        
   {                                                                                     [h:attackRoll = 1d20 + Strength + attackBonus]
     [damageRoll = floor((1d6+Strength)/2)]                                          
     [special = "Roll 1d6. On a 4 or better, the foe is stunned for three rounds."]      <!-- Check to see if the attack succeeds (a roll of 15 or higher is a hit) -->
   };                                                                                
   {                                                                                     [h,if(attackRoll >= 15),CODE:
     [damageRoll = "None"]                                                               {
     [special = "No special effect."]                                                      [successText = "a success!"]
   }]                                                                                      [hit = 1]
                                                                                         };
   <!-- Display the Damage result and special effect -->                                 {
                                                                                           [successText = "a failure."]
   <b>Damage: </b> [r:damageRoll]<br>                                                      [hit = 0]
   <b>Special: </b> [r:special]                                                          }]
                                                                                     
                                                                                         <!--Display the attack result and the success, and then send
                                                                                          back the success info for final processing-->
                                                                                     
                                                                                         The [r:powerName] attack is [r:successText].<br>
                                                                                         [h:macro.return=hit]
===================================================================================== =================================================================================

.. raw:: html

   </div>

======================================================================== =============================================================================
Shield Bash マクロ                                                       Use Power マクロ
======================================================================== =============================================================================
.. code:: mtmacro                                                        .. code:: mtmacro
   :number-lines:                                                           :number-lines:
                                                                        
   <!-- Use Power マクロを呼び出す -->                                      <!-- マクロ引数を受け取る -->
                                                                            [h:powerName = macro.args]
   [MACRO("Use Power@Lib:MT"): "Shield Bash"]                           
                                                                            <!-- パワーの Attack Bonus を決めるために switch を使う -->
   <!-- Use Powerの実行が終わるまえに、変数 macro.return を受け取る -->     [h,switch(powerName):
                                                                            case "Sword": attackBonus = 2;
   [h:hitValue = macro.return]                                              case "Bow":  attackBonus = 0;
                                                                            case "Shield Bash": attackBonus = -1;]
   <!-- IF を使って変数 hitValue の値をチェックし、オプションを選ぶ --> 
                                                                            <!-- 攻撃ロールを行う -->
   [h,if(hitValue == 1),CODE:                                           
   {                                                                        [h:attackRoll = 1d20 + Strength + attackBonus]
     [damageRoll = floor((1d6+Strength)/2)]                             
     [special = "1d6を振り、4以上が出たら敵一体が3ラウンドの間気絶する"]    <!-- 攻撃が成功したかどうか判定する（出目が15以上なら命中） -->
   };                                                                   
   {                                                                        [h,if(attackRoll >= 15),CODE:
     [damageRoll = "None"]                                                  {
     [special = "特殊効果なし"]                                               [successText = "命中！"]
   }]                                                                         [hit = 1]
                                                                            };
   <!-- ダメージの結果と特殊効果を表示する -->                              {
                                                                              [successText = "はずれ！"]
   <b>ダメージ: </b> [r:damageRoll]<br>                                       [hit = 0]
   <b>特殊効果: </b> [r:special]                                            }]
                                                                        
                                                                            <!--　攻撃の結果と成否を表示し、最後の処理を行うために成否の情報を返す -->
                                                                        
                                                                            The [r:powerName] の攻撃は [r:successText].<br>
                                                                            [h:macro.return=hit]
======================================================================== =============================================================================

`Category:MapTool <Category:MapTool>`__
`Category:Tutorial <Category:Tutorial>`__
