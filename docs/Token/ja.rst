.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{Languages|Token}}

{{#customtitle:トークン|トークン}}

.. _トークン_トークン:

トークン: トークン
==================

.. raw:: html

   <div style="color:gray">

Every object that can be dropped down on a map and manipulated by the GM
or the players is a *token* of some type. The possible token types are
`Image Token <Image_Token>`__, `Library Token <Library_Token>`__, `PC
Token <PC_Token>`__, and `NPC Token <NPC_Token>`__. In addition, when
images are dropped onto a `map layer <map_layer>`__ other than the
**Token** layer, they take on the name *object* or *stamp* instead. (The
term *stamp* is often used to denote an image that is placed repeatedly,
sometimes in a pattern, whereas *object* means a less often used image.
A forest would be full of **tree stamps** but an office building would
have *table and chair objects*.)

.. raw:: html

   </div>

マップ上に配置され、GMやプレイヤーが操作するモノは\ *トークン*\ であり、いくつかの種類がある。有効なトークン種別は\ `画像トークン <Image_Token/ja>`__\ 、\ `ライブラリトークン <Library_Token/ja>`__\ 、\ `PCトークン <PC_Token>`__\ 、\ `NPCトークンだ <NPC_Token>`__\ 。さらに、\ **トークン・レイヤー**\ 以外の\ `マップレイヤーに配置した画像は <map_layer>`__\ 、トークンではなく\ *オブジェクト*\ や\ *スタンプ*\ と呼ばれる。（\ *スタンプ*\ という用語は、模様など頻繁に繰り返し配置する画像を指し、\ *オブジェクト*\ は少数使われる画像を指す。森は沢山の\ **樹木のスタンプ**\ を敷き詰めるが、オフィスビルでは\ **テーブルと椅子のオブジェクト**\ を使用する）

.. raw:: html

   <div style="color:gray">

This page discusses how tokens and objects are saved externally; the
overall file format as well as some specifics about how to manipulate
the contents of the **.rptok** file.

.. raw:: html

   </div>

このページでは、トークンとオブジェクトを外部に保存する方法、\ **.rptok**\ ファイルのファイル・フォーマットの全容と内容の操作に関する詳細に取り組む。

ファイル・フォーマットの全容
----------------------------

.. raw:: html

   <div style="color:gray">

Tokens can be saved by the token owner by right-clicking on the token
and choosing **Save As...**, then navigating to a directory and entering
a filename. The filename will automatically have **.rptok** appended to
the end to indicate that contents. The actual format of the file,
however, is an ordinary ZIP file! This means you can rename the file to
end with **.zip** and treat it as any other ZIP file. There are a number
of features related to this:

.. raw:: html

   </div>

トークンは所有者がトークン上の右クリックメニューから\ **Save
As...**\ を選択し、任意のディレクトリに、任意のファイル名で保存できる。このファイル名の末尾には自動的にファイルの種類を示す\ **.rptok**\ の拡張子が追加される。実のところ、このファイルの中身はどこにでもある
ZIP ファイルだ！
つまり、ファイル名を\ **.zip**\ で終わる名前に変更することで普通の ZIP
ファイルとして扱えるということだ。ファイルには次の特徴がある：

.. raw:: html

   <div style="color:gray">

-  All tokens are automatically stored in a compressed format.
-  All tokens can contain multiple data files inside

   -  One file is called **content.xml**
   -  Another one is **properties.xml**
   -  A directory is also included called **assets**

      -  The token image is stored here,
      -  The token portrait is stored here, and
      -  The token handout is stored here.

   -  The last file is called **thumbnail**

.. raw:: html

   </div>

-  全てのトークンは自動的に圧縮して保存される。
-  全てのトークンは内部に複数のデータ・ファイルを含むことが可能。

   -  ひとつ目のファイルは\ **content.xml**\ 。
   -  もうひとつは\ **properties.xml**\ 。
   -  さらに\ **assets**\ という名のディレクトリーも含まている。

      -  ここにはトークンの画像と、
      -  トークンの肖像画像と、
      -  トークンのハンドアウトが保存されている。

   -  最後のファイルは\ **thumbnail**\ だ。

トークン・ファイルの内容の解析
------------------------------

.. raw:: html

   <div style="color:gray">

Because the token files are ZIP files, you can easily extract the images
or other data from the token. To do so, unpack the ZIP file into a
directory on your computer. Look inside the **assets** directory and
you'll see multiple filenames. They will appear to be random strings of
letters and numbers, but actually the are checksums of the image they
contain. You can think of a checksum as a *summary* of the content.
These files don't have filename extensions so you may not be able to
view the content unless you use a program that ignores the filename
extension and looks at the content instead. One example utility that
does that is the GNU Image Manipulation Program, or GIMP for short.

.. raw:: html

   </div>

トークン・ファイルは ZIP
ファイルなので、トークンから画像やデータファイルを抜き出すのは簡単だ。パソコンの好きなディレクトリーにZIPファイルを展開すれば良い。\ **assets**\ ディレトリーの中にはいくつかのファイルがあることが確認できるだろう。そこには英数字がでたらめに並んだファイル名があるが、この文字は収容されている画像のチェックサムになっている。チェックサムは内容の\ *要約*\ と考たら良い。このファイル名は拡張子がないのでそのままでは画像を確認することができない。ビューアが拡張子を無視してファイルの中身を検査して判別するソフト（例えばGIMPなど）であれば表示することが出来る。

.. raw:: html

   <div style="color:gray">

Note that some versions of MapTool (which ones?) store the asset as the
image data encoded in XML. This makes the image unviewable using _any_
standard graphics tool. Trevor has said that this is a bug and future
versions will use the actual graphics image format (JPG or PNG).

.. raw:: html

   </div>

あるバージョンのMapTool（さてどのバージョンだったか…）では画像をXMLにエンコードして保存する。このため、一般的などの画像ツールを用いても画像を表示することは出来ない。トレボーは、この振る舞いは不具合であり、将来のバージョンでは実際の画像フォーマット（JPG、PNG）を使用すると述べている。

トークン・ファイル内の画像やデータを修正する
--------------------------------------------

.. raw:: html

   <div style="color:gray">

Modifying the images used in the token is more complex, however. Here
are the required pieces of the puzzle:

.. raw:: html

   </div>

トークンで使用している画像を修正することはより複雑だ。必要な材料は次の通り：

.. raw:: html

   <div style="color:gray">

#. Locate the new image(s) to be stored in the token,
#. Calculate the checksum of the image (it's an MD5 checksum),
#. Rename the image file to be the checksum, removing any filename
   extension in the process,
#. Move the new file into the **assets** directory,
#. Record the name of the old image from the **assets** directory, and
#. Remove the old image from the **assets** directory.

.. raw:: html

   </div>

#. トークンに格納する新しい画像を用意する。
#. 画像のチェックサムを計算する。（MD5チェックサム）
#. 画像のファイル名をチェックサムの値に変更し、拡張子を取り除く。
#. 新しい画像を\ **assets**\ ディレクトリに移動する。
#. **assets**\ にある古い画像のファイル名を記録し、
#. 古い画像を\ **assets**\ ディレクトリーから削除する。

.. raw:: html

   <div style="color:gray">

Sounds easy, right? But that's only half of it. It turns out that just
dumping images into the **assets** directory wouldn't tell MapTool
enough about the image, such as what size to scale it to and whether it
represented the portrait or handout image. Those details are stored in
the **content.xml** file. This file is **NOT** in the **assets**
directory, but is at the top level of the unpacked ZIP file.

.. raw:: html

   </div>

実に簡単だが、まだ行程の半分だ。画像を\ **assets**\ ディレクトリーに放り込んだだけではMapToolに十分な情報（画像サイズや、どのファイルが肖像画像やハンドアウト画像であるかなど）を伝えることにはならない。これらの詳細は\ **content.xml**\ に格納される。このファイルは\ **assets**\ ディレクトリーに\ **入れずに**\ 、展開したZIPファイルの最上位に配置する。

.. raw:: html

   <div style="color:gray">

If you open the **content.xml** file use a text editor. Do not use a
word processor or saving the file could corrupt the contents with extra
information created by the word processor. Use a program such as Notepad
or TextPad to perform any editing. Obviously, an editor that understands
the XML syntax can make editing much easier.

.. raw:: html

   </div>

**content.xml**\ を編集するには、テキストエディターを使用する。ワープロソフトは保存するときに余分な情報を加えてファイルを壊してしまうので使わないように。編集には「メモ帳」や「TextPad」などのソフトが相応しい。もちろん、XML構文を解釈する編集ソフトであれば申し分ない。

.. raw:: html

   <div style="color:gray">

You need to locate the portion of the XML file that refers to the
portrait image (if you were planning to replace the portrait) and
replace the 16-character checksum from the old asset with the
16-character checksum of the new asset. Fortunately, you recorded that
information as you performed the steps given above! But fear not -- if
you did not record the old checksum value, you can simply delete the
entire top-level directory and unpack the ZIP archive again, starting
from the beginning.

.. raw:: html

   </div>

肖像画像を置き換えるのであれば、XMLファイルの中から肖像画像を参照する箇所を見つけ出し、古い肖像画像の16文字のチェックサムを新しいものと置き換える必要がある。幸いにも、上記の行程で古い情報は記録済みだ！
記録し忘れてたとしても心配する必要はない。最上位のディレクトリーを削除し、もう一度ZIPファイルを展開し、最初からやり直せば良い。

.. raw:: html

   <div style="color:gray">

The simplest way to make the change, is to perform a string search for
the old checksum, replacing it with the new one whenever you find it.

.. raw:: html

   </div>

一番簡単な変更手順は、古いチェックサムを文字検索し、新しいものと置き換える方法だ。

.. raw:: html

   <div style="color:gray">

After you've made all of your replacements, use a ZIP utility to create
a ZIP file containing the contents of the top-level directory and
everything below it in the directory structure (which currently means
the **assets** directory). Be sure that the directory structure is
preserved because the **assets** directory must be there. Now the file
can be dragged and dropped into MapTool! You can change the filename
extension to **.rptok** if you like, but MapTool isn't particular about
the name of the file, only about the contents.

.. raw:: html

   </div>

全ての変更作業が終わったら、ZIPツールを使ってこれまでのファイルを含む最上位ディレクトリーを下位のディレクトリー構造（\ **assets**\ ディレクトリーが重要）を保ったままZIP形式で圧縮する。\ **assets**\ ディレクトリーがなければならないのでディレクトリー構造を必ず確認するように。これでMapToolにファイルを配置できるようになった！
お好みでファイル名の拡張子を\ **.rptok**\ に変更しても構わないが、MapToolはファイル名ではなく、ファイルの中身を重視する。

`Category:Token <Category:Token>`__
