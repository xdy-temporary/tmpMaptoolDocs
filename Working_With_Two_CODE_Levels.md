# Working With Two CODE Levels

One of the biggest limitations of the MT macro script is that the script
parser can't handle more that 2 levels of . So this will work:

` [If(condition), CODE:{`
`   [if(another_condition), CODE:{`
`      [code to execute when true]`
`   };{}]`
` };{}]`

And this won't:

` [If(condition), CODE:{`
`   [if(another_condition), CODE:{`
`     [if(another_condition), CODE:{`
`       [code to execute when true]`
`     };{}]`
`   };{}]`
` };{}]`

  - Note that this is an example, there are other occasions where one
    uses , e.g.  instead of . This is subject to the same problem. The
    only exception I've encountered is with json objects: . This is NOT
    subject to this problem. However I believe that if you use  instead
    of  it won't work (or the other way around).

## So what to do when you do need to go deeper?

Basically there are 3 general tricks you can use if you need to go
deeper:

### Trick 1: Create another UDF

One of the most common *tricks* is to create a User Defined Function
(UDF) and call this in the nested level. Within this UDF you can yet
again go 2 CODE levels deep.

### Trick 2: Code smarter

Many many examples can be given here, but you can achieve a lot by using
roll options e.g.:

` [if(condition): if(another_condition, "show this", "else show this"); if(yet_another_condition, "show this"; "else show this")]`

You can also work with multiple roll options, but this *should* not
work, but does sometimes work e.g.:

` [foreach(item,items), if(item == someVar), CODE:{};{}]`

works while:

` [if(listCount(items)>2), foreach(item,items), CODE:{};{}]`

won't work.

A lot can be achieved by restructuring your code in this manner.

### Trick 3: Store commands

One final trick I recently learned from Ahzrei is a rather dirty trick
but can be used in certain circumstances. In my case I have code that
needs to be executed that is already two levels deep and then I ALSO
want to execute this for certain selected tokens. In this case you can
first store the to-execute-commands in a json object and then exit the
two loops. Now you have a json object containing all code that needs to
be executed onto certain tokens. For this you can start a new loop that
uses  per json object per token id.

### Trick 4: More than 2 CODE levels

Officially this is NOT supported in MT and thus it *could* break your
code if improperly used. That said, I've been using this trick for 6
(dd: 2017) years now and my code is flooded with it and have not yet
encountered any issue, so its reasonable to assume that its safe to use.
Disclaimer: Still this is at your own risk.

As it turns out it IS possible to have more then 2 nested code levels
but in order to do that you have to *mislead* the parser. This is done
as follows:

``` mtmacro numberLines
[if(1), CODE:{
    [if(1), CODE:{
        [if(1), CODE:{
              you should never see this in the chat...but you do!
        ''
        };{''}]
    ''
    };{''}]
''
};{''}]
```

Important notes:

  - put the  in the ELSE statements as well when they're not empty.
  - do NOT use the single quote  anywhere in the nested code\!\! It
    \*can\* be used, but it \*can\* also lead to errors\! I've not been
    able to determine when it goes right and when wrong, so to be safe:
    don't use them.
  - if you use multiple embedded if(),code statements, make sure that
    you use add the else: {} part as well (like in the above example),
    even if its empty. Due to this 'hack' its possible that if not all
    elses are given but some are that the an else is used of an embedded
    if statement instead of the one intended\!\!

What it boils down to is to add two single quotes  at the END of EACH
code block. This will fool the MT parser and it will accept this
nesting. I've tried it upto 9 nestings without a problem (more is probly
also no issue). Do keep in mind that this will SERIOUSLY impact the
stack though, so don't go writing huge code blocks this way. I mainly
use it for cases where you only have a few lines of code but are
required to go 3 or 4 nestings deep and its just annoying to create a
separate macro for one or two lines of code.

Note that if in the above example the  will show up in the chat. You can
also use  instead to prevent this.

\--[Wolph42](User:Wolph42 "wikilink") 16:22, 19 March 2011 (UTC)

[Category:Cookbook](Category:Cookbook "wikilink")