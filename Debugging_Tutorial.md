# Debug Methods For Maptool Scripting

*A tutorial to squash little critters from your MT code.*

## What is this about?

I've been working with MT for over 2 years now and I can still remember
the initial struggle I had due to the lack of any debugger. As it turns
out there are quite a few methods to debug your code but unfortunately
they're not very obvious to find. So here is a short summary of
available tools.

I've marked this article as 'advanced' as it does assume that you know
the basics of MT script, like [Library Token](Library_Token "wikilink"),
[onCampaignLoad](onCampaignLoad "wikilink") and [User defined
functions](defineFunction "wikilink").

## Notepad++

The most basic form of debugging is using an editor that uses syntax
highlights for your code. Np++ can help with that, especially in
combination with
[rpedit](http://forums.rptools.net/viewtopic.php?f=8&t=16770) created by
Aliasmask. You can find the install for np++ and syntax highlighting
(also by AM)[here](http://forums.rptools.net/viewtopic.php?f=8&t=13690).
Once you've done that go to: Settings -\> Preferences -\> New
Document/Default Directory to automatically convert ANSI files to UTF-8
without BOM on open (so both the radiobutton and the checkbox). This
helps when copy pasting code straight from a website into np, sometimes
ansi character creep in there with which MT cannot work giving errors
like 'unknown character 0x0A'.

## Pause

The most basic and I think most used method is the 'Pause' method as
developed by zEal. The only way in MT to interrupt the flow of the code
is with the use of . zEal created some clever code around  to use for
debugging. His full contribution can be found here:
[1](http://forums.rptools.net/viewtopic.php?p=110935#p110935). Its
working is simple as shown in this example:

``` mtmacro numberLines
  [h:strength = 5]
  [h:toughness = 10]
  [h:pause("strength", "toughness")]
  [r:"This text you'll see AFTER the pause"]
```

The running code will stop after the toughness=10 line, show the two
variables both name and value and after you've clicked ok the code will
continue. It is possible to just run:

``` mtmacro numberLines
 [h: pause()]
```

in several places in your code so you can check where it crashes.

In order for pause to work in your campaign you will need a library
token with an [onCampaignLoad](onCampaignLoad "wikilink") macro
containing the following line:

``` mtmacro numberLines
  [ defineFunction("pause", "pause@this", 1, 0 ) ]
```

and you will also need a macro called  on the same library token
containing the following code:

``` mtmacro numberLines
    [ toolkit.DebugVariableCount = argCount() ]
    [ toolkit.DebugInputParameter = ".|<html>" +
        "<table cellspacing='2' cellpadding='0' style='background-color:#595751'>" +
        "<tr><td>" +
        "<table width='300px' cellspacing='0' cellpadding='2' style='background-color:#FAF9F5;'>" +
        "%{toolkit.DebugVariableRows}</table></td></tr></html>" +
        "|Debugger|LABEL|SPAN=TRUE"
    ]
    [ toolkit.DebugVariableRow = "<tr %{toolkit.DebugVariableRowStyle}><td>" +
        "<b>%{toolkit.DebugVariableName}</b></td><td>%{toolkit.DebugVariableContent}" +
        "</td></tr>"
    ]
    [ toolkit.DebugVariableRows = "<tr style='background-color:#E0DDD5; font-size:1.1em;'><td><b>Variable</b></td><td><b>Value</b></td></tr>" ]
    [ count( toolkit.DebugVariableCount ), code:
    {
        [ toolkit.DebugVariableRowStyle = "" ]
        [ toolkit.DebugVariableName = arg( roll.count ) ]
        [ toolkit.DebugVariableContent = eval( arg( roll.count ) ) ]
        [ if( floor( roll.count/2 ) == roll.count/2 ), code:
        {
            [ toolkit.DebugVariableRowStyle = "style='background-color:#EDECE8;'" ]
        } ]
        [ toolkit.DebugVariableRows = toolkit.DebugVariableRows +
            strformat( toolkit.DebugVariableRow )
        ]
    } ]
    [ if( toolkit.DebugVariableCount == 0 ), code:
    {
        [ toolkit.DebugVariableRows = "<tr><td style='font-size: 1.4em' align='center'><b>Pause</b></td></tr>" ]
    } ]

    [ toolkit.DebugBreak = input( strformat( toolkit.DebugInputParameter ) )]
    [ abort( toolkit.DebugBreak ) ]
```

You can also find this code after the above link to zEal's post.

**Tip:** if you want to copy-paste the above code or the code from the
post, then FIRST paste it into a simple text editor and copy it from
there and THEN paste it into the MT macro. This prevents from
unintentional copying e.g. linefeeds (0x0A). Even better is using np++
in UTF-8 setting (see header here above).

### Where pause goes wrong

A couple of useful things to know when you start using .

  - if you use it at the top of your macro to e.g. check the values of
    the passed on arguments like this:

<!-- end list -->

``` mtmacro numberLines
  [tmp = macro.args]
  [pause("tmp")]
  [var1 = arg(0)]
  [var2 = arg(1)]
```

then  will no longer exist\!\! The value that  contain changes as soon
as  has run as it has its own scope and redefines it. Usually this can
lead to inexplicable errors so beware of this\! It is better to use it
like this:

``` mtmacro numberLines
  [tmp = macro.args]
  [var1 = arg(0)]
  [var2 = arg(1)]
  [pause("tmp")]
```

  - can only handle very simple HTML code, so if you want to debug a
    dynamic form which you have assigned to a variable, I would suggest
    you use a combination of the [Show_HTML](Show_HTML "wikilink")
    method and put a  right after that.

## The log file

Going to a slightly more advanced method you can start using the log
file.

First off, if MT crashes you can always check the  file which is located
in your  directory. Its location varies per OS:

  - For win7 it is .
  - For MacOS it's  aka . Be aware that, because this directory's name
    begins with a dot, it's invisible in the Finder. So, either you use
    a utility like Onyx to make the Finder show invisible files, either
    you use the "Go to \> Go to directory…" Finder menu and type one of
    those path.

You should also find a  file in that directory. The XML file tells
MapTool what to send to the  file. Per default MT install, this will
only log generated errors.

You can however also replace this file with the one that you can find in
the MapTool install directory (the one you unzipped initially). In the
directory  you find a  file. You can replace the existing XML file in
your  directory with that one (don't forget to rename it to  \!) and it
will log ALL macro code. If your code crashes or generates weird errors,
you can check the log file to see where it went wrong.

**MAC Users**: upto b89 the  does NOT contain these logging XML files.
You will need to download the  file to get those.

This can render into a HUGE log file and slows down MT a bit, so be
careful with it. In my case I have a PC and Laptop, the laptop I use for
running the games, so no logging, the PC I use for coding so logging is
always turned on on that PC.

BUILD 91 AND LATER

if your using b91 or later, there is a launcherxxxx.jar provided. When
you run that you will have an advanced tab. There you see 'Macro
Handling' checkbox. Check that. This will automatically replace the
logging.xml file for the right one as described above. Don't forget to
delete the log.txt file first, so its cleared.

if for some reason this does not work under b91 (as is with one of my
PCs) you need to manually replace the logging.xml as described above AND
you must start maptool WITHOUT the launcher, as the launcher will simple
reset the logging.xml. Instead run maptool from a .bat file. To do this
simply create a file called runMaptool.bat and edit it. Place in the
.bat the line:

` java -Xmx1024M -Xss4M -jar maptool-1.3.b91.jar run`

Save it and run it.

## The Console

The console is the real kicker. I found out about this after a year or
so and since I'm aware of it it has made coding and debugging in MT SO
MUCH SIMPLER\!\!

**On Windows**

To activate it you need to do 2 things:

  - first you need to replace the  file with the  (or check 'macro
    handling' in the launcher for b91+) as described here above.
  - second you need to edit your  file (called  on \*nix based OS's).
    This file you will find in the install directory. The content will
    look like something like this:

` MAXMEM=1024`
` MINMEM=64`
` STACKSIZE=4`
` JVM=C:\Program Files\Java\jre6\bin\javaw`
` PROMPT=true`

depending on your settings and OS. You need to remove only ONE letter:
the  from . So it becomes:

` JVM=[what it reads here differs per OS]java`

Now you will have a console which shows the MT script real-time. Combine
this with strategically placed 's and debugging becomes a breeze. Here's
my usual screen layout when I'm debugging:
[image:Wolph42_Debugging_Screenshot.jpg](image:Wolph42_Debugging_Screenshot.jpg "wikilink")


**On MacOS**

You'll find the Console utility in . Just launch it before you launch
MapTool.

All applications' messages, including MapTool, will appear in the
"Console messages" part.

If you want to focus on MapTool's messages you just have to open the
described in the Log File section above with the Console app. Just do a
right click on the  file and choose "Open with…" from the contextual
menu, and then of course Console. Don't try to open the file from the
Console app with the "File \> Open" menu, as the directory is invisible
and won't show.

You've got a convenient search field to filter out the messages. Don't
forget it.

**Notes:**

  - Text and comment is NOT ported to the console. So

<!-- end list -->

``` mtmacro numberLines
  Hello world
  <!-- this is comment -->
```

won't show in the console nor in the log. However:

``` mtmacro numberLines
  [r:'Hello world']
  [h:'<!-- this is comment -->']
```

will show up\! Note though the latter is slower than the former to
execute (which becomes noticeable around 200 to 400 of these lines, so
not much to worry about).

  - I personally find it very useful to quickly see at which macro I'm
    looking, so in the header of all my macros I add:

<!-- end list -->

``` mtmacro numberLines
  [h:'<!-- ------------------------------------MACRO NAME ---------------------------------------->']
```

and sometimes I also add a:

``` mtmacro numberLines
  [h:'<!-- ------------------------------------/END MACRO NAME ---------------------------------------->']
```

at the bottom, e.g. for the  function\!

  - If you're running heavy macros, especially ones with lots of loops,
    then you will notice that the code runs a lot faster when the
    console is minimized. Keep this in mind\!
  - In Windows you can change the console settings. Especially for the
    MT log this is very useful as the default console settings are  and
    . This means that lines are likely wrapped making them hard to read,
    and with a history of 300 lines you won't come far. You can change
    this by right clicking on the top bar of the console, a context menu
    should pop-up with . Here you go to the  tab and you can edit the .
    My settings are  and . Fortunately the settings are remembered by
    Windows so you only need to do this once.

## Broadcast

is a fairly new function to MT and is great for debugging purposes. The
advantage of  is that it ports the result to the chat IMMEDIATELY.
Usually all text to chat whether it is  or  will be accumulated until
all macros are done and THEN the text is ported to the chatbox. So in
case of an  or  or a crash in the code you will find either the
assertion message, a bug report or nothing at all. All the accumulated
text is discarded.

Two useful usages for :

### Using broadcast to track down a code crash

Let's say you have an macro of a few 100 lines, you run it and...
nothing or some vague message like . If you want to pin point the crash
you can simply put  lines between the code and see how far it gets. From
the output you can deduce the location of the crash. Here an example,
lets say you have:

` [a block of code]`
` [another block of code]`
` [and yet more blocks of code]`
` [and finally a last block of code]`

If you want to find out where the code stops:

` [a block of code]`
` [h:broadcast("1")]`
` [another block of code]`
` [h:broadcast("2")]`
` [and yet more blocks of code]`
` [h:broadcast("3")]`
` [and finally a last block of code]`

If the output to the chat is eg:

` 1`
` 2`

Then you'll know that the error is somewhere inside .

### Using broadcast to track variable development

I usually use  to check my variables. However if something goes wrong
somewhere in a 500+ loop, you will be clicking  a lot. In these
instances it is much easier to add a:

``` mtmacro numberLines
  [broadcast("variable_name: "+variable_name+"another_variable_name: "+another_variable_name)]
```

inside the loop. This way the code is not interrupted but you will get
to see where the loop goes haywire.

Like with pause() there is also a more advanced debug macro created in
maptool. This is bot_debugInfo() In principle it makes use of the
broadcast method but it has a huge set of extra options to make more
optimally use of this function and to easier track down issues. This
function is part of the [Bag of
Tricks](http://forums.rptools.net/viewtopic.php?f=46&t=16066). Note that
pause() is also part of this bag, so if you install it you don't need to
create it seperately.

## Bug tracking by elimination

This is a very basic method and also a 'if all else fails'. When you've
used all the other methods and are still stuck, its time to start
debugging by elimination. Most common use is in a code:{} (or frame:{},
dialog:{}, etc.) block that has a bug inside the block but generates an
error report on the 'code block' level, making the broadcast, pause,
console methods useless.

The method is very simple and can take different forms. The first is
simply deleting large chunks of code and running the macro again until
you've eliminated the bug. Then you start placing code back again and so
you can narrow down to the line(s) where the code crashes. Usually in a
large macro with a big code block that crashes, I start with deleting
the entire body (that is everything between the { } ) to see if the
block itself works. If that's the case I start putting back lines of
code until the macro crashes. Its tedious, but VERY effective.

Another more preferable approach (but not always possible) is to remove
the code:{} block itself and run the code body with the required
parameters. So e.g. run this:

` [foreach(element, elements), CODE:{`
`   [if(element == 1): bla]`
`   [bla]`
` }]`

as this

`   [element = 1]`
`   [if(element == 1): bla]`
`   [bla]`

this way the macro will crash on the specific line which allows you to
use the console, pause, broadcasts methods again.

'Note' that in case of dialogs and frames, you can do the same thing.
The generated HTML will be ported straight to the chat. This can however
lead to a stack overflow (porting large portions of text straight from a
macro to the chat will cause that), you can omit that by raising the
stack to 20 (TEMPORARILY\!, normally you should never go higher then 4
during a game).

## Typical Bugs

Here I'll give a few examples of things that typically go wrong when
coding. It is useful to check this once in a while as a reminder and I
hope that others will add to this list so this accumulates in a FOB
(frequently occurring bugs).

### My number one

``` mtmacro numberLines
can't
```

or better recognized in

``` mtmacro numberLines
<!-- this you can't do in MT script -->
```

This is not the most occurring bug, but it certainly is the most
annoying as it REALLY screws up your code and it is hell to debug. The
issue is with the single quote. When strategically placed this can
result in an entire section of code not being executed, picking it up
later or dropping back to the parent macro altogether. IF you also close
the quote (that is put a second one in the comment as well) then there
will be no issue, also if you encapsulate it in a  (and not ) it will
run along nicely.

About the latter, although the MT script allows you to stuff like this

` He hits for [r:1d6+strength]`

I find it bad practice (and generally the first step in hard to debug
code) to NOT follow the sacred 'code' code, which is: 1. input 2.
process 3. output

example

` <!- input -->`
` [h:input("strength")]`
` <!- process -->`
` [h:textOut = "He hits for 1d6 + "+strength+": "+1d6+strength]`
` <!- output -->`
` [r:textOut]`

### THE number one

It remains a guess but I think it is a safe assumption that two  in one
line of code (with the exception of switch and code) is the most
commonly made mistake. Fortunately MT generates clear debug info on this
one the syntax is ALWAYS:

`[option , option , option : function]`

### Stray semicolon ';' in the chat

I think this one is in second place, not a bug per se, but annoying
nonetheless. This occurs when you forget to include the *false* part in
an  statement when using the code option, e.g.:

``` mtmacro numberLines
  [if(statement), CODE:{apparently the statement is true}]
```

will generate the following output:

` apparently the statement is true`
` ;`

this is easily prevented by adding  :

``` mtmacro numberLines
  [if(statement), CODE:{apparently the statement is true};{}]
```

### Stray comma ',' in the chat

Another common 'bug' encountered regularly are stray comma's. Obviously
there can be numerous reasons for this to happen but in most cases it is
because of a loop like  or . This for example:

``` mtmacro numberLines
  [foreach(number, "1,2,3,4"), CODE:{[h:"don't show this"]}]
```

will generate:

` ,,,`

For this particular example this is simply solved by hiding the output
altogether:

``` mtmacro numberLines
  [h,foreach(number, "1,2,3,4"), CODE:{["don't show this"]}]
```

Note that when the outer loop is hidden, that the contents are hidden by
default so the h: is not necessary. If you do wish to show the context
BUT not the comma's, you need to define the delimiter e.g.:

  - Seperate by nothing:

<!-- end list -->

``` mtmacro numberLines
  [r,foreach(number, "1,2,3,4", ""), CODE:{[r:"Hello World"]}]
```

  - Seperate by space:

<!-- end list -->

``` mtmacro numberLines
  [r,foreach(number, "1,2,3,4", " "), CODE:{[r:"Hello World"]}]
```

  - Seperate by break:

<!-- end list -->

``` mtmacro numberLines
  [r,foreach(number, "1,2,3,4", "<br>"), CODE:{[r:"Hello World"]}]
```

**Tip**: To pin point the origin of a stray comma in a large chunk of
code, you can put numbers (1,2,3,4,etc) between the code. These numbers
will appear in the chat and the comma will be among them, making it
easier to find it.

### Closing syntax characters

A myriad of errors can be created by not closing off syntax characters:

To help diagnose this, copy your macro into a text editor.
\[<http://forums.rptools.net/viewtopic.php?t=13690>| aliasmask's
Notepad++ mod\] is recommended as it has other uses for MapTool. Use the
 function to count each of the characters, and the totals should equal
for each pair.

Note, if you use strings which contain only one of the paired syntax
characters e.g.  you should *close* off the pair in a comment:

``` mtmacro numberLines
  [h: '<!-- This comment is to close off the bracket in the next line ( -->']
  [h: broadcast ("1) This is the first point.")]
```

other issues can arise with stray 'single quotes' in words like . If
these are not enclosed in " " or closed of by another ', you will get
bogus output or syntax errors.

### Cheater you have been reported

This *functionality* is embedded to prevent cheating… obviously. However
this can also result in this error message (and only this error message)
in your own code\! This typically happens when  the result of an  call,
where the  result contains « guillemots »: . E.g. paste this into your
chat:

``` mtmacro numberLines
  [h:result = evalMacro(decode("4 The attack scoops out one of the target's eyes, inflicting <b>[Fat=1d5] level(s) of Fatigue"))]
  [h:broadcast(result)]
```

To debug this I store  in a [lib:token](Library_Token "wikilink")
property before I do the . From the text it is usually easy to find
where the guillemots have entered. So:

``` mtmacro numberLines
  [h:result = evalMacro(decode("4 The attack scoops out one of the target's eyes, inflicting <b>[Fat=1d5] level(s) of Fatigue"))]
  [h:setLibProperty("debugOutput", result, "lib:Token")]
  [h:broadcast(result)]
```

Then after running the macro I can copy paste that property inside a
text editor and track down the guillemots.

### The Switch Case

Another really annoying little bug. If you ever get stuck with the use
of  cause it keeps generating error reports and you REALLY can't find
the issue, then likely you have used  or  or any other variant with a
capital letter in it. As it happens  is case-sensitive (yes it almost
looks intentional...). Anyway  ONLY works with  (so lower case only\!).

\--[Wolph42](User:Wolph42 "wikilink") 12:23, 7 June 2012 (UTC)

[Category:Tutorial](Category:Tutorial "wikilink")