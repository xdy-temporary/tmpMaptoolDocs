The following is the full code for the [Creating a List Input with Names
and Images](Creating_a_List_Input_with_Names_and_Images "wikilink")
tutorial.

``` mtmacro
[H: tokenList=getExposedTokenNames()]
[H: imgList = tokenList]

[H: Num = listCount(imgList)]

[h,COUNT(Num),CODE:
{
[h:tokenName=listGet(imgList,roll.count)]
[h,token(tokenName): image=getTokenImage()]
[h:imgList=listReplace(imgList,roll.count,tokenName+" "+image)]
}]

[h:status=input(
    "Target|"+imgList+"|Select Target|LIST|SELECT=0 ICON=TRUE ICONSIZE=30",
    "newName| |Enter a new name for this token"
)]
[h:abort(status)]


[h:targetName = listGet(tokenList,Target)]

[h:switchToken(targetName)]

[h:token.name=newName]
The token's name has been changed to <i>[r:newName]</i>.
```

[Category:Cookbook](Category:Cookbook "wikilink")