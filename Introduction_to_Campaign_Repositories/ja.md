{{\#customtitle:はじめてのキャンペーン・リポジトリー|キャンペーン・リポジトリー}}

## リポジトリーとは

<div style="color:gray;">

A campaign repository is a set of files (mostly images) that are used in
a campaign. By hosting a repository someplace other than the GM's
computer you can help speed up the image download time of your players,
making the game run smoother in general.

</div>

キャンペーン・リポジトリーは、キャンペーンで使用するファイル（主に画像）を集めたものだ。リポジトリーをGMのコンピューター以外の場所に設置することで、プレイヤーが画像をダウンロードする速度を速めることができ、円滑なゲーム進行の一助となる。

<div style="color:gray;">

You must have some externally hosted web space to properly use a
repository. Many ISPs give you some space you can use for this type of
purpose. If your ISP does not provide this you can usually find cheap
(and even free, in some cases) web hosting if you search around.

</div>

そのためにリポジトリーを設置可能なウェブ上のディスク領域が必要だ。多くの接続プロバイダーはリポジトリーを問題なく設置できる領域を提供している。契約しているプロバイダーが領域を提供していない場合、安価な（または無料の）レンタルサーバーを探せば良いだろう。

<div style="color:gray;">

Unless you are running MapTool from a really beefy server-class machine
on a T1 connection (or you picked a really bad web server) you're almost
guaranteed that clients will be able to download files from any hosted
web storage faster than they will from your machine. This is one of the
main benefits of a repository.

</div>

光ファイバー接続されたサーバー並みのマッチョなマシンで MapTool
を稼働させていない限り（もくは粗悪なレンタルサーバーを使用していない限り）、参加者のダウンロード速度は、君のパソコンからダウンロードするよりWeb上にホストしたサーバーからダウンロードする方が速いことは十中八九間違いない。このことはリポジトリーの主要な利点の一つだ。

## リポジトリーの作成

<div style="color:gray">

To create a repository file, open your campaign in MapTool and go to
File -\> Export -\> Campaign Repository File. This will create a zip
file that contains the repository information.

</div>

リポジトリー・ファイルを作るには、MapTool でキャンペーンを開き、「ファイル→書き出し→キャンペーン・リポジトリー」を選択する。

<div style="color:gray">

Unzip the file. (This is very important\! MapTool cannot use the
repository if it remains zipped\!) Inside should be a folder called
"assets" and a file called index.gz. Upload both the assets folder and
the index.gz file to your web storage. Make sure they are in the same
directory. (Do not put the index.gz file *inside* the assets folder. It
should be at the same level as the assets folder.)

</div>

ZIPファイルを展開する（非常に重要なことなので忘れないように\!\! MapTool
はZIP圧縮されたリポジトリーを使用不可能）。展開した中には「assets」フォルダーと「index.gz」ファイルがある。このふたつをウェブ上のサーバーへアップロードする。二つとも必ず同じディレクトリーにアップするように（「index.gz」を「assets」の中に**入れてはいけない**。「index.gz」は「assets」フォルダーと同じレベルに置くように）。

<div style="color:gray">

Make a note of the URL for to your index.gz file. You can test the URL
by typing it or copying and pasting it into your browser's address bar.
If you have the address right you should see a page full of letters and
numbers that won't mean much to you.

</div>

作成した index.gz
ファイルのURLを記憶する。ブラウザのアドレスバーにURLを貼付けてテストすることができる。アドレスが正しければ解読不可能な英数字の羅列するページが表示されるだろう。

<div style="color:gray">

In MapTool, go to Edit -\> Campaign Properties then go to the
Repositories tab. Delete any links that are already there, then add the
URL of your index.gz file.

</div>

MapTool に戻り、「編集→キャンペーン・プロパティ」を開き、「リポジトリー」のタブを選択。既にあるリンクを全て削除し、先ほどの
index.gz へのURLを追加する。

<div style="color:gray">

Save your campaign. Now when clients connect to your server they will
get the campaign files from the repository online instead of your PC.

</div>

キャンペーンを保存する。以上で、君のサーバーに接続する参加者はキャンペーンのファイルを君のパソコンからではなく、リポジトリーから取得するようになった。

<div style="color:gray">

If you make changes to your campaign file you will need to re-export the
campaign repository file and re-upload it to your web space. You will
not need to re-add the URL to the Repositories tab of the Campaign
Properties unless you changed the location where your files are being
kept.

</div>

その後、キャンペーン・ファイルを変更するのであれば、再度エクスポートして、もう一度Webサーバーにアップロードする必要がある。再アッブしても、キャンペーン・プロパティのリポジトリー・タブのURLは変更しなくて構わない。もちろんアップロード先を変えた場合は変更先のURLを追加しなければならない。

[Category:MapTool](Category:MapTool "wikilink")
[Category:Tutorial](Category:Tutorial "wikilink")