__TOC__ 　Maptoolのチャットシステムでは、チャットに直接入力することで特定のアクションを実行することができるような、多くの「スラッシュ・コマンド」（slash commands）をサポートしている。この〔スラッシュという〕名前は、コマンドの直前に“/”を打ち込むことに由来している。

一般的な使い方
--------------

　チャット・コマンドを使うときは、チャット画面に直接、以下のようなフォーマットで入力するとよい：

``` mtmacro
/command argument
```

　*command*のところには、〔このページの〕下の一覧表にあるコマンドのうち一つを入力する。そして*argument*の部分には、コマンドの動作に適した引数が入る（ダイスを振る場合、テキストを入力する場合、などなど……）。

**`重要なこと`**`: すべてのコマンドの直前にスラッシュ（`**`/`**`） の文字列が入ることを忘れないように。`

コマンド一覧
------------

<table>
<thead>
<tr class="header">
<th><p>コマンド</p></th>
<th><p>組込み済の略語<br />
（あれば）</p></th>
<th><p>コマンドの説明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>addtokenstate</p></td>
<td><p>tsa</p></td>
<td><p>トークンに対して新たなトークン・ステータスを追加する。</p></td>
</tr>
<tr class="even">
<td><p>alias</p></td>
<td><p>alias</p></td>
<td><p>コマンドの略語（＝エイリアス）を作成する。</p></td>
</tr>
<tr class="odd">
<td><p>clear</p></td>
<td><p>clr</p></td>
<td><p>チャット画面をクリアする。</p></td>
</tr>
<tr class="even">
<td><p>clearaliases</p></td>
<td></td>
<td><p>すべてのコマンド略語〔の設定〕をクリアする。</p></td>
</tr>
<tr class="odd">
<td><p>color</p></td>
<td><p>cc</p></td>
<td><p>チャットの文字色を変更する。色の指定は16進数形式でなければならない。例：<em>/cc #ff0099</em></p></td>
</tr>
<tr class="even">
<td><p>emit</p></td>
<td><p>e</p></td>
<td><p>接続中のすべてのプレイヤーに対して、送信したという事実を隠したままテキストを送信する（GM専用コマンド）。</p></td>
</tr>
<tr class="odd">
<td><p>emote</p></td>
<td><p>me</p></td>
<td><p>emoteを接続された全てのプレイヤーに送信する。（original： Broadcast an emote to all connected players.)</p></td>
</tr>
<tr class="even">
<td><p>gm</p></td>
<td><p>togm</p></td>
<td><p>GMだけにテキストを送信する。</p></td>
</tr>
<tr class="odd">
<td><p>goto</p></td>
<td><p>g</p></td>
<td><p>特定のロケーションあるいは特定のトークンに〔視点を〕移す。例：<em>/goto X,Y</em> or <em>/goto tokenname</em></p></td>
</tr>
<tr class="even">
<td><p>help</p></td>
<td><p>h</p></td>
<td><p>使用可能なコマンド一覧を表示する。</p></td>
</tr>
<tr class="odd">
<td><p>impersonate</p></td>
<td><p>im</p></td>
<td><p>まるで誰か、あるいは何かであるかのように話す（ふつう、トークンに対して使う）</p></td>
</tr>
<tr class="even">
<td><p>loadaliases</p></td>
<td></td>
<td><p>略語が盛り込まれたファイルを読み出す。略語は、一行ごとに書かれた特定の名前と値が（あなた自身が入力したそのままで）読み出される。（original: Load a file that contains aliases, one per line, with a : between the name and the value (just as if you were typing it in.）</p></td>
</tr>
<tr class="odd">
<td><p>loadtokenstates</p></td>
<td><p>tsl</p></td>
<td><p>全てのトークン・ステータスをファイルから読み出す。</p></td>
</tr>
<tr class="even">
<td><p>ooc</p></td>
<td></td>
<td><p>プレイヤー発言（＝アウトオブキャラクター）として喋る。この発言は二重丸カッコ（（～～））で閉じられる。</p></td>
</tr>
<tr class="odd">
<td><p>reply</p></td>
<td><p>rep</p></td>
<td><p>最後にあなたに囁いたプレイヤーに対して返信する。</p></td>
</tr>
<tr class="even">
<td><p>roll</p></td>
<td><p>r</p></td>
<td><p>ダイスを振り(<a href="Dice_Expressions/ja" title="wikilink">ダイスの記法（日本語ページ：翻訳未了）を参照せよ</a>)、結果を全てのプレイヤーに見せる。</p></td>
</tr>
<tr class="odd">
<td><p>rollgm</p></td>
<td><p>rgm</p></td>
<td><p>ダイスを振り、結果を自分自身とGM〔の二人〕だけに見せる。</p></td>
</tr>
<tr class="even">
<td><p>rollme</p></td>
<td><p>rme</p></td>
<td><p>ダイスを振り、結果を自分自身にだけ見せる。</p></td>
</tr>
<tr class="odd">
<td><p>rollsecret</p></td>
<td><p>rsec</p></td>
<td><p>ダイスを振り、結果をGMにだけ見せる（〔出目の〕結果は振った本人でさえ見えない）。</p></td>
</tr>
<tr class="even">
<td><p>savealiases</p></td>
<td></td>
<td><p>現在のすべてのコマンド略語をファイルに保存する。</p></td>
</tr>
<tr class="odd">
<td><p>savetokenstates</p></td>
<td><p>tss</p></td>
<td><p>現在のトークン・ステータスをファイルに保存する。</p></td>
</tr>
<tr class="even">
<td><p>say</p></td>
<td><p>s</p></td>
<td><p>接続している全てのプレイヤーにメッセージを送信する。</p></td>
</tr>
<tr class="odd">
<td><p>self</p></td>
<td></td>
<td><p>自分自身にだけメッセージを送信する。</p></td>
</tr>
<tr class="even">
<td><p>settokenproperty</p></td>
<td><p>stp</p></td>
<td><p><a href="Token_Property/ja" title="wikilink">トークン・プロパティ（日本語ページ：翻訳未了）の値を設定する</a>。</p></td>
</tr>
<tr class="odd">
<td><p>settokenstate</p></td>
<td><p>sts</p></td>
<td><p><a href="Token_State/ja" title="wikilink">トークン・ステータス（日本語ページ：翻訳未了）の値を設定する</a>。</p></td>
</tr>
<tr class="even">
<td><p>table</p></td>
<td><p>tbl</p></td>
<td><p>テーブル・ルックアップを実行する。例：<em>/tbl tablename value-to-lookup</em></p></td>
</tr>
<tr class="odd">
<td><p>tmacro</p></td>
<td><p>tm</p></td>
<td><p>選択したトークンに対して任意のマクロを実行する。</p></td>
</tr>
<tr class="even">
<td><p>tsay</p></td>
<td><p>ts</p></td>
<td><p>選択したトークンに対して任意の発話を実行する。</p></td>
</tr>
<tr class="odd">
<td><p>whisper</p></td>
<td><p>w</p></td>
<td><p>特定のプレイヤーにメッセージを送信する。</p></td>
</tr>
</tbody>
</table>

{{\#customtitle:チャット・コマンド|チャット・コマンド}}

<Category:MapTool>