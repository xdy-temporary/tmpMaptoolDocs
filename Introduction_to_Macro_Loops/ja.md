{{\#customtitle:はじめての繰り返し|はじめての繰り返し}}

はじめに
--------

<div style="color:gray">
We've looked at [branching](Introduction_to_Macro_Branching "wikilink") in macros, using , , and the more advanced roll options and . Branching is one of the most important tools for macro writing, since it lets you automate decisions based on certain factors or conditions that arise during play.

</div>
マクロについては[branchingで](Introduction_to_Macro_Branching "wikilink")とと、さらに高度なオプションである と を使った例を見てきた。マクロ作成においては分岐は非常に重要な道具の一つだが、これはプレイの最中に発生するさまざまな要素や条件に基づいた判断を自動化することができるからだ。

<div style="color:gray">
Another common task in MapTool macros is to repeat a process multiple times - for example, you may want to repeat an attack roll several times, against multiple targets (for instance, if you threw a grenade, you might need to roll to see which targets are hit by the blast), or you may want to go through a list of skills, and print out the skill rating for each one. In both cases, you're repeating the same operation several times in a row, generating different results each time. In macro writing, we call this process *looping* (you may see it described in places as “looping through a list” or “iterating over an array” - regardless, the processes to do it are *loops*).

</div>
MapToolのマクロで共通しているもう一つの重要な道具は、同じプロセスの反復だ。例えば、複数の標的に対して複数回の攻撃ロールを繰り返したいような場合（手榴弾を投げ込んだらどの標的が爆発に巻き込まれたかをそれぞれ判定しなければならないだろう）や、技能の一覧をざっと見てそのレーティングと一緒にプリントアウトしたい場合などがこれにあたる。どちらの場合でも、同じ処理を何度か続けて行って、一回ごとに違った結果を得ている。マクロ作成においては、これを*反復*と呼ぶ（「リスト内をループする」とか「配列の中身を羅列する」とかの表現を見たことがあるだろう。表現はともかく、こうした処理を*反復*と呼ぶのだ）。

<div style="color:gray">
There are four loop structures in MapTool macros: , , , and . Each of the three is a *roll option*, which means - as we've seen before:

</div>
MapTool のマクロには、、 、 、、の4つの反復構造が存在している。これらはいずれも*ロール・オプション*であり、すでに見てきたように：

<div style="color:gray">
1.  It is placed at the beginning of a macro command
2.  It is followed by a colon
    1.  If more than one roll option is used, they are separated by commas, and the *last* one is followed by a colon
3.  After the colon, you place the operation you want to do every time the loop runs

</div>
1.  マクロコマンドの先頭に置かねばならない
2.  次にコロンがついていなければならない
    1.  複数のロール・オプションを使うなら、それぞれコンマで区切らなければならず、*最後の*オプションはコロンで終わらなければならない
3.  コロンの後ろに、ループ1回ごとに処理して欲しい内容を書いておく

<div style="color:gray">
Before we continue, we'll need to introduce a couple concepts that will be used heavily in the examples below, especially for and loops.

</div>
この先に進む前に、以下の例で、中でも と で繰り返し使うことになる概念をいくつか説明しておく必要がある。

新しい概念：文字列リストと文字列プロパティ
------------------------------------------

<div style="color:gray">
RPGs have a lot of information that goes into playing them - there are stats, and skills, and dice rolls, and weapons, and equipment, and powers and magic and...well, you name it, and there's an RPG out there that covers it.

</div>
RPGはプレイを進める上で多くの情報を扱う。能力値、技能、ダイスロール、武器、装備、特殊能力、魔法…などなど、RPGが対応する名前のある全ての情報が溢れている。

<div style="color:gray">
For basic things, it might make sense to create a token property for each piece of information. In fact, you can do this for every possible bit of information you want to record about a character - but already, I bet you're thinking “that's a *lot* of properties”). And it is!

</div>
基本的には、個々の情報をトークンのプロパティとして作成すれば良い。実際に、記録したいキャラクターの情報を登録することは可能だ。だが、君はきっと「*たくさんの*プロパティがある」と思うに違いない。その通りだ!

<div style="color:gray">
Fortunately, there are other ways to store information in MapTool properties (and macro variables) that let you group information together. The two new information storing methods we'll use - which are properly referred to as *data types* - are [string lists](String_List "wikilink") and [string properties](String_Property_List "wikilink").

</div>
幸いにも、MapToolの情報（またはマクロ変数）をまとめて分類し保存する方法は他にもある。下記の延べる収容方法（正確にはデータタイプと呼ぶ）に関する二つの情報は[文字列リストと](String_List "wikilink")[文字列プロパティ・リストだ](String_Property_List "wikilink")。

### 文字列リスト

<div style="color:gray">
A string list is, first, a *string* - that is, a collection of alphanumeric text that is treated as just text (that is, it's not a number, so you can't add it to another number; it's not a dice roll, so MapTool won't automatically roll it; it's just a string of characters).

</div>
まず、文字列リストは*文字列*である。この文字列は、テキストとして扱う英数字から成り立つ（純粋な文字列。数値ではないので、後から数値を追加することは出来ない。ダイスロールではないので MapTool が自動的にロールすることはない。）。

<div style="color:gray">
Second, it is a *list* - a collection of single items, separated by some sort of separating character - the (you guessed it) *separator* (also called a *delimiter*). The separator marks the beginning and end of an individual item in a list. This is a long way of saying “a string list is a single value that is a list of things, like colors: blue, green, red, orange, mauve.”

</div>
第2に、文字列リストは*リスト*である。区切り文字（*セパレーター*とも呼ばれる）と見なされる文字に区切られた項目の集まり。区切り文字はリスト内の個々の項目の始まりと終わりを示す。簡潔に言えば「文字列リストは、一覧（例えば色の一覧：blue, green, red, orange, mauve）を表す単体の値である」。

<div style="color:gray">
Formally - in macro code - a string list looks like:

</div>
文字列リストのマクロ・コードにおける正確な書式は次の通り：

> ``` mtmacro
> [h:listOfColors = "blue, green, red, orange, mauve"]
> ```

<div style="color:gray">
In the example, you'll see that we've made a variable assignment, and given the variable the values . The whole thing is enclosed in double quotes, which tells MapTool that it's a string, and from its very format, MapTool knows that it's a *string list*.

</div>
上記例では、変数定義が書かれていて、変数 に が与えられている。MapTool は文字列を表す二重引用符に挟まれ、規則正しく書式化された箇所を*文字列リスト*であると解釈する。

<div style="color:gray">
A string list can contain anything - it could be a list of names, of numbers, of dice rolls - anything you might want to keep a list of.

</div>
文字列リストは一覧として保持しておきたいあらゆる物（名前の一覧、数値の一覧、ダイス・ロールの一覧など）を含ませることが出来る。

<div style="color:gray">
**However!** It is important to remember that no matter what each item in a string list *is*, it is always treated as a *string*. So if MapTool reads a string list that looks like , it will not see the first item and see a command to roll 1 six-sided die; instead it will see the character “1”, the character “d”, and the character “6”, all put together. They may look the same to us, but they don't look the same to MapTool - to turn that “1d6” into so that MapTool will roll it, we need to use the function to tell MapTool “evaluate that string *as if* it were a dice roll.” You'll see some examples of later on.

</div>
**ただし!** 重要なことだが、文字列リスト内の各項目は*常に文字列*として扱われることを忘れないように。そのため、 のような文字列リストを読んだ MapTool は、最初の項目を1つの6面ダイスをロールするコマンドとは見なさず、「1」の文字、「d」の文字、「6」の文字を組み合わせたものとして解釈される。見た目は同じように感じるが、MapTool にとっては異なるものである。「1d6」を MapTool がロールする にするには、 関数を使い、MapTool に「文字列を*ダイスロールとして*評価しなさい」と伝える必要がある。後述の の例を見ると良いだろう。

### 文字列プロパティ

<div style="color:gray">
String properties are very similar to string lists - they are strings with special formatting, and they contain a collection of items. However, string properties have additional features that make them very useful for storing information in a different way.

</div>
文字列プロパティは、特殊な書式の文字列であることと項目の集まりでできている点で文字列リストによく似ている。それに加えて、文字列プロパティは情報を格納するのにとても有用な機能を備えている。

<div style="color:gray">
The essence of a string property is the the *key - value* pairing. Basically, for each item in the string property, there is a *key* that is paired with a *value*. For instance, if you have a weapon with the following details:

</div>
*キー⇔値*がつがいになっていることが文字列プロパティの特徴である。基本的に、文字列プロパティの各項目は*キー*と対になる*値*を持っている。例えば、次のようなデータを持つ武器があるとして：

-   Weapon Name: Broadsword
-   Weapon Damage Dice: 1d8
-   Weapon Damage Type: Slashing
-   Weapon Category: Versatile

<div style="color:gray">
You have a series of *key - value* pairs: the key “Weapon Name” is paired with the value “Broadsword,” the key “Weapon Damage Dice” is paired with the value “1d8,” and so on. A string property is simply a “formal” way to set up this kind of pairing in a single variable. The string property for the above weapon might read:

</div>
この例では：キー「Weapon Name」は値「Broadsword」とペア、キー「Weapon Damage Dice」は値「1d8」とペア、と行った具合に*キー＝値*のペアが連なっている。文字列プロパティは一つの変数に上記のようなペアを示す「規則的な」書式でなりたつ。上記の武器の文字列プロパティは次のようになる：

> ``` mtmacro
> [h:weapon1 = "name=Broadsword; damageDice=1d8; damageType=Slashing; category=Versatile;"]
> ```

<div style="color:gray">
In that string property, the word to the left of the equal sign is the *key*, and the word to the right is the *value*. The semicolon is the *separator* or *delimiter*. MapTool has special functions to retrieve and change the values within a string property, which you'll see in use later.

</div>
この文字列プロパティでは、「=」の左側の単語が*キー*であり、右側が*値*である。「;」は*セパレーター*または*区切り文字*だ。後ほど説明するが、MapToolは文字列プロパティの値を読み取り、変更する特殊な関数がある。

<div style="color:gray">
Now, let's get to the loops!

</div>
では、繰り返しについて学んで行こう！

COUNT：繰り返して、繰り返して、繰り返して…
------------------------------------------

<div style="color:gray">
The first looping structure we'll cover is the option. This option is the simplest loop - it repeats the operation following the colon a number of times equal to its *argument* (remember, arguments are the values or variables you put inside the parentheses). The format of a (which can also be abbreviated statement is:

</div>
まず最初に取り上げる繰り返しの仕組みはオプションだ。このオプションは、*引数*に等しい回数ぶん、コロンに続く処理を繰り返す、最も単純な繰り返しである（引数は括弧に挟まれた値または変数であることに注意）。（に省略可能）の書式は：

<div style="color:gray">
> ``` mtmacro
> [count(repetitions): command]
> ```

</div>
> ``` mtmacro
> [count(繰り返し回数): コマンド]
> ```

<div style="color:gray">
or

</div>
または、

<div style="color:gray">
> ``` mtmacro
> [c(repetitions): command]
> ```

</div>
> ``` mtmacro
> [c(繰り返し回数): コマンド]
> ```

<div style="color:gray">
The example should be pretty self-explanatory. It contains:

</div>
この例は一目瞭然で説明するまでもないだろう。各要素は：

<div style="color:gray">
-   The option itself - without the option, we wouldn't need this tutorial, right?
-
    this is the value that tells how many times to repeat

-
    this is the actual macro command you want count to do over and over again.

</div>
-   オプションそのもの。もう説明しなくても良いね？

-   ：を何回繰り返すかに指示する値。

-   ：実際に繰り返し実行させたいマクロ・コマンド。

<div style="color:gray">
Let's look at an example. Suppose you have a character who can cast a spell, which creates a cloud of poisonous gas that can hit up to nine targets at the same time. Suppose we also have a cluster of 6 hapless orcs standing in the room, that you are about to poison with this toxic cloud. The rules of your game indicate that you must roll a separate attack for each possible target, meaning that you'd have to roll your attack 6 different times. You can either do that by hand, each time, or you could write a macro that uses to roll the attack over and over, and all you need to give it is the number of times!

</div>
実例を考えてみよう。仮に、君は呪文を使えるキャラクターを持っていて、そのキャラクターが一度に9体の敵に効果のある毒ガス雲を作り出したとしよう。更に、部屋の中には6体の憐れなオークンがいて、君はオーク達に有害な雲を放ち毒殺しようとしている。このゲームのルールでは効果を及ぼしうる対象に対しそれぞれロールを行わなければならないので、6回攻撃それぞれにロールすることになる。すべての攻撃を手動でロールすることもできるが、あらかじめを使って繰り返し攻撃のロールを行うマクロを書いておき、ロールする回数を与えるだけでも構わない！

<div style="color:gray">
Here's how you'd write that macro:

</div>
その時に書くマクロは次のようになるはずだ：

<div style="color:gray">
> ``` mtmacro
> [h:attackBonus = 7]
>
> Toxic Cloud: [count(numAttacks): 1d20+attackBonus]
> ```

</div>
> ``` mtmacro
> [h:attackBonus = 7]
>
> 毒性雲:[count(numAttacks): 1d20+attackBonus]
> ```

<div style="color:gray">
What we did here was:

</div>
ここで書いたものは：

<div style="color:gray">
-   Line 1 sets a value for , to be used later.
-   Line 3 sends the text "Toxic Cloud: " to chat, and then, begins the Count Loop. Since is *undeclared*, MapTool will prompt you for a value before it can start the loop. Once you enter that value, the count loop will process the calculation of that many times, sending the result to chat each time, and separating each result with a comma.

</div>
-   1行目で、後で使うために、に値を代入。
-   3行目で、チャット・ウィンドウに「毒性雲：」のテキストを送り、COUNTの繰り返しを開始する。が*定義されていない*ので、繰り返しの処理を始める前にMapToolが値を催促してくる。値を入力すると、COUNTの繰り返し処理がを何度も計算し、その計算結果をコンマで区切りながらチャット・ウィンドウに出力する。

<div style="color:gray">
The output of this macro will look something like (assuming you entered 4 when prompted for ):

</div>
このマクロの出力は次のようになるはずだ（の値を求められたときに「4」を入力した場合）：

<div style="color:gray">
> Toxic Cloud: 17, 19, 12, 8

</div>
> 毒性雲：17, 19, 12, 8

### 特殊変数：*roll.count*

<div style="color:gray">
Since it's often useful to know what “round” or “turn” we're on when a loop is running, MapTool creates a special variable every time you start a count loop. This variable is called \[\[roll.count|のコマンドを実行し、結果をチャットに表示する。もし、の値が*0より大きくなければ*、繰り返しを中止する。このマクロの出力は次のようになる：

> 9,8,7,6,5,4,3,2,1

<div style="color:gray">
You'll note that “10” was never shown. That's because while the loop may have started with having the value of 10, the first time we *see* any output is when the operation takes place - so the first thing we see is , which is 9.

</div>
「10」が表示されないことに気づくだろう。繰り返し WHILE は は10の値とともに開始して、なんらか出力を最初に見るときは、の処理が行われる場合なので、最初に目にする値は の結果、9になるわけだ。

### 例2：マシンガン

<div style="color:gray">
Let's look at a more complicated (and perhaps more interesting) example. In this example, we won't be using the [Sample Ruleset](Sample_Ruleset "wikilink"), mostly because I couldn't think of a useful example from that game. So, let's assume we have the following game situation:

</div>
では、もっと複雑な（そしてより楽しい）例を考えてみよう。この例では、相応しい実例を思いつけなかったので[サンプルルールセットは使わない](Sample_Ruleset "wikilink")。そこで、次のような状況を想定することにする：

<div style="color:gray">
-   A character has a machine gun with 30 rounds of ammunition
-   They may fire one to six rounds for every action
-   If their attack roll of 1d20 is greater than 15, they may make another attack; otherwise, they must end their turn. They always get at least 1 attack, though.

</div>
-   キャラクターは30発の弾薬を持つマシンガンを装備している
-   このキャラクターはアクションごとに1〜6発、発砲することができる
-   1d20の攻撃ロールが16以上の場合、さらにもう一回攻撃することができる。15以下であれば、ターンを終える。とはいえ常に最低1回の攻撃機会を得る。

<div style="color:gray">
So what we need to do is repeat the operation until *either* the weapon runs out of ammo, or they roll less than a 15 on their attack. Here's how that macro would look:

</div>
武器の弾薬を使い果たすか、ロールの結果が15以下であるまで処理を繰り返すにはどうすれば良いのだろうか。下記のマクロがどのようにしているのか見てみよう：

<div style="color:gray">
> ``` mtmacro
> [h:ammo = 30]
> [h:hit = 1]
>
> [while(ammo > 0 && hit == 1, "<br>"),CODE:
> {
>   [h:attackRoll = 1d20]
>   [h:ammoSpent = 1d6]
>   [h,if(attackRoll > 15): hit = 1; hit = 0]
>   [h:ammo = ammo - ammoSpent]
>   Your first attack expends [r:ammoSpent] rounds, and [if(hit==1, "hits.", "misses.")] You have [r:ammo] rounds remaining.
> }]
>
> [if(hit==0): "Your turn ends because you missed a target."]
> [if(ammo==0): "Your turn ends because you are out of ammo."]
> ```

</div>
> ``` mtmacro
> [h:ammo = 30]
> [h:hit = 1]
>
> [while(ammo > 0 && hit == 1, "<br>"),CODE:
> {
>   [h:attackRoll = 1d20]
>   [h:ammoSpent = 1d6]
>   [h,if(attackRoll > 15): hit = 1; hit = 0]
>   [h:ammo = ammo - ammoSpent]
>   君の攻撃は、[r:ammoSpent]発消費し、[if(hit==1, "命中した。", "失敗した。")] 弾薬は [r:ammo]発残っている。
> }]
>
> [if(hit==0): "攻撃に失敗したので、ターン終了。"]
> [if(ammo==0): "弾薬が無くなったので、ターン終了。"]
> ```

<div style="color:gray">
Here's the breakdown of this macro:

</div>
ではこのマクロを分析してみよう：

<div style="color:gray">
-   Line 1 and 2 set two important variables: and . We set to 30, per the assumptions above, and we set to 1, so that the character always gets at least *one* attack roll (if we didn't set to 1, the loop might stop before it started!).
-   Line 4 is the start of the While Loop: we establish the loop, and give it a combined condition. We say that *while* has a value greater than 30, *and* (remember, two ampersands is the logical operator “and”) *is equal to* 1, the loop should go 'round. If *either or both* of those is *not* true, then the loop should stop. Also, we set the separator to &lt;br&gt;, so that a new line will be printed each time the loop runs.
-   Lines 5 - 9 handle the actual loop processing. Note that in that loop, we make sure to set a new value for and  - this is ***critical***. If you never change the variables that your conditions are based on, then your loop will ***never stop***.

</div>
-   1行目と2行目では、二つの重要な変数：とを設定している。上記の前提の通りには30を設定し、キャラクターは常に*1回の攻撃ロール*を行えるのでには1を設定している（もしに1を設定しなければ、この繰り返しは処理を開始する前に終わってしまう！）。
-   4行目で、WHILEの繰り返しが始まる。繰り返しを作り、組み合わせた条件式を与えている。の値が30より大きく、*そして*（二つのアンパサンド（&&）は論理演算子「AND（≒及び）」のことだ）が*1と等しい*状態である間、この繰り返しは処理を繰り返しつづける。この条件の*片方または両方*が真ではなくなったとき、繰り返しは処理を止める。さらに、繰り返しが実行されるごとに、セパレーターの&lt;br&gt;が新しい行を出力する。
-   5〜9行では、繰り返しの実際の処理がおこなわれる。この繰り返しでは、とに新しい値を代入していることによくよく注意を払うように。これは***危険を伴う***。条件式はこの変数に基づいており、値が変更されなければ、この繰り返しは***止まることなく永遠に***処理をし続ける。

<div style="color:gray">
It's worth repeating: in a while loop, you ***must change the variable that your condition is checking, or you can end up with a loop that never stops***.

</div>
重ねて述べるが、WHILEの繰り返しでは、***条件式を判定する変数を必ず変更しなければならない。さもなくば永遠に止まることなく処理をし続けてしまう***。

<div style="color:gray">
So, the output of this macro will look something like:

</div>
このマクロの出力は次のようになる：

<div style="color:gray">
> Your attack expends 6 rounds, and hits. You have 24 rounds remaining.
> Your attack expends 2 rounds, and hits. You have 22 rounds remaining.
> Your attack expends 3 rounds, and misses. You have 19 rounds remaining. Your turn ends because you missed a target.

</div>
> 君の攻撃は、6発消費し、命中した。弾薬は24発残っている。
> 君の攻撃は、2発消費し、命中した。弾薬は22発残っている。
> 君の攻撃は、3発消費し、失敗した。弾薬は19発残っている。攻撃に失敗したので、ターン終了。

FOR：どう例えれば良いものやら
-----------------------------

<div style="color:gray">
The next loop structure to address is the roll option. This option is somewhat similar to , because it repeats a sequence of code a number of times based on a particular condition; it is also like because that particular condition is “has our counter reached a particular number yet?”

</div>
次に取り組む繰り返しの構造は、 ロール・オプションだ。このオプションは、一連のコードを特定の条件に基づいた回数繰り返すので に少し似ている。また、特定の条件は「カウンターはまだ指定の値に届いているのか？」というものなので に似ているともいえる。

<div style="color:gray">
The general format for a loop is:

</div>
の繰り返しの一般的な書式は次の通り：

> ``` mtmacro
> [for(counter, start, end, stepsize, separator): command]
> ```

> ``` mtmacro
> [for(カウンター, 開始値, 終了値, 増分, 区切り文字): コマンド]
> ```

<div style="color:gray">
Here's how that breaks down:

</div>
ではやり方を分析していこう：

<div style="color:gray">
-   ****: as always, we need to actually put the roll option in there
-   **counter**: this is the variable that will be used to count the iterations through the loop; typically people us a simple 1-letter variable in here, like or . For examples below, we'll use .
-   **start**: this is what the variable starts at (it can be zero, another variable, or any other numeric value)
-   **end**: this is the value that *ends* the loop
    -   In a loop where the variable is *increasing* - in other words, a loop with a positive  - the loop runs as long as is *less than*
    -   In a loop where the variable is *decreasing*- in other words, a loop with a negative  - the loop runs as long as is *greater than*
-   **stepsize**: this is how big the increment is for each iteration of the loop (for example, if you set to 2, then will increase by 2 ever iteration). The default stepsize is +1 (that is, by default, the variable increments by 1 each time the loop is processed).
-   **separator**: like with and , this is an optional separator to show between each output line from the loop; the default is a comma.

</div>
-   ****：いつも通り、ここにロール・オプションをおく必要がある
-   **カウンター**：繰り返しの処理中に反復回数を記録するための変数。一般的に、 や などの単純な1文字の変数を指定することが多い。後述の例では、 を使用している。
-   **開始値**：変数が最初に指定する値（この値は、ゼロや他の変数、あらゆる数値を指定可能）
-   **終了値**：繰り返しが*終了*する値
    -   変数が*増加*していく（が正の値の）場合は、変数がより少ない限り処理を繰り返す。

    -   変数が*減少*していく（が負の値の）場合は、変数がより多い限り処理を繰り返す。

-   **増分**：繰り返しの処理が巡るごとに増加する値（たとえば、を2としたら、繰り返しが続く限り、が2づつ増加する）。標準の増分は＋1である（つまり、標準では変数は繰り返しの処理ごとに1づつ増加していく）。
-   **区切り文字**：やと同じように、繰り返しごとに出力する任意の区切り文字。標準はコンマである。

### 例1：簡単なカウントダウン

<div style="color:gray">
This example illustrates how the option's various components work. As with the previous looping structure, this is a basic countdown:

</div>
この例は、オプションの個々の要素の働きを説明するものだ。前述の繰り返し構造と同じく、ここでも簡単なカウントダウンを用いる：

> ``` mtmacro
> [FOR(i,10,0,-2): "i is now " + i]
> ```

> ``` mtmacro
> [FOR(i,10,0,-2): "i は " + i]
> ```

<div style="color:gray">
In this example, we have specified all components of the loop:

</div>
この例では、繰り返しの全要素を指定している。

<div style="color:gray">
-   The counter variable is .
-   The start value is
-   The end value is
-   The stepsize is (the counter *decrements* by 2 every time the loop processes)

</div>
-   カウンター変数 。
-   開始値
-   終了値
-   増分 （繰り返しの処理を行うごとにカウンターを2づつ*減少させる*）

<div style="color:gray">
The output of this will look like:

</div>
この出力は次のようになる：

> i は 10, i は 8, i は 6, i は 4, i は 2

<div style="color:gray">
You will note that there is no *i is now 0* step - this is because when the counter counts down to 0, is no longer greater than 0.

</div>
この例では *i は 0* の段階には進まないことに注意するように。カウンターが 0 になれば、 はもはや 0 より大きい値ではなくなるからだ。

### 例2：複数行の表を作る

<div style="color:gray">
This example illustrates a practical use of the option to create a table that will be sent to chat, with a number of rows based on how many properties are in a String List.

</div>
この例は、文字列リストの項目数と同じ行数の表を作り、チャットに表示するを使って作る実用的な例だ。

> ``` mtmacro
> [h:theList = "Strength, Endurance, Dexterity, Intelligence"]
>
> [h:numberOfRows = listCount(theList)]
>
> <table border="1">
> [for(i, 0, numberOfRows, 1, ""):  "<tr><td>"+listGet(theList, i)+"</td></tr>"]
> </table>
> ```

<div style="color:gray">
The example above uses a few cool commands to generate the output.

</div>
上記の例では、出力を作成する便利なコマンドをいくつか使用している。

<div style="color:gray">
-   is simply a string list variable containing four elements

-   is a function that, when you put the name of a string list variable in it, will return the number of elements in the string list

-   We create the beginning of an HTML table by using the &lt;table&gt; tag
-   The loop here uses the counter variable , which starts at 0, and counts up until it reaches . It increases by 1 each loop, and the default separator has been changed to so that no extraneous commas are printed to chat.
-   Inside the loop, we [concatenate](Introduction_to_Macro_Writing#String_Concatenation "wikilink") the HTML tags for table rows and table cells around the function . This function will retrieve, from a string list variable, the value of the element that is at the position specified in the second argument. In this case, we say, “get from the variable the value of the element that's in the same position as ” - so that it starts with element 0 (all lists start at item 0 in MapTool) and each time we loop through, it gets the next element.
-   At the end, we close the table with the appropriate HTML tag.

</div>
-   は4つの要素を持つ簡単な文字列リストの変数だ

-   は、文字列リストの変数名を与えると、リストの要素数を返す関数だ。

-   まず、&lt;table&gt;を使ってHTMLテーブルの開始を作成する。
-   の繰り返しのところでカウンター変数のを使用している。この変数は 0 より始まり、に達するまで繰り返しごとに1づつ増えていく。区切り文字は、不必要なコンマをチャットに出力しないように、標準のものからに変更している。

-   繰り返しの中では、テーブルの行とセルのHTMLタグをの周りで[結合している](Introduction_to_Macro_Writing/ja#String_Concatenation "wikilink")。この関数は、文字列リストの変数より、2つ目の引数として与えられた位置にある要素の値を取り出すものだ。今回の例では、「変数の番目にある要素の値を取り出すように」と伝えている。要素はゼロ番目から始まり（MapToolのリストはすべてゼロ番目から始まる）、繰り返しの終わりまで毎回取得するので、次の要素を取得する。
-   最後に、適切なHTMLタグによってテーブルを閉じている。

<div style="color:gray">
The output looks like this. If you add in several more elements to the variable , the table will grow in size to accommodate the new elements.

</div>
この出力は次のようになる。君がにいくつかの要素を追加すれば、表は追加した数だけ行が増えるであろう。

> |              |
> |--------------|
> | Strength     |
> | Endurance    |
> | Dexterity    |
> | Intelligence |
>
FOREACH：特定用途の FOR
-----------------------

<div style="color:gray">
The loop structure lets you repeat a set of commands a specified number of times, with flexible beginning, ending, and steps. That looping method is applicable to many things, and can be looked at as a very “general” way to loop - it gives you lots of flexibility with where you start and end, and can be used for many operations.

</div>
の繰り返しの構造は、一連のコマンドを柔軟な開始値、終了値、増分により指定した回数実行する。この繰り返しの手法は開始値と終了値を決め、多くの式を使うことで、多彩な柔軟性に富んでいる。そのため、多くの場面に応用でき、繰り返しにおける非常に『一般的』な手法と言える。

<div style="color:gray">
However, frequently loops are used to go through a list of items that is already established, and it is kind of a pain to have to make sure to count each list, then assign the variables in a loop, and make sure you can figure out how the variable corresponds to the position of an item in a list. So, a different kind of for loop - one that handles most of that without bothering *you* about it - also exists. This one is called .

</div>
しなしながら、頻繁に使われる繰り返しでは既に作られているリスト内の項目を順番に見ていくものであり、リストの数を調べての繰り返しの変数を定義し、リスト内の項目の位置を示す変数がいくらであるか求めるなければならないのは、ある種の苦痛である。そしため、煩わしい多くの設定を省いたFORの繰り返しの亜種を用意している。これをと呼ぶ。

<div style="color:gray">
In a loop, the looping structure is given two arguments: the name of a string list, and a variable. The variable takes on the value of each element in the list, in turn, as the looping structure iterates. That's a bit confusing, so first, let's look at the general structure of a loop:

</div>
の繰り返し構造には、2つの引数を用いる：文字列リストの名前と一つの変数だ。この変数は繰り返し構造が反復する度に、リストの各要素の値を保持する。少しばかり混乱しやすいので、まずはの繰り返しの一般的な構造を見ていこう：

> ``` mtmacro
> [foreach(item, list): command]
> ```

<div style="color:gray">
-   ****: once again, the roll option itself.
-   **item**: this is the variable that takes on the value of each successive element in the list or property
-   **list**: this is the string list you want the to work on
-   **command**: the operation you want performed on each successive in

</div>
-   ****：おなじみのロールオプション自身である。
-   **item**：リストやプロパティの一連の要素のそれぞれの値を保持する変数。
-   **list**：で処理を行う文字列リスト
-   **command**：内の一連のに対して実行する処理。

<div style="color:gray">
To explain that in plain English: assume for a moment that there you have the names of several targets (NPC tokens) that your character wants to attack at the same time. You need to make an attack roll against each target, which is equal to 1d20 + 7, but you have to roll separately for *each* target.

</div>
説明のためわかりやすくしてみよう。君のキャラクターが同時に攻撃しようとしている複数の名前のある対象（NPCトークン）があるとしよう。君は各対象に攻撃ロール（1d20＋7）を行う必要があるが、*個々の対象*に別々にロールしなければならない。

<div style="color:gray">
You could write out the attacks each time like this:

</div>
この行為は次のように書き出すことができる。

<div style="color:gray">
``` mtmacro
I attack target 1: [1d20+7]<br>
I attack target 2: [1d20+7]<br>
I attack target 3: [1d20+7]<br>
I attack target 4: [1d20+7]<br>
```

</div>
``` mtmacro
対象 1 への攻撃： [1d20+7]<br>
対象 2 への攻撃： [1d20+7]<br>
対象 3 への攻撃： [1d20+7]<br>
対象 4 への攻撃： [1d20+7]<br>
```

<div style="color:gray">
And so forth and so on. Not so bad if you have 3 targets. But what if you have 6? Or 12?

</div>
その他、色々な書き方があるだろ。相手が3体なら悪くないが、6体ならどうか？12体なら？

<div style="color:gray">
So instead, what if you created a single variable that was a list of the names of each target? Then, you can use the loop to go through the list one by one and let you make the roll with a very efficient little bit of code. may be a little hard to explain, but once you understand what it can do, you will see how useful it can be!

</div>
その代わりとして、各対象の名称のリストの変数を作るとしたらどうだろうか？ リストの一つ一つを取り出しながら一か所のコードで効率的にロールを行うために、の繰り返しを使うことができる。は少しばかり説明が難しいが、何ができるかを理解すれば、いかに便利か解るだろう!

<div style="color:gray">
Now, let's jump to some examples.

</div>
では、例を見てみよう。

### 例1：文字列リストの内容を並べる

<div style="color:gray">
This simple example will go through a string list, and list the value of each element in the list, from beginning to end.

</div>
この単純な例では文字列リストを通して、リストの初めから終わりまでのそれぞれの要素の値を取り出して一覧していく。

> ``` mtmacro
> [h:theList = "18, Bob, 29, Foo, 1009, Snorkel"]
>
> [foreach(item, theList, "<br>"): item]
> ```

<div style="color:gray">
In the above macro, we've created a loop that takes the list variable , and goes to each element in that list, and assigns the value of that element to the variable . We've set the separator to the HTML code for a line break, and then -- after the colon -- instructed the macro to print the value of the variable to the chat window.

</div>
上記のマクロでは、リストの変数 を扱う を作り、リスト内の各要素を取り出し、その要素の値を変数 に割り当てている。改行を表す HTML コードをセパレーターとして設定し、コロンに続けて変数 の値をチャットウィンドウに出力するマクロ指定している。

<div style="color:gray">
The output of that macro looks like:

</div>
このマクロを出力は次のようになる。

> 18
> Bob
> 29
> Foo
> 1009
> Snorkel

<div style="color:gray">
Do you see what happened there? The foreach() option went to each element in , said, “the variable is now equal to the element,” and then printed the value of to chat.

</div>
なにが起きているの解っただろうか？ この foreach() オプションは の各要素を取り出して「変数 はこの要素と同じである」と宣言し、 の値をチャットウィンドウに出力している。

### 例2：群がるゴロツキどもを打ちのめす

<div style="color:gray">
Now, let's look at the example described in the beginning. Remember how we had those target names to attack? Here's how we'd do that:

</div>
では最初にこの例を見てみよう。攻撃する対象の名前を持つ方法をどうするか覚えいるだろうか？次の通りだ。

<div style="color:gray">
> ``` mtmacro
> [h:targetList = "Orc 1, Goblin 2, Orc 4, Zombie 17, Big Boss"]
>
> [foreach(target, targetList, "<br>"),CODE:
> {
>    [h:attackRoll = 1d20+7]
>    I attack [r:target] with an attack roll of [r:attackRoll]
> }]
> ```

</div>
> ``` mtmacro
> [h:targetList = "オーク 1, ゴブリン 2, オーク 4, ゾンビ 17, 親玉"]
>
> [foreach(target, targetList, "<br>"),CODE:
> {
>    [h:attackRoll = 1d20+7]
>    [r:target] に攻撃し、攻撃ロールは [r:attackRoll] 。
> }]
> ```

<div style="color:gray">
-   The first line simply sets up the variable , as discussed.
-   The foreach loop goes through each element in , assigning its value to the variable . So, the first time through, has the value of the first item in  - in other words, is equal to . The second time through, equals the *second* item in the list, and so on.
-   The roll option is used so we can execute multiple commands (and because it sometimes makes formatting the output a little easier)
-   Inside the CODE brackets, we calculate a variable called . This is recalculated on every loop, so it's different for each .
-   Finally, we generate some chat output, inserting the variable and the variable in the appropriate places.

</div>
-   前述の通り、最初の行は変数 を定義している。
-   foreach の繰り返しを使い の各要素を取り出し、その値を変数 に割り当てている。最初の繰り返しでは は の最初の値（つまり は となる）を持っている。繰り返しの*2回目*では はリストの2番目の値となり、以降順々に繰り返されていく。
-   複数のコマンドを実行するためにロールオプション を使用している（出力の書式を簡単にするために使うこともある）。
-   CODE の確固の中で、と名付けた変数を計算している。この変数は繰り返しごとに再々計算されるので、それぞれの ごとに異なる結果となる。
-   最後に、変数 と の値を埋め込みチャットへの出力を生成している。

<div style="color:gray">
The output of that macro, when sent to chat, looks like:

</div>
このマクロの出力がチャットウィンドウに送るものは次の通り。

<div style="color:gray">
> I attack Orc 1 with an attack roll of 12
> I attack Goblin 2 with an attack roll of 11
> I attack Orc 4 with an attack roll of 21
> I attack Zombie 17 with an attack roll of 17
> I attack Big Boss with an attack roll of 9

</div>
> オーク 1 に攻撃し、攻撃ロールは 12
> ゴブリン 2 に攻撃し、攻撃ロールは 11
> オーク 4 に攻撃し、攻撃ロールは 21
> ゾンビ 17 に攻撃し、攻撃ロールは 17
> 親玉 に攻撃し、攻撃ロールは 9

最後に
------

<div style="color:gray">
That about covers the looping basics for MapTool macros. The examples shown above are very simple, of course - just enough to show you how these work. But looping is *incredibly* useful for many applications in a MapTool macro, from generating multiple die rolls to building tables to editing token properties, so make sure to experiment with it.

</div>
ここでは、MapTool マクロにおける基本的な繰り返し処理を学んできた。上記の例は非常に単純なものである（もちろん例示する作業には純分なものだ）。しかし、繰り返し処理は MapTool マクロを、複数のダイスロールの生成から、テーブルの構築、トークンのプロパティの編集などに応用するうえで*非常に*に有用なものでありので、ぜひこの機能を試してもらいたい。

<Category:MapTool> <Category:Tutorial> <Category:MapTool> <Category:Tutorial>