{{\#customtitle:はじめてのマクロ分岐|はじめてのマクロ分岐}}

## はじめに

<div style="color:gray">

When you write a macro, you'll frequently find yourelf wanting to either
repeat an operation several times, or to choose from several options
based on the outcome of a macro command. In game terms, you might want
to make an damage roll several times in a row (say, one time for each
enemy caught by a grenade blast), or you might want your macro to give
you a damage roll *if* you hit, and say  if you miss.

</div>

マクロを書いていると、何度も同じ処理を繰り返したり、マクロ・コマンドの結果に応じて複数の選択肢から一つを選んで実行したりしたくなることが良くある。ゲームを例に取るなら、（例えば手榴弾の爆発に複数の敵を巻き込んだときのように、）何度も続けてダメージ・ダイスを振りたいこともあるだろうし、また、*もし*攻撃が命中したらダメージ・ダイスを振り、外したら
と表示してくれるようなマクロを作りたいと考えるかも知れない。

<div style="color:gray">

In programming jargon, those concepts are called *looping* (where you go
through a process repeatedly, or "loop through it"), and *branching*
(where your program - in this case, the macro - "branches" down
different paths). The MapTool macro language has several roll options
(and one function) to let you branch and/or loop your commands.

</div>

プログラム用語では、こういう概念を*繰り返し*（一つの処理を繰り返す）と*分岐*（プログラム―ここではマクロだが―が異なる複数の処理に枝分かれする）と呼ぶ。MapToolのマクロ言語にはダイスを振るための複数のオプション（や関数）があり、これであなたの命令を分岐・繰り返しさせることができる。

<div style="color:gray">

Finally, because there are a lot of times when you'll want to do
*several* things at the same time when you branch or loop, there's a
special roll option called *code* that tells MapTool to treat several
macro commands as a single "unit" when you loop or branch. That may
sound confusing, but you'll see what it all means shortly\!

</div>

そして最後に、分岐や繰り返しを使って一度に*複数の*事をさばきたいと感じるのは良くあることなので、繰り返しや分岐の際に複数のマクロ・コマンドをまとめて一つの「単位」として扱える*code*というオプションも用意されている。ちょっと分かりにくいかも知れないが、すぐに分かるようになる。

<div style="color:gray">

Since there's a lot of ground to cover, this tutorial will cover
*branching* (running different commands based on some condition). The
[Introduction to Macro Loops](Introduction_to_Macro_Loops "wikilink")
will handle looping (running a process repeatedly, until you wish it to
stop).

</div>

話さなければならないことが沢山あるので、このチュートリアルでは*分岐*（ある条件によって異なる命令を実行する）について説明することにする。繰り返し（ある処理を止めるまで繰り返す）については[Introduction
to Macro Loopsで解説する](Introduction_to_Macro_Loops "wikilink")。

## 想定する読者

<div style="color:gray">

We're going to get to using these options pretty fast, so I assume
you've read the [Introduction to Macro
Writing](Introduction_to_Macro_Writing "wikilink") and have knowledge of
how to create a new macro and use some very basic commands in it (like
creating a variable or a dice roll).

</div>

これから急ぎ足でいろいろなオプションを使っていくことになる。そんなわけで、[Introduction to Macro
Writingを読み終え](Introduction_to_Macro_Writing "wikilink")、新しいマクロの作り方を知っていて、その中に含まれていた（変数を作ったり、ダイス振りをしたりするなどの）基本的なコマンドが使えると想定することにする。

<div style="color:gray">

There are a couple concepts that should be introduced first, since
they're going to be a great way to illustrate some of the branching
concepts (and looping concepts, in the [Introduction to Macro
Loops](Introduction_to_Macro_Loops "wikilink"). You'll get an
explanation of the new concepts below.

</div>

まず最初にいくつかの概念を理解してもらうが、これは分岐という概念を（そしてこの先[Introduction to Macro
Loopsで説明する繰り返しの概念を](Introduction_to_Macro_Loops "wikilink")）理解するという大変な作業を行うために必要だからだ。その新しい概念について、これから説明していこう。

## 新しい概念: CODE オプション

<div style="color:gray">

Normally, in any branching or looping technique, MapTool lets you do
*one thing* - that is, one command. So if you had a statement that said
"if a condition is true, do something cool," then "something cool" can
only be one single thing - you might roll some dice, or assign a
variable, or print out some text to the chat window. However, you
couldn't roll some dice, assign a variable, assign *another* variable,
do some math, and *then* print out something all in that statement.
That's too many operations.

</div>

MapToolでは、分岐や繰り返しの技法を使うと、*一つのこと*しかできないのが普通だ。この一つのこととは、つまりコマンド１個ということだ。だから「もしある条件が満たされたなら、なにかイケてることをしろ」では、この「なにかイケてること」の部分には一つのことしか入れられない。ダイスを振るとか、変数を宣言するとか、チャット・ウィンドウになにかのテキストを表示するとか、だ。しかし、ダイスを振って、変数を宣言して、さらに*もう一つ*変数を宣言して、計算を行い、*それから*そのなにかを出力する、といった処理はできない。処理の数が多すぎるからだ。

<div style="color:gray">

If you could only do one thing when you branch or loop, macros would be
very limited - so the macro language supports a special roll option
called , which indicates to MapTool that you want to do several things
at once, but have them all happen as a single "branch" or "loop." You
would group these several commands inside a pair of curly braces ( { }
).

</div>

分岐や繰り返しを使うと一つのことしかできないというのでは、マクロの可能性は限られたものになってしまう。そこで、マクロ言語は特殊なロールのオプションを用意している。これがだ。これは、複数の処理を行いたいが、それが「分岐」や「繰り返し」の一つとして行われるべきだということをMapToolに伝えるためのものだ。複数のコマンドを一組の中カッコ（{}）の中に書く。

<div style="color:gray">

The examples below will use the  option, so you can see how it works.

</div>

以下の例ではのオプションを使っている。その仕組みが分かってもらえるだろう。

## 新しい概念: 比較演算子と論理演算子

<div style="color:gray">

In macro writing, you're going to want to compare values together a lot
- is my dice roll greater than 20? Are my hit points less than 0? Does
that weapon name equal "Warhammer?" All of these are handled via
comparison operators and logical operators.

</div>

マクロを作成する場合、二つの数値を比べたいと考えることがよくある。ダイスの出目は20より大きいか？ ヒットポイントは 0　より小さいか？
その武器の名前は "Warhammer" と等しいか？

<div style="color:gray">

*Comparison Operator* is programming jargon for the symbols we use to
have MapTool compare two values to each other in certain ways (an
*operator* is a symbol that performs an operation - for instance, the +
symbol is an operator that adds things together).

</div>

*比較演算子*とはプログラミングで用いる用語で、MapToolで二つの値を特定の基準で比べあうときに使う記号のことだ（*演算子*とは、ある演算を行うための記号だ）。例えば＋記号は加算を表す。

<div style="color:gray">

A *Logical Operator* is a symbol you use to instruct MapTool in what
order to consider comparisons, and how to group comparisons together.
The comparison and logical operators are described below:

</div>

*論理演算子*は、MapToolに対してどういう順番で比較を解釈したらよいか、それをどうまとめるかを教えるための記号だ。比較演算子と論理演算子については以下で説明する：

<div style="color:gray">

In the examples below, the  function is used to illustrate the examples.
It's described in more detail later, but the basic "format" of the
function is this:

</div>

以下の例では、 を使って説明している。これについては後でもう少し詳しく解説するが、基本的なの「文法」は以下の通りだ：

<div style="color:gray">

</div>

<div style="color:gray">

  - **Comparison** is where you do your actual comparison (greater than,
    less than, etc.)
  - **Value_if_true** is where you put the output or value if the
    comparison is true
  - **Value_if_false** is, obviously, where you put the output or
    value if the comparison is false

</div>

  - **比較**は、実際に比較を行う部分（～より大きい、～より小さい、など）
  - **真のときの値**は、比較結果が正しいときに出す出力や取る値を書く部分
  - **偽のときの値**は、当然、比較結果が正しくないときに出す出力や取る値を書く部分　

### 比較演算子

<div style="color:gray">

The symbols below are the comparison operators. Remember that you must
always think of these comparisons from the reference point of the value
on the *left* side. So, in the comparison , you read it based on the
left side: "is  greater than . This is the rule for comparisons in
MapTool - the left side of the operator is the "point of view."

</div>

比較演算子を以下に挙げる。こうした比較は常に*左辺値*を起点として考えねばならない点に注意すること。だから、という比較では、左辺値を基本として「はよりも大きい」と読むことになる。これはMapToolで比較を行う場合の規則だ。演算子の左辺値がかならず比較の「視点」となる。

<div style="color:gray">

  - **==**: "is equal to;" this is the operator you use to see if one
    value is equal to another. Be careful - it has *two* equals signs in
    a row (remember, one equal sign is already reserved for assigning
    values to variable). An example of this comparison would look like
  - **\>**: "is greater than; use this to see if the value on the left
    side is greater than the value on the right. For example: . You can
    put a number on the left side, like  (note that it basically
    reverses the first example, so you need to switch the true and false
    outputs).
  - **\>=**: "is greater than or equal to"; use this to see if the value
    on the left side is greater than *or equal to* the value on the
    right. For example:
  - **\<**: "is less than"; use this to see if the value on the left
    side is *less than* the value on the right. For example, }
  - **\<=**: "is less than or equal to"; use this to see if the value on
    the left side is *less than or equal to* the value on the right. For
    example:
  - \!=: "is not equal to"; use this to compare whether the value on the
    left side is *not equal to* the value on the right. Note that this
    operator doesn't care what the values actually *are*, only that they
    are *not equal*. For example,

</div>

  - **==**: 「～と等しい」
    これは両方の値が等しいことを確認するための演算子だ。間違いやすいので注意して欲しいが、等号は*二つ*並んでいる（等号一つは、左辺値が変数であることを表すときに使われることを思い出して欲しい）。比較の例はこのようになる。
  - **\>**: 「～より大きい」
    これは左辺値が右辺値よりも大きいことを確認するために用いる。例えば、という具合だ。左辺値は数値にすることもでき、その場合はこのようになる。
    （これは単に最初の例を逆にしただけだ。なので、結果が真のときと偽の時の処理を逆にする必要がある）。
  - **\>=**: 「～以上」 左辺値が右辺値*以上*になることを確認するためのもの。例えば、という具合に。
  - **\<**: 「～未満」 左辺値が右辺値*未満*であることを確認するときに使われる。例えば、} のように。
  - **\<=**: 「～以下」 左辺値が右辺値*以下*であることを確認するときに使われる。例えば、 のように。
  - **\!=**: 「～と等しくない」
    左辺値と右辺値が*等しくない*ことを調べるために使うことができる。なお、この演算子はそれぞれの値が実際に*どういう値かは考慮しない*点に注意。単に*等しくない*ことだけを調べている。例えば、
    のように。

### 論理演算子

<div style="color:gray">

The symbols below are the *logical operators*. You use this to group
comparisons together (you only need these if you need to make multiple
comparisons at the same time). These go *between* individual comparisons
(these don't replace the comparison operators above\!).

</div>

以下に挙げる記号が*論理演算子*だ。これらの演算子は組み合わせて使うことができる（が、それが必要なのは一度に複数の比較を行いたい場合だけだろう）。こうした演算子は比較演算子の*間*で使われる（前述の比較演算子を置き換えるものではない）。

<div style="color:gray">

  - **&&**: "and"; use this if you want to make sure that two or more
    comparisons are *all* true. For example:  requires *both*
    comparisons to be true, for the whole comparison group to be true.
    In other words, the roll must be *greater than 1* **and** *less than
    20* in order for it to be a hit. If both of those aren't true, the
    output is .
      - **Remember: if you use &&, every part of the comparison
        statement must be true for the whole comparison to be true\!**
  - **||**: "or"; use this if you want or need only one out of multiple
    comparisons to be true, in order for the whole thing to be true. For
    example, . In the example, if *either* condition is true (that is,
    if  is "dead" *or* "dying") the entire comparison group is true.
    Only if *neither* comparison is true does the whole thing become
    false.
      - **Remember: use || if you only need one out of several
        comparisons to be true**

</div>

  - **&&**: 「かつ」
    これは複数の比較が全て真になるかどうかを確かめるときに用いる。例えば、とした場合、二つの比較の*両方とも*真となり、比較群全体としても真となることが求められている。
    言い換えると、命中するためには、ダイスの出目は*１より大きく*て、*かつ*、*２０未満*でなければならないことになる。この両方が真にならない場合、出力結果はになる。
      - **注意： 全ての比較条件を && で結んだ場合、その全てが真にならないと、全体の結果も真にならない。**
  - **||**: 「または」
    は、複数の比較のうちどれかが真であれば、全体が真となる場合に使用する。例えば、というように。この例では、*どちらかの*条件が真なら（つまり、が"死亡"または"瀕死"なら）、比較群全体が真になる。*両方とも偽*である場合にのみ、全体が偽となる。
      - **注意： 複数の条件のうち一つでも真になればよいときだけ、|| を使うこと。**

## IF: 値を比較する

<div style="color:gray">

One of the most elementary ways to branch any code is the use of the
idea of *if - then*. That is, *if* some comparison is true, *then* do
something else. You would use the *if* concept to say "If my attack
hits, then show the damage result\!"

</div>

あらゆるコードで使われる中でも最も基本的な分岐の方法は*if -
then*だ。つまり、*if(もし)*何らかの比較結果が真になる、*then(なら)*何か特別なことをする。この*if*は、「もし、私の攻撃が命中したら、ダメージ値を表示する！」というように使うことになるだろう。

<div style="color:gray">

MapTool's macro language has two kinds of if - a function (a function is
a pre-defined set of instructions that you can "call" by referring to it
by name), and a roll option (a roll option is a "switch" or "toggle"
that tells MapTool how to handle a command.

</div>

MapToolのマクロ言語には二種類の if
がある。―関数とロール・オプションだ。関数とは、あらかじめ定義されている一連の命令のことで、名前をつかってそれを「呼び出す」ことができる。ロール・オプションとは、MapToolに対してある命令の扱い方を教えるための「スイッチ」とか「トグル」のことだ。

### if() 関数

<div style="color:gray">

The  function is called simply by writing  and putting the thing you
want compared, what to do if the comparison is true, and what to do if
the comparison is false, all inside the parentheses. The general format
is:

</div>

関数は単にと書いて、比較すべきものと、その結果が真になったときにすることと、偽になったときにすることを、全てカッコの中に入れるだけで使える。基本的な文法はこうなる：

<div style="color:gray">

>

</div>

>

<div style="color:gray">

An actual example would look like:

</div>

そして実際の例はこんな風になる：

<div style="color:gray">

>
>
> ``` mtmacro
> [if(attackHits == "yes", "You hit!", "You missed")]
> ```

</div>

>
>
> ``` mtmacro
> [if(attackHits == "yes", "命中！", "外れ")]
> ```

<div style="color:gray">

In that single line, we've said:

</div>

この一行でやらせていることは以下のとおり：

<div style="color:gray">

  - Check the variable  to see if it has the value "yes"
  - If it has the value "yes", then print  to chat, or
  - If it does *not* have the value "yes", then prin  to chat

</div>

  - 変数 の値が"yes"かどうかを確認
  - 値が"yes"なら 、
  - 値が"yes"*でない*なら と、チャットに表示する。

<div style="color:gray">

The *value_if_true* and *value_if_false* parts of the  statement can
be text, dice roll commands (like 1d6 or 1d20), or variables. What they
*cannot* be is variable assignments - that is, you can't write an
statement like this:

</div>

関数の中の、*真の時の値*と*偽の時の値*の二つの部分はテキストでも、ダイスロール・コマンド（1d6とか1d20とか）でも、変数でも構わない。そこに*入れてはいけない*のは、変数の代入だ。つまり、をこういう風には書けないことになる：

<div style="color:gray">

>
>
> ``` mtmacro
> [if(attackHits=="yes", output = "You Hit!", output = "You missed")]
> ```

</div>

>
>
> ``` mtmacro
> [if(attackHits=="yes", output = "命中！", output = "外れ")]
> ```

<div style="color:gray">

It may seem like a good idea, but it won't work - MapTool will give
what's known as a *null pointer exception*, and the macro will fail.
However, there is a trick to get around that: since  is a function, and
all functions - when they run - produce a *value*, you can assign the
*result* of it to a variable\! You would do it like this:

</div>

一見よさそうに見えるが、これはうまくいかない。これをやると、MapToolは俗に「ヌルポインター例外」と呼ばれるものを出し、マクロはエラーを起こしてしまう。しかし、これをうまく回避するワザもある。は関数であり、すべての関数は実行すると*値を返す*のだから、その*戻り値*を変数に代入することができるんだ。こんな風に：

<div style="color:gray">

>
>
> ``` mtmacro
> [output = if(attackHits=="yes", "You Hit!", "You missed")]
> ```

</div>

>
>
> ``` mtmacro
> [output = if(attackHits=="yes", "命中！", "はずれ")]
> ```

<div style="color:gray">

When you do it that way, MapTool will:

</div>

このように書いておくと、MapToolはこんな風に動く：

<div style="color:gray">

  - First, decide what the result of the  is, and
  - Second, assign that *result* to the variable , which you can then
    use like any variable

</div>

  - まず、の値を求め、それから
  - 次に、その*戻り値*を変数に代入し、それを他の変数と同じようにいろいろ使う

###  ロール・オプション

<div style="color:gray">

In addition to , there is another way to employ the concept of "if-then"
in macro code. The  *roll option*. Roll options are, as mentioned above,
effectively "switches" or "toggles" that you set for a macro command
that affect how MapTool will handle it. A couple simple roll options are
mentioned in the [Introduction to Macro
Writing](Introduction_to_Macro_Writing "wikilink") - things like  and
for hidden or expanded output, for example.

</div>

の他にも、「もし～ならば～」の概念をマクロ・コードで使う方法がもう一つある。それがの*ロール・オプション*だ。ロール・オプションとは、前述したとおり、あらかじめ与えておいたマクロ・コマンドの扱い方をMapToolに「切り替え」あるいは「トグル」させるためのものだ。[Introduction
to Macro
Writingにはそのいくつかが載っている](Introduction_to_Macro_Writing "wikilink")。やなどがそれだ。

<div style="color:gray">

Roll options must follow these rules:

</div>

ロール・オプションは以下の規則に従わねばならない：

<div style="color:gray">

1.  Appear at the beginning of a macro command
2.  If only **one** roll option is on the line, it ends with a colon.
    For example:
3.  If *multiple* roll option are on the same command, they are
    separated by commas, and the *last* one is followed by a colon. For
    example,
4.  If a roll option takes an *argument* - that is, it has parentheses
    and wants you to put something in them, like a comparison - the
    colon (or comma, if there are multiple roll options) goes *after*
    the parentheses. Look at the examples below to see how it's used.

</div>

1.  マクロ・コマンドの先頭につける
2.  その行内に現れるロール・オプションが*'一つだけ*なら、オプションはコロンで終わる。例：
3.  同じに現れるロール・オプションが*複数ある*なら、コンマで区切り、最後にコロンをつける。例：
4.  ロール・オプションが*引数*を持つ場合、つまり、比較をするときのように、そのオプションには小カッコがついていて、その中に何かを入れたい場合、コロン（複数のロール・オプションがある場合はコンマも）はその小カッコの*後ろ*に来る。どうなるかは以下の例を見て欲しい。

<div style="color:gray">

To use the  option as a comparison, you must follow the format:

</div>

オプションを比較に使う場合、以下の文法を使わなければならない：

<div style="color:gray">

>
>
> ``` mtmacro
> [if(comparison): command_if_true; command_if_false]
> ```

</div>

>
>
> ``` mtmacro
> [if(比較): 真のときのコマンド; 偽の時のコマンド]
> ```

<div style="color:gray">

  - **Comparison**: this is a comparison statement, as used in the
    above.
  - **Command_if_true**: this is the command to execute if true; in
    this form of IF, you *can* do variable assignments or commands that
    you cannot do in the  method. However, it doesn't *have* to be a
    whole command - it can still be a bit of text.
  - **Command_if_false**: this is the command to execute if false.
    This is an optional statement - if you want it to do nothing if the
    comparison is false, then leave off the semicolon and the  part
    entirely.

</div>

  - **比較**： これは比較文を表している。前述したで使われたのと同じだ。
  - **真のときのコマンド**：
    これは真の時に実行されるコマンドを表す。この形式のIFでは、コマンドだけでなく、では不可能だった変数への代入ができる。なお、この部分はコマンドでなくても構わない。テキストでもいいのだ。
  - **偽のときのコマンド**：
    これは偽の時に実行されるコマンドを表す。この部分はオプショナルであり、比較結果が偽のときにしたいことがなければ、セミコロンも、その後ろのも書かなくていい。

<div style="color:gray">

An example of the use of the  roll option might be:

</div>

ロール・オプションの例は以下の通りだ：

<div style="color:gray">

>
>
> ``` mtmacro
> [h,if(attackHits == "yes"): output="You hit!"; output="You missed"]
> Result of your attack: [r:output]
> ```

</div>

>
>
> ``` mtmacro
> [h,if(attackHits == "yes"): output="命中！"; output="外れ"]
> 攻撃結果: [r:output]
> ```

<div style="color:gray">

In the above example, the following things are happening:

</div>

上の例では、以下のように処理されている：

<div style="color:gray">

  - MapTool compares the value of  to the value
      - If the comparison is *true* - that is, the value of  is *indeed*
        equal to  - it assigns the value  to the variable .
      - If the comparison is *false* - the value of  is *not equal to*
        - it assigns the value  to the variable .
  - It then prints a short line of text and the value of  to chat.

</div>

  - MapToolはの値との値とを比較する
      - 比較結果が*真*になったら、つまり、が*本当に*と等しいなら、変数にの値を代入する。
      - 比較結果が*偽*になったら、つまり、{code|attackHits}}がと*等しくない*なら、変数にの値を代入する。
  - そして、短いテキストとの値をチャットに表示する。

<div style="color:gray">

You'll note that the first line - the line that uses if - has ***two***
roll options on the same line:  and . You'll also see that they are
separated by a comma, and the colon goes *after* the last roll option,
and *before* the commands in the  and  sections.

</div>

１行目で気づいた人もいるだろう。ここでは一つの行で、 と
の*二つ*のロール・オプションを使っている。この二つのオプションはコンマで区切られていて、コロンは最後のロール・オプションの後ろ、とのセクションの前にある。

### IF と CODE

<div style="color:gray">

So what if you want to do more than one thing based on a comparison?
Say, set a bunch of variables to a certain value? For that, you use the
roll option.

</div>

比較の結果としてやりたいことが複数あったらどうしたらいいだろうか？ 例えば、複数の変数にそれぞれ値を代入するとか？
それにはロール・オプションが使える。

<div style="color:gray">

Like all roll options,  is put at the beginning of the line, separated
from other roll options by a comma. Macro programming convention (that
is, the way most macro writers seem to do it) is to put  as the last
roll option in the list. So, the general format you will see in a macro
is likely to be:

</div>

他のロール・オプションと同じように、は行の先頭に置き、他のロール・オプションとはコンマで区切る。マクロプログラミング規約（要は、ほとんどのマクロがそうなってるって意味だ）では、
をロール・オプションの一番最後につけることになっている。だから、マクロの中では一般にはこんな風になる：

<div style="color:gray">

>
>
> ``` mtmacro
> [roll_option1, roll_option2, code: macro_commands]
> ```

</div>

>
>
> ``` mtmacro
> [roll_option1, roll_option2, code: macro_commands]
> ```

<div style="color:gray">

The second component of the  option is the curly bracket ({ }). You use
these to enclose multiple commands as a single group. Remember the
format of the  roll option?

</div>

オプションの二番目の要素は中カッコ（{}）だ。これを使って複数のコマンドを一つの群にまとめる。ロール・オプションの文法を覚えているかな？

<div style="color:gray">

>
>
> ``` mtmacro
> [if(comparison): command_if_true; command_if_false]
> ```

</div>

>
>
> ``` mtmacro
> [if(comparison): 真のときのコマンド; 偽のときのコマンド]
> ```

<div style="color:gray">

Well, the  option lets you replace  and  with *multiple* macro commands.
Let's look at an example:

</div>

さて、オプションでは  と  に*複数の*マクロ・コマンドを置くことができる。例を見てみよう：

<div style="color:gray">

Suppose we write a macro to look at a variable called . We want to
compare it to a number (the target number), which is held by the
variable . Here's what we want the macro to do:

</div>

これからという変数の値を調べるマクロを書くとしよう。そしてこれをある値（目標値）と比較しようと考えている。この値はという変数に格納されている。マクロにやらせたいのはこういうことだ：

<div style="color:gray">

If  is greater than or equal to , the macro should:

  - Set  to "yes"
  - Set  to "hits"
  - Set  to 3
  - Set  to the result of the dice roll 1d8+4.
  - Output a string telling the user the results.

</div>

もし  が  以上なら：

  - に "yes" をセット

  - に "命中" をセット

  - に 3 をセット

  - には 1d8+4　の結果をセット

  - ユーザーにその結果を知らせる文字列を表示する

<div style="color:gray">

If  is *not* greater than or equal to , the macro should:

  - Set  to "Yes"
  - Set  to "misses"
  - Set  to 3
  - Set  to "no"
  - Output a string to chat telling the user the results.

</div>

もし  が *未満*なら：

  - に "yes" をセット

  - に "外れ" をセット

  - に 3 をセット

  - には "no" をセット

  - ユーザーにその結果を知らせる文字列を表示する

<div style="color:gray">

Here's how to do it:

</div>

では、以下にそのマクロを載せる：

<div style="color:gray">

>
>
> ``` mtmacro
> [h:attackRoll = 1d20]
> [h:targetNumber = 15]
>
> [h,if(attackRoll >= targetNumber), code:
> {
>   [attackUsed = "yes"]
>   [attackResult = "hits"]
>   [attackRecharge = 3]
>   [damageRoll = 1d8+4]
> };
> {
>   [attackUsed = "yes"]
>   [attackResult = "misses"]
>   [attackRecharge = 3]
>   [damageRoll = "no"]
> }]
>
> Your attack [attackResult], and you do [damageRoll] damage. Your attack will recharge in [attackRecharge] rounds.
> ```

</div>

>
>
> ``` mtmacro
> [h:attackRoll = 1d20]
> [h:targetNumber = 15]
>
> [h,if(attackRoll >= targetNumber), code:
> {
>   [attackUsed = "yes"]
>   [attackResult = "命中"]
>   [attackRecharge = 3]
>   [damageRoll = 1d8+4]
> };
> {
>   [attackUsed = "yes"]
>   [attackResult = "外れ"]
>   [attackRecharge = 3]
>   [damageRoll = 0]
> }]
>
> あなたの攻撃は [attackResult] で、与えたダメージは [damageRoll] 点。 次の攻撃ができるまで [attackRecharge] ラウンドかかる。
> ```

<div style="color:gray">

There's a lot going on here, but the important thing to look for is the
CODE option in the very first line, and the curly braces. The curly
braces enclose multiple separate commands, but say to MapTool, "treat
these as one thing". So in the example above:

</div>

ここではいろいろなことをしているが、注目して欲しいのは一番最初の行にある CODE
オプションと、中カッコだ。中カッコの中には複数のコマンドが入っているが、MapToolに対してこれを「一つのものとして扱う」よう指示していることになる。従って、上の例はこのように動作する：

<div style="color:gray">

  - We declare two variables,  and , and give them initial values (in
    this case,  will be the result of a 1d20 roll, and  is set to 15).
  - We set up the comparison (putting an h, in front - remember, that
    will hide the results from chat, so you don't see all the
    calculations in the if statement).
  - We put  in there to warn MapTool that each part of the  roll option
    -  and  - will actually consist of multiple separate commands.
  - We put a colon after the word , to mark off the end of all the roll
    options. There is only ONE colon in the line\!
  - We use a { to mark the start of the  portion of the IF statement. We
    then put in our commands, each one separately and enclosed in square
    brackets. Once finished, we *close* that section of the IF statement
    with a }, and put a semicolon on the end (remember, the IF roll
    option needs a semicolon to separate  from .
  - We do the same process for the  section - a { followed by a series
    of commands, and then closed with a }.
  - We make sure to close off the ***whole*** if statement with another
    square bracket ( \] ). Remember, an IF roll option is still just a
    macro command, and all macro commands must be enclosed in **\[ \]**.
  - Finally, we write some text, with the several variables we have
    inserted at appropriate points, to be sent to chat when the macro
    runs.

</div>

  - 二つの変数  と  を宣言し、初期値を与える（この場合、 は 1d20 の結果、 は15になるはずだ）。

  - 比較条件を設定する（まず最初に h を置く。このオプションをつけるとその結果をチャットに表示しなくなる。従って、この if
    文の計算結果は見えなくなる）。

  - ロール・オプションの中の、 と
    のそれぞれの部分にを置いて、この部分の中には複数のコマンドが入るのだということをMapToolにあらかじめ報せておく。

  - 文の後ろにコロンを置き、ロール・オプションの終端であることを知らせる。この行にあるコロンはこれ一つだけ！

  - IF文の中の、 の最初に { を置く。それからそれぞれ大カッコでくくったコマンドを並べていく。全部終わったら、このセクションを }
    で閉じ、最後にセミコロンをつける（ IF ロール・オプションでは、 と
    を区切るのにセミコロンが必要だということを思い出して欲しい）

  - 上と同じ作業を  のセクションについても行う。 { の後に一連のコマンドを並べ、最後に } で閉じる。

  - ここでこの if 文**''全体を**''大カッコ（ \] ）でくくっておくこと。 IF
    ロール・オプションもマクロ・コマンドの一つであり、全てのマクロ・コマンドは**\[
    \]**でくくられていなければならない。

  - 最後に、それぞれの変数を適当な場所に埋め込んだテキストを書き、マクロが実行されたときにチャットに送り込まれるようにしておく

<div style="color:gray">

**NOTE**: The CODE roll option only works with *other roll options*. You
would not use this with the  *function*. That is a bit confusing, but
just remember: CODE only goes with other roll options.

</div>

**注意**： CODE ロール・オプションは*他のロール・オプション*と組み合わせたときにだけ動作する。*関数*である
とは組み合わせられない。ちょっとややこしいかも知れないが、「 CODE は
ロール・オプションと組み合わせてしか使えない」とだけ、覚えておいて欲しい。

## SWITCH: 複数の選択肢の中から選ぶ

<div style="color:gray">

The  function and the  roll option both let you pick from two options -
either do something when the comparison is *true*, or do something
different when the comparison is *false*. But life - and RPG's - are not
always so black and white. When you want to do different things based on
one of *many* options, you use the  roll option.

</div>

関数とロール・オプションは両方とも二つある処理のどちらか一つを選ぶものだ。比較結果が*真*ならこちら、*偽*ならこちらという具合に。しかし人生というものは、そしてRPGもだが、常に白黒はっきりしたものではない。*複数の*選択肢の中から異なった動作を一つ選ぶ場合には、ロール・オプションを使いたまえ。

<div style="color:gray">

The general format is:

</div>

一般的な文法は以下の通り：

<div style="color:gray">

>
>
> ``` mtmacro
> [switch(val):
> case case_value1: command_1;
> case case_value2: command_2;
> case case_value3: command_3;
> default: command_Default]
> ```

</div>

>
>
> ``` mtmacro
> [switch(val):
> case 第1の値: 第1のコマンド;
> case 第2の値: 第2のコマンド;
> case 第3の値: 第3のコマンド;
> default: デフォルトのコマンド]
> ```

<div style="color:gray">

What's happening here is this:

</div>

MapToolはこういう風に動作する：

<div style="color:gray">

  - MapTool is looking at the value of the variable
  - MapTool then looks at each of the  statements in the switch, and
    compares  to , , and
  - When MapTool finds a match - that is,  is equal to one of those
    cases, the appropriate command (either , , or ) is executed, and
    then MapTool exits the switch statement (which just means, once it's
    found a match, it does what that case says, and then stops checking
    for matches).

</div>

  - 変数  の値を調べる
  - それから switch の中の  文を一つ一つ見ていって、 を 、、 と比較する
  - 一致する値が見つかったら、つまり  が case
    文のどれかと等しくなったら、それに該当するコマンドを（、、のいずれかを）実行する。それが終わったら、switch
    文を抜ける（要は、一致するものを探して、そこに書いてある通りのことをして、そこで探すのをやめる、ということだ）。

<div style="color:gray">

Suppose, for example, that the we wanted a macro that would
automatically assign the right  value to a token, based on the token's .
If you've been following along, you might recognize the **Armor** value
as one of the attributes in the [Sample
Ruleset](Sample_Ruleset "wikilink"). If you visit the [Sample
Ruleset](Sample_Ruleset "wikilink") page, you'll see that a character
can have one of several armor values, based on the character's class:

</div>

例えば、あるトークンに対して、そのに応じた正しい値を自動的に代入するマクロが欲しいと仮定してみる。ここまで読んできてくれたのなら、ここでいう**Armor**値は[Sample
Rulesetにある属性値の一つだということが分かってもらえるだろう](Sample_Ruleset "wikilink")。[Sample
Rulesetのページを読めば](Sample_Ruleset "wikilink")、キャラクターが自分のクラスに応じていくつかの装甲値(armor
value)のなかから一つを選べることが分かるはずだ：

<div style="color:gray">

  - A **Warrior** has an armor value of 6
  - A **Rogue** has an armor value of 2
  - A **Wizard** has an armor value of 1
  - A **Priest** has an armor value of 4

</div>

  - A **Warrior** の装甲値は 6
  - A **Rogue** の装甲値は 2
  - A **Wizard** の装甲値は 1
  - A **Priest** の装甲値は 4

<div style="color:gray">

So, let's say we want a macro to ask us for the value of the variable ,
and then use that variable to assign the right  value. Here's how we'd
do it:

</div>

そこで、マクロがそのトークンのを質問してくるようにして、その後で正しい値を代入するようしよう。こういう風になる：

<div style="color:gray">

>
>
> ``` mtmacro
> [h:class = "Rogue"]
>
> [h,switch(class):
> case "Warrior": Armor = 6;
> case "Rogue": Armor = 2;
> case "Wizard": Armor = 1;
> case "Priest": Armor = 4;
> default: Armor = 0]
>
> Your Armor Value is [Armor].
> ```

</div>

>
>
> ``` mtmacro
> [h:class = "Rogue"]
>
> [h,switch(class):
> case "Warrior": Armor = 6;
> case "Rogue": Armor = 2;
> case "Wizard": Armor = 1;
> case "Priest": Armor = 4;
> default: Armor = 0]
>
> あなたの装甲値は [Armor]　です。
> ```

<div style="color:gray">

What the above example does is:

</div>

この例で何をやっているかというと、こういうことだ：

<div style="color:gray">

  - Look at the value for  - if you try this out, it will always show
    the value for "Rogue." If you alter the  line, you can see how
    changing that value affects the switch statement).
  - Compare what you put in there with the four different cases -
    checking to see if  is equal to , , , or .
  - If  equals any of those (and we mean EXACTLY equals - case
    sensitive, no spaces, an *exact* match), run the command to set the
    variable  to the appropriate value.
  - If no match is found, do whatever follows the  option (in other
    words, set  to 0.
  - Stop looking for matches, and move on.

</div>

  - 変数の値を調べる。このマクロを試しに動かしてみると、常に "Rogue" の値を表示してくるだろう。 の行を変更すれば、それが
    switch 文にどういう影響を与えるか、分かるはずだ。

  - ここで代入したものを、他の４つの case と比較する。の値が、、、、のどれと等しいか調べる。

  - が上のどれかと同じ値であれば（ここでいう同じとは、「全く同じ」ということだ。大文字小文字やスペースの有無にいたるまで、全く同じでなければならない）、対応するコマンドを実行して、
    に正しい値を与える。

  - どれとも一致しなかった場合、 の後ろにあるとおりに実行する（ここでは、 に 0 をセットする）。

  - そこで探すのを止めて、次の処理へと移動する。

### SWITCH と CODE を組み合わせる

<div style="color:gray">

The  option can be used with a  option, in a similar manner as . There
are a couple tricky bits, but if you follow the pattern given in the
examples, it should work for you.

</div>

以前に  でもできたように、 は
とも組み合わせることができる。多少ややこしいが、例に挙がっているパターンにさえ従っていれば、うまく動いてくれる。

<div style="color:gray">

To do a  option with , the general format is:

</div>

と  とを組み合わせる場合、基本的な文法は以下の通りだ：

<div style="color:gray">

>
>
> ``` mtmacro
> [switch(val),code:
> case case_1: { commands_for_case_1};
> case case_2: { commands_for_case_2};
> case case_3: { commands_for_case_3};
> default: { commands_for_default}]
> ```

</div>

>
>
> ``` mtmacro
> [switch(val),code:
> case 第1のケース: { 第1のケースのコマンド };
> case 第2のケース: { 第３のケースのコマンド　};
> case 第3のケース: { 第３のケースのコマンド　};
> default: { デフォルトのコマンド}]
> ```

<div style="color:gray">

An actual example can be drawn from the [Sample
Ruleset](Sample_Ruleset "wikilink") as well. Not only does a character's
class indicate his or her armor value, but also the list of "Beginning
Powers" from which the character can draw. Suppose we wanted to set not
only the armor value, but also a variable called . To do that, you'd
write a SWITCH that looks like:

</div>

これは [Sample Ruleset](Sample_Ruleset "wikilink")
からそのまま引いてきたもう一つの実例だ。キャラクターのクラスが決めるのは装甲値だけでなく、そのキャラクターが選択できる「作成時パワー」のリストもそれで決まる。装甲値以外にも
 変数も代入したいと仮定する。これを行うには、SWITCH 文を以下のように書けばいい：

<div style="color:gray">

>
>
> ``` mtmacro
> [h,switch(class),code:
> case "Warrior":
> {
>   [Armor = 6]
>   [beginningPowers = "Sword, Shield Bash, Bow, Shield, Torch"]
> };
> case "Rogue":
> {
>   [Armor = 2]
>   [beginningPowers = "Dagger, Hide, Backstab, Pick Lock, Torch"]
> };
> case "Wizard":
> {
>   [Armor = 1]
>   [beginningPowers = "Dagger, Staff, Light, Lightning Bolt, Fire Ball"]
> };
> case "Priest":
> {
>   [Armor = 4]
>   [beginningPowers = "Mace, Heal, Protect, Banish Undead, Torch"]
> };
> default:
> {
>   [Armor = 0]
>   [beginningPowers = "Fists, Feet"]
> }]
>
> Your Armor Value is [Armor] and your beginning powers are [beginningPowers].
> ```

</div>

>
>
> ``` mtmacro
> [h,switch(class),code:
> case "Warrior":
> {
>   [Armor = 6]
>   [beginningPowers = "Sword, Shield Bash, Bow, Shield, Torch"]
> };
> case "Rogue":
> {
>   [Armor = 2]
>   [beginningPowers = "Dagger, Hide, Backstab, Pick Lock, Torch"]
> };
> case "Wizard":
> {
>   [Armor = 1]
>   [beginningPowers = "Dagger, Staff, Light, Lightning Bolt, Fire Ball"]
> };
> case "Priest":
> {
>   [Armor = 4]
>   [beginningPowers = "Mace, Heal, Protect, Banish Undead, Torch"]
> };
> default:
> {
>   [Armor = 0]
>   [beginningPowers = "Fists, Feet"]
> }]
>
> あなたの装甲値は [Armor] で、開始時パワーのリストは [beginningPowers] です。
> ```

<div style="color:gray">

As you can see, each different case is treated as a single block of
operations - so you need to put curly braces for each separate case, and
separate them all with the semicolon. At the very end, we put a closing
square bracket (**\]**), to finish the whole command. Again, what has
happened is that the CODE option and the curly braces have allowed you
to replace a single command, like , with a *group* of commands.

</div>

お分かりのように、それぞれのケースが一つの処理として扱われている。だからそれぞれのケースは中カッコで囲み、セミコロンで区切っておかなければならない。そして一番最後を大カッコ（**\]**）で閉じ、コマンド全体を区切る。ここでも、CODE
オプションを使うことで、 のコマンドを、コマンドの「グループ」で置き換えることができる。

<div style="color:gray">

Also, you'll see that I've added in some line breaks so that each
separate group of operations is easier to read - MapTool is cool with
that, because extra line breaks *inside* a command (remember, commands
are enclosed within **\[ \]**) are ignored. This is nice, because it
makes the macros *much* easier to read.

</div>

なお、読みやすくするために、それぞれの処理グループごとに改行を入れているのが分かると思う。ここはMapToolのいいところで、一つのコマンドの*中*での改行を無視してくれる（一つのコマンドは、**\[**
と **\]** で囲まれているという点に注意）。これはマクロを*大幅に*読みやすくできて、都合がいい。

## 高度な分岐オプション

<div style="color:gray">

The two options illustrated above are the most common branching options
used in macro writing. However, they are not the *only* options for
branching macros - there are two others, which involve either leaving
one macro entirely to call on another, or changing the focus (that is,
what token is the [Current Token](Current_Token "wikilink")) of a macro
temporarily. Since these are fairly complex operations all on their own,
you'll find them in the [More Branching
Options](More_Branching_Options "wikilink") guide.

</div>

ここで説明した二つのオプションは、マクロを書くときに最もよく使われる分岐方法だ。しかし、マクロで分岐を行う手段は*これだけではない*。他にも二つのオプションがあるが、その中には、あるマクロの中から完全に抜け出して別のマクロを呼び出したり、マクロのフォーカスを切り替える（つまり、マクロの[Current
Tokenが表すトークンを一時的に変える](Current_Token "wikilink")）ものが含まれている。こうした処理はそれ単体でもやや複雑なものなので、この先の[More
Branching Optionsガイドで読むことにする](More_Branching_Options "wikilink")。

[Category:MapTool](Category:MapTool "wikilink")
[Category:Tutorial](Category:Tutorial "wikilink")