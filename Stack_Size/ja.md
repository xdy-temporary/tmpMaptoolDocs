{{\#customtitle:スタック・サイズ|スタック・サイズ — MapToolDoc}}

## スタックとは？

<div style="color:gray">

When MapTool starts, the Java Virtual Machine (the program that lets
MapTool run on your computer\!) configures a number of settings for the
program. Two of these settings involve the available memory given to
MapTool: main memory, and the **stack**.

</div>

MapTool の起動時、JAVA仮想マシン（これは君のパソコンでMapToolを動かすためのプログラムだ！）は MapTool
用にいくつかの設定を行う。そのうちの2つの設定は MapTool
が使用するメモリー、メイン・メモリーと**スタック**に関するものである。

### メイン・メモリーの割り当て

<div style="color:gray">

The main memory allocated to MapTool simply indicates how much of your
computer's RAM MapTool can play with - if you have, for instance, 2GB of
RAM, you can tell MapTool that it can play around with 1GB; likewise if
you want, you can say "MapTool can only use 256KB of RAM\!"

</div>

MapTool
へのメイン・メモリーの割り当ては単純にパソコンのRAMをMapToolがどれだけ利用可能かを示せば良い。たとえば、2GBのRAMがあるなら、MapTool
に潤沢な1GBのメモリーを与えても良いし、望むのなら「MapToolは256KBのメモリーしか使っては行けません！」ということにしても構わない。

### スタック・サイズ

<div style="color:gray">

There is another memory amount that Java sets up when MapTool launches,
and this one has to do not with the total amount of memory that MapTool
gets, but the amount of memory any particular *thread* of a program can
eat up at a given time. This memory is called the *stack*.

</div>

MapToolが利用可能なメモリー総量以外に、起動時に Java
が設定するメモリー量に関するもう一つの設定は、プログラム内の*各スレッド*が一度に利用可能なメモリー量のことである。このメモリーを*スタック*と呼ぶ。

<div style="color:gray">

The stack is especially important when you are using macros to perform
calculations: the more complex a macro gets (and some macros can get
*very* complex\!) the more *stack memory* it will consume.

</div>

このスタックは計算を伴うマクロを使うときに特に重要なものだ。複雑なマクロは、より多くの*スタックメモリー*を消費するからだ（いくつかのマクロは*とてつもなく*複雑だ！）。

<div style="color:gray">

Eventually, a macro can get so complex, it eats up all the stack it is
permitted, and then cries out for more. When this happens, you get a
**Stack Overflow** error, and the macro will simply Not Work.

</div>

結局のところ、マクロは複雑になるもので、利用可能なスタックを食いつくすと更なるメモリを求めてだだをこね始める。そしてそのとき、**Stack
Overflow**のエラーを吐き出し、マクロは動かなくなってしまう。

## スタックの設定

<div style="color:gray">

In the beginning, MapTool used whatever default stack size Java felt
like setting. The actual amount varied from computer to computer and
operating system to operating system, but it was generally enough for
the simple macros that were in use at the time.

</div>

さしあたり、MapTool は Java
により設定される標準のスタックサイズをそのまま使用する。実際の容量はパソコンやOSにより様々であるが、単純なマクロを動作させるには十分な容量である。

<div style="color:gray">

As the power and flexibility of the macro code increased, macros began
to bump up against the limits of the default stack, and users began
adjusting their stack size to compensate.

</div>

強力かつ柔軟な能力を持つマクロになってくると、標準のスタックサイズの限界に達するので、ユーザーはスタックサイズを相応しい容量まで引き上げることになる。

### .BAT や .SH でのスタックサイズの設定

<div style="color:gray">

One of the ways to start MapTool is via the various *batch files* that
are included when you download and unzip a copy of MapTool. These files
are called things like **Launch Maptool-512M-Memory.bat** (for Windows
machines) and **Launch MapTool.sh** (for Linux). The number in the
filename indicates the amount of *main memory* allocated to MapTool. The
contents of these batch files looks like:

</div>

MapTool を起動するには、ダウンロードしZIPファイルを展開した MapTool
に含まれる数種類の*バッチファイル*を利用する方法がある。これらのファイルは**Launch
Maptool-512M-Memory.bat**（Windows用）や**Launch
MapTool.sh**（Linux用）といったファイル名になっている。ファイル名の数値は
MapTool が確保する*メイン・メモリーの容量*を指している。これらのバッチファイルの中身は次のようになっている：

<div style="color:gray">

The critical pieces here are the ones that begin with . The first,
indicates how much main memory (in this case, 512MB) is allocated to the
Java virtual machine.

</div>

ここで重要となる点はで始まる部分だ。一つ目の、はJava仮想マシンがどれほどメイン・メモリーを予約するかを表している（この場合は512MB）。

<div style="color:gray">

The second,  is how much memory is allocated to the stack (the "ss" is
for "stack size").

</div>

二つ目の、 はスタックがどれ程のメモリーを予約するか、ということだ（「ss」は「スタック・サイズ（stack size）」のこと）。

<div style="color:gray">

In versions of MapTool prior to 1.3.b54, the  is absent. To set the
stack size allocated (overriding the defaults that are picked by Java or
the value indicated), do the following:

</div>

バージョンが1.3.b54より古い MapTool では
は欠けている。確保するスタック・サイズを設定する（Javaが設定する初期値を上書きする）方法は下記の通り：

<div style="color:gray">

1\. Open the batch file in a text editor like Notepad.

</div>

1\. バッチファイルをメモ帳などのテキストエディターで開く。

<div style="color:gray">

2\. Edit the  line to be another value, for instance,  or  (M is for
megabytes, K is for kilobytes).

</div>

2\. の部分を、やなどの異なる値に書き換える（M はメガバイト、K はキロバイトを意味する）。

<div style="color:gray">

3\. Save the file, and then start MapTool using that batch file.

</div>

3\. ファイルを保存し、このバッチファイルを使い MapTool を起動する。

<div style="color:gray">

<font color="red">**WARNING**</font>: When you are changing the stack
size, the best settings are usually 512K, 1M, or 2M.
<font color="red">**DO NOT set it to 512M**\!</font> That will cause Bad
Things to happen.

</div>

<font color="red">**注意：**</font>スタック・サイズを変更する場合、一般的な最適値は
512K、1M、または2Mである。<font color="red">**決して 512M
と設定しないように！**</font> さもなくば大変なことになってしまうだろう。

### MapToolLauncherを使用したスタックサイズの設定

<div style="color:gray">

If you start MapTool with the Windows launcher, the third field is where
you can indicate stack size.

</div>

<div style="color:gray">

The Windows launcher defaults to a 2MB stack, which is perfectly
acceptable for pretty much all uses. If you change it, that new value
will be saved for the next time.

</div>

### WebStart利用時のスタックサイズの設定

<div style="color:gray">

If you start MapTool using the Java WebStart option, you can change the
settings here, too.

</div>

<div style="color:gray">

1\. Go to [The Launch
Page](http://www.rptools.net/index.php?page=launch)

</div>

<div style="color:gray">

2\. Click the **CUSTOMIZATION** link.

</div>

<div style="color:gray">

3\. Enter the values you want to use when you WebStart one of the
applications.

</div>

<div style="color:gray">

4\. Click on the links above to start the application you wish to use.

</div>

### Mac OSX でのスタックサイズの設定

<div style="color:gray">

These instructions apply to OSX users who have downloaded the **.dmg**
file from the [RPTools web site](http://www.rptools.net) and installed
MapTool from it. They were most recently tested on **Snow Leopard
10.6.3**. OSX users who are running MapTool using the WebStart approach
won't need these instructions since the CUSTOMIZATION link on the
[Launch page](http://www.rptools.net/index.php?page=launch) allows the
memory settings to be configured there.

</div>

<div style="color:gray">

(Unfortunately, Apple doesn't make this process easy. Their belief seems
to be that the application provider should allow these values to be
changed from inside the application but they didn't consider that the
Java memory settings cannot be changed from inside Java. )

</div>

<div style="color:gray">

The installer in the .dmg creates what Apple calls an "app" -- it's a
directory with the .app filename extension that contains all of the
files necessary for the application. This includes the configuration
file when the program is Java-based.

</div>

<div style="color:gray">

Here's the procedure for editing the configuration file (called a
property list). Note that I'm describing the technique that uses the OSX
TextEdit program because the only property list editor I have on my
machine is under the /Developer directory -- which is an optional
install for OSX so most people won't have it.

</div>

<div style="color:gray">

1.  Ctrl-click (or right-click) on the application icon (the filename
    should end with .app).
2.  Choose Show Package Contents and a Finder window will open.
3.  Open the Contents folder and locate the Info.plist file.
4.  Ctrl-click (or right-click) on that file and choose Open With \>
    Other...
5.  In the Choose Application dialog that opens, locate TextEdit and
    double-click on it.
6.  The Info.plist file is now open. There is an entry in the file
    called VMOptions (mine was about two-thirds of the way down the
    file) that should be changed to match the memory characteristics
    your GM wants you to use. Here's what mine looks like in case you
    want a reference for the following steps:
      -
        <key>VMOptions</key>
        <array>
        <string>-Xmx768m</string>
        <string>-Xms64m</string>
        <string>-Xss3m</string>
        </array>
7.  Replace your entries with the example text in Step 6. However, your
    GM may have directed you to use a particular value for the "maximum
    memory" setting. If so, replace the 768 number with the new maximum.
    The GM may also ask you to change the "stack size" amount -- that's
    the 3 number following the ss. (The 64 number never needs to be
    changed.) If you have other entries between the <array> and </array>
    lines, they should be removed because you're specifying completely
    new values.
8.  Use Cmd-Q and then choose Save. You can close the Finder window that
    opened as well.

</div>

<div style="color:gray">

You're all done\!

</div>

[Category:MapTool](Category:MapTool "wikilink")