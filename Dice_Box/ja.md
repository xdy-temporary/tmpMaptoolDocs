## ダイスボックス

<div style="color:gray">

*Dice Box* is a collection of MapTool macros that provide a visual, user
friendly interface for making basic dice rolls. MapTool has an extensive
set of chat commands that let users roll dice in the main chat window
(dice commands that look like **/roll 1d20+9**). The Dice Box scripts
add a visual, easy-to-understand window for rolling dice and sending the
results to the chat window.

</div>

*ダイスボックス*とは、見やすく分かりやすいインターフェイスで基本的なダイス振りを行うための、MapToolのマクロ群のことだ。MapToolには多種多様なチャットコマンドが用意されており、メイン・チャット・ウィンドウ上でこれを使ってダイスを振ることができる（コマンドは**/roll
1d20+9**のような形式だ）。ダイスボックスのスクリプトでは、ビジュアルで分かりやすいウインドウを使ってダイスを振り、その結果をチャット・ウィンドウに送り込む。

<div style="color:gray">

The instructions below assume you are familiar with how to start MapTool
and how to navigate around MapTool. If you aren't, please check out the
[Introduction to Mapping](Introduction_to_Mapping "wikilink") for a
quick guide to getting started with MapTool.

</div>

下記の解説では、MapToolの立ち上げや使い方について理解できていることを前提としている。もしそうでないな ら、[Introduction
to
Mappingのページを見て](Introduction_to_Mapping "wikilink")、MapToolを始めるためのガイドを読んで欲しい。

### 使用環境

<div style="color:gray">

1.  MapTool **1.3.b66** or later. It may work on previous versions, but
    is untested.
2.  A Java [stack size](Stack_Size "wikilink") higher than 512KB.

</div>

1.  MapTool **1.3.b66** 以降。それ以前のバージョンでも使えるかも知れないが、テストはしていない。
2.  Java [stack size](Stack_Size "wikilink") が512KB以上

### ダイスボックス・トークンを取得する

<div style="color:gray">

1.  Download Dice Box from [my
    website](http://www.houseofgenius.com/files/mtfw/dicebox/diceBox_v31.rptok).
    The latest version is **3.1**. You should receive a file called
    **diceBox_v31.rptok**
2.  Download the [table of colorful dice
    images](http://www.houseofgenius.com/files/mtfw/dicebox/colordice.mttable).
    This contains the images and is required for Dice Box to function.
    You should get a file named **colordice.mttable**. If it is renamed
    to colordice.zip, make sure to change the extension to "mttable".

</div>

1.  ダイスボックスを[my
    website](http://www.houseofgenius.com/files/mtfw/dicebox/dicebox_v31.rptok)からダウンロードする。最新バージョンは**3.1**だ。ダウンロードされるファイル名は**dicebox_v31.rptok**である。
2.  [table of colorful dice
    images](http://www.houseofgenius.com/files/mtfw/dicebox/colordice.mttable)　をダウンロードする。この中にはダイスボックスで使用される画像が含まれており、必須のファイルである。ダウンロードされるファイル名は**colordice.mttable**だ。もしcolordice.zipという名前になっているようなら、かならず拡張子を"mttable"に変更して欲しい。

<div style="color:gray">

**Tip**: Files with an **.rptok** extension are MapTool's format for
saving tokens and all of the macros and information they may contain.
Files with a **.mttable** extension are MapTool's format for tables
within the system.

</div>

**Tip**:
拡張子が**.rptok**となっているのは、MapToolがトークンやその内部に持っているマクロをセーブするためのフォーマットを持つファイルだ。**.mttable**はシステム内のテーブルを収めるためのフォーマットを持っている。

### ダイスボックスの「インストール」

![Db27_dragtomap.png](Db27_dragtomap.png "Db27_dragtomap.png")

![Diceboxconfig.png](Diceboxconfig.png "Diceboxconfig.png")

![Dicebox_vistoplayers.png](Dicebox_vistoplayers.png
"Dicebox_vistoplayers.png")

![Dicebox27.png](Dicebox27.png "Dicebox27.png")

<div style="color:gray">

Though this section is called "Installing Dice Box," bear in mind that
we're not actually *installing* anything - you won't need to run any
programs besides MapTool, and your MapTool files will not be changed.
However, for simplicity's sake, I used the term "installing." Anyway,
here's how to get the Dice Box on your system:

</div>

この章は「ダイスボックスの『インストール』」と書かれているが、実際には何も「インストール」していない。実行するプログラムはMapToolだけで、MapTool上のファイルも一切変更されていない。ただ、話を分かりやすくするために「インストール」という言葉を使っただけだ。ともかく、あなたのシステムにダイスボックスを載せるための手順は以下の通りだ：

<div style="color:gray">

1.  Open MapTool.
2.  Drag the file **dicebox_v31.rptok** from wherever you downloaded
    it, onto the MapTool map. You should see a token called **Lib:Play**
    appear on the map. **Tip**: if you are familiar with MapTool's
    Resource Library, you can save your token there, too, and drag it
    from your Resource Library onto the map. Also, once you put the
    token on one map, *don't put it on any others* - the way Library
    Tokens work, they can only be on ***one*** map. So once you've put
    it on one map, that's all you need to do.
3.  Double-click on the token to get the **Edit Token** window.
4.  Go to the **Ownership** tab and make sure *nothing* is checked.
5.  Go to the **Config** tab and make sure **Visible to Players** is
    checked.
6.  Click **OK** to close the Edit Token window.
7.  Go to **Window \> Tables**
8.  Click the "Import" button.
9.  Navigate to where you saved the file **colordice.mttable** and
    select it. Click "Open." A new table called "NewDice" will appear in
    the Tables window.
10. Go to **File \> Save Campaign As** and save your work so far as a
    Campaign File, giving it whatever name you like (such as
    "Basic.cmpgn").
11. Select the Dice Box token, and in the selection window (if you don't
    see that window, go to **Window \> Selection**) and click the button
    labeled **onCampaignLoad**. The Dice Box frame will pop up\!

</div>

1.  MapToolを開く
2.  　**dicebox_v28.rptok**をダウンロードした場所からドラッグして、MapToolの地図上に持ってくる。地図上には**Lib:Play**というトークンが表示されるはずだ。
    **Tip**:
    もしあなたがMapToolのリソース・ライブラリについて詳しいのなら、ここでトークンをセーブして、リソース・ライブラリからマップ上にドラッグしてもいい。また、一度マップ上にこのトークンを置いたら、*他の場所には置かないこと。*ライブラリ・トークンの仕組み上、***一つの地図上でしか***動作できない。そのため、トークンを地図上に置いたら、それでやることは終わりだ。
3.  このトークンをダブルクリックし、**Edit Token**ウィンドウに出す
4.  **Ownership**タブを選んで、*何も変更されていない*ことを確認する
5.  **Config**タブを選んで、**Visible to Players**がチェックされていることを確認する
6.  **Ok**をクリックして、**Edit Token**ウィンドウを閉じる
7.  **Window \> Tables**を開く
8.  "Import"ボタンをクリックする
9.  先ほど**colordice.mttable**をセーブしておいた場所を開き、そのファイルを選択して、"Open"をクリックする。するとTablesウィンドウに"NewDice"という名前の新しいテーブルが表示される。
10. **File \> Save Campaign
    As**を選んで、この作業をとりあえずキャンペーン・ファイルとしてセーブしておく。名前は好きに決めていい（"Basic.cmpgn"とか）。
11. ダイスボックスのトークンを選択し、その選択ウィンドウ（もしこのウィンドウが表示されていなければ、**Window \>
    Selection**を行ってください）の中から **onCampaignLoad**
    という名前のボタンをクリックする。すると、ダイスボックスのフレームが表示されるはずだ。

### ダイスボックスの使い方

![Dicebox-output.jpg](Dicebox-output.jpg "Dicebox-output.jpg")

ダイスボックスの使い方は簡単だ:

<div style="color:gray">

1\. Click on the pictures of the dice you need to roll. Each time you
click, you'll add one more die of that type to the roll. The total for
each kind of die is shown below or beside the corresponding image.

</div>

1\. 振りたいダイスの画像をクリックする。１回クリックするごとにそのダイスの個数が１つ増える。ダイスの総数はその画像の傍に表示されている。

<div style="color:gray">

2\. Add any fixed amount in the last box (for instance, if you want to
add 7 to the total dice roll, put a 7 in the last box).

</div>

2\. 最後のボックスの中に固定値を入れる（例えば、出目の合計値に7を足したければ、このボックスに7を入れる）。

<div style="color:gray">

3\. Click on the **Show Results To:** link to switch between making the
results visible to everyone, or visible only to the GM and yourself.
Click on "Results" to change between a "tooltip" that shows only the
*total* of each group of dice, or shows the total *and* the results of
each individual die.

</div>

3\. **Show Results
To:**のリンクをクリックして、結果を全員またはＧＭと自分だけに公開するよう設定する。"Results"をクリックして、"tooltip"の中身を、それぞれのダイス種類ごとの*total*とするか、totalとそれぞれのダイスの出目の*両方*とするかを選ぶ。

<div style="color:gray">

4\. Once you've selected the dice you want to roll, click **Roll**. The
result of the roll will appear in the chat window, as shown below:

</div>

4\. 振るダイスを決めたら**Roll**をクリックする。振った結果はチャット・ウィンドウに以下のように表示される：

<div style="color:gray">

5\. If you make a mistake, you can hit "Clear All" to clear out the dice
you've selected, and start over.

</div>

5\. もし間違えたら、"Clear All"をクリックして、選んだダイスを全てクリアし、またやり直す。

<div style="color:gray">

If you need to adjust the layout of the Dice Box (to fit your MapTool
window better) click "Change Layout," and pick from one of the options.

</div>

（MapToolと組み合わせ易いように）ダイスボックスの中のレイアウトを変更したければ、"Change
Layout"をクリックし、オプションの中から選択する。

{{\#customtitle:ダイスボックス|ダイスボックス}}

[Category:Cookbook](Category:Cookbook "wikilink")