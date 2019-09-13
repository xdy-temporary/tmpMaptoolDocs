MapTool's chat window and macro system supports several of the most
common dice expressions based on the formats **XdY** and **dY**.

Maptoolのチャット・ウィンドウとマクロ・システムは、 **XdY** と **dY**
を基本的な形式とする、いくつかの一般的なダイスの記法をサポートしている。

In the tables below, the variable *Y* is described as the "number of
sides" on the dice being rolled; in reality the dice roller is picking a
random number between 1 and *Y*. The end result is the same.

以下のテーブルにおけるさまざまな*Y*は、振るダイスの「面の数」を表している。実際には、ダイスローラーは1から*Y*までの乱数を取り出す。結果の出力については同じである。

Additionally, in the expressions, capital letters signify an argument
you must provide, while the lower-case letters are a fixed part of the
dice expression. For example, in the expression **XdYsS**, you replace
*X*, *Y*, and *T* with numbers to indicate the number of dice, how many
sides the dice have, and what number indicates a success, respectively.
The lower case "d" and "s" are left alone.

（加えて～以下未訳）

Finally, note that when entering a dice roll directly in chat, you need
to use the /roll [Chat Command](Chat:Commands "wikilink") to execute the
roll. In a macro, you would enclose the roll expression in square
brackets. For example, if you wanted to roll one twenty sided die, one
six sided die, and add 8 to the result:

　最後に、チャットで直接ダイスを振りたいときは、実行するための[チャット・コマンド](Chat:Commands/ja "wikilink")「/roll」を使う必要がある
。マクロでは、大カッコ \[\]
でダイスの記法で書かれたものを囲むとよい。たとえば、君が1個の20面体ダイスと1個の6面体ダイスを振り、その結果に8を加える場合、次のように書く：

*Directly in chat*:

    /roll 1d20+1d6+8

*チャットに直接書き込む場合*:

    /roll 1d20+1d6+8

'' [マクロで書く場合](Macros:introduction/jp "wikilink")'':

    [1d20+1d6+8]

You may also access these dice expressions directly using macro
functions, see [:Category:Dice
Function](:Category:Dice_Function "wikilink").

　マクロ機能を使うことで、これらのダイスの記法〔それ自体〕に対してもアクセスすることができる[:Category:Dice
Function](:Category:Dice_Function "wikilink")。

## 一般的なダイスの記法

| 記法         | 機能                | 解説                                                                                                                                     | 用例                                                                                                                                                  |
| ---------- | ----------------- | -------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| **XdY**    |                   | *Y* 面体のサイコロを *X* 個ぶん振って（もし X が含まれていない場合は、 1個の *Y* 面体を振るものと見なす）、出目のすべてを足し合わせた数字をチャットに表示する〔註：個々の出目は表示してくれない〕。                            | */roll 1d20* は1個の20面体を振り、出た結果をチャットに表示する。                                                                                                            |
| **XdYdN**  | drop              | *Y*面体のサイコロを*X*個ぶん振り、出目の低い順に*N*個ぶんのさいころを捨てる。                                                                                            | */roll 4d6d1*は4個の6面体を振り、一番低い出目のサイコロを捨て、残ったサイコロの合計をチャットに表示する。                                                                                        |
| **XdYkN**  | keep              | Roll *X* dice with *Y* sides each, and keep the highest *N* dice afterwards                                                            | */roll 4d6k3* rolls four six-sided dice, keeps the highest 3 rolls, and presents the total in the chat window                                       |
| **XdYrL**  | reroll            | Roll *X* dice with *Y* sides each, rerolling any results lower than *L*                                                                | */roll 3d8r2* rolls three eight-sided dice, rerolls any dice that are lower than 2, and then sums and presents the total in chat                    |
| **XdYsT**  | success           | Roll *X* dice with *Y* sides each, and count any rolls that meet or exceed *T* (the "target number")                                   | */roll 4d6s4* rolls four six-sided dice, and counts any individual roll that exceeds four, presenting the number of "successes" in chat             |
| **XdYe**   | explode           | Roll *X* dice with *Y* sides each, and reroll any dice that roll *Y*, add the new roll to the total                                    | */roll 2d6e* rolls two six-sided dice, and if either rolls a 6, it is rerolled and added to the total (this continues until neither die rolls a 6). |
| **XdYesT** | exploding success | As success rolls, above, but the individual dice can "explode" (*i.e.*, they are rerolled if they roll their maximum value)            | */roll 4d6es8* will roll 4 six-sided dice, explode any that roll their maximum, and then total the rolls that exceed 8                              |
| **XdYo**   | open              | Roll *X* dice with *Y* sides each, and explode any dice that roll *Y*, then return the value of all rolls, as well as the highest roll | */roll 5d6o* rolls 5 six-sided dice, and explodes any that roll 6                                                                                   |

## 個別のゲーム向けの記法

| Expression  | Game System       | Function                         | Description                                                                                                                                                                                                                                                                                                                              |
| ----------- | ----------------- | -------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **XdYh**    | Hero              | Stun Dice                        | Rolls *X* dice with *Y* sides each, keeping track of the results for hero rolls for body damage. Where a roll of 1 = 0 body damage, a roll of *Y* = 2 body damage and a roll in between these two values = 1 body damage.                                                                                                                |
| **XdYb**    | Hero              | Body Dice                        | Returns the body damage from the last XdYb Hero Stun Dice roll as long as *X* and *Y* matches the Stun Dice roll                                                                                                                                                                                                                         |
| **Xdf**     | Fudge             | Fudge Dice                       | Rolls *X* [Fudge](http://www.fudgerpg.com/fudge.html) dice (which return -1, 0, or 1), summing the dice and returning the sum                                                                                                                                                                                                            |
| **Xdu**     | Ubiquity          | Ubiquity Dice                    | Rolls *X* Ubiquity dice, which return 0 or 1, summing the result and returning that value to chat                                                                                                                                                                                                                                        |
| **Xsr4**    | Shadowrun 4th Ed. | Shadowrun Basic Roll             | Roll *X* number of 6 sided dice. Output the number of Hits (Rolls 5 or above) and the numbers of Ones rolled. If the number of Ones is half or more of *X*, display **Glitch**. If the number of Ones is half or more of *X* and there are no Hits, display **Critical Glitch**.                                                         |
| **Xsr4gT**  | Shadowrun 4th Ed. | Shadowrun Gremlin Roll           | Roll *X* number of 6 sided dice. Output the number of Hits (Rolls 5 or above) and the numbers of Ones rolled. If the number of Ones is half or more of *X* minus *T*, display **Glitch**. If the number of Ones is half or more of *X* minus *Y* and there are no Hits, display **Critical Glitch**.                                     |
| **Xsr4e**   | Shadowrun 4th Ed. | Shadowrun Exploding Roll         | Roll *X* number of 6 sided dice. Output the number of Hits (Rolls 5 or above) and the numbers of Ones rolled. Reroll any 6 adding it to the pool. If the number of Ones is half or more of *X*, display **Glitch**. If the number of Ones is half or more of *X* and there are no Hits, display **Critical Glitch**.                     |
| **Xsr4egT** | Shadowrun 4th Ed. | Shadowrun Exploding Gremlin Roll | Roll *X* number of 6 sided dice. Output the number of Hits (Rolls 5 or above) and the numbers of Ones rolled. Reroll any 6 adding it to the pool. If the number of Ones is half or more of *X* minus *T*, display **Glitch**. If the number of Ones is half or more of *X* minus *T* and there are no Hits, display **Critical Glitch**. |

{{\#customtitle:ダイスの記法}}

[Category:MapTool](Category:MapTool "wikilink")