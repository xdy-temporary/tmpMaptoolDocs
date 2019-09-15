.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=if
   |version=1.3b38
   |description=
   Is used to check whether a certain code ''expression'' should be executed or not. If the ''condition'' to be evaluated with this function is {{true}}, the first ''expression'' of code is the result, otherwise the second ''expression'' of code is the result.

   {{note|Note that both ''expressions'', the true and the false, are evaluated!
   This means that updates, macro calling, etc. in '''both''' ''expressions'' will be executed regardless of the test result.<br />
   Therefore, this function should only be used in limited cases where the ''expressions'' are simply returning a value.}}

   This function doesn't have the parentheses limit that the roll option has:
   <source lang="mtmacro">
   [if(((1))): 1;0]     <!-- in this case if() roll option fails -->
   [if(((1)),1,0)]      <!-- in this case if() function    works -->
   </source>
   |usage=
   <source lang="mtmacro" line>
   if(condition, trueExpr, falseExpr)
   </source>
   '''Parameters'''
   * {{code|condition}} - What is tested to determine is the {{code|trueExpr}} or {{code|falseExpr}} will be executed. This follows the standard rules for ''conditions'' that can be found in the [[Macros:Branching_and_Looping|Branching and Looping]] article.
   * {{code|trueExpr}} - A section of code that is returned if {{code|condition}} is {{true}}.
   * {{code|falseExpr}} - A section of code that is returned if {{code|condition}} is {{false}}.
    
   <!-- The 'nbsp' is needed to force the DIV to close. -->
   |examples=
   '''Example 1:'''
   <source lang="mtmacro" line>
   [h: a = 10] [h: b = 20]
   [r: if(a > b, "A is larger than B", "A is not larger than B")]
   </source>
   :'''Returns:''' {{code|A is not larger than B}}


   '''Example 2:'''
   <source lang="mtmacro" line>
   [h: number = 1]
   [r: if(number >= 1, 20, "")]
   </source>
   :'''Returns:''' A ''blank string'', please note that a ''blank string'' is not an ''empty variable'' if you were to assign the ''output'' of this function.


   '''Example 3:'''
   <source lang="mtmacro" line>
   [h: variable = "Foobar"]
   [r: if(variable == "Text", 1, 0)]
   </source>
   :'''Returns:''' {{code|0}}


   '''Example 4:'''
   <source lang="mtmacro" line>
   [h: variable = 20]
   [property = if(variable > 0 && variable < 20, 1, 0)]
   </source>
   :'''Returns:''' {{code|property}} set to {{code|0}}


   '''Example 5:''' Usually its better to use the roll option version {{roll|if}}. Sometimes it's pretty handy to use the version documented here, since you can easily embed it in loops and expressions.

   Let's say you want to check if one of a player's tokens has Initiative, you could do it this like this:
   <source lang="mtmacro" line>
   [h: tokensOfPlayer = getOwned(getPlayerName(), "json")]
   [h: hasIni = 0]
   [h: iniToken = getInitiativeToken()]
   [h, foreach(id, tokensOfPlayer): hasIni = if(id!=iniToken,hasIni,1)]
   </source>

   |also=
   [[Macros:Branching_and_Looping|Branching and Looping]], [[if_(roll_option)|if (roll option)]]
   }}

`Category:Miscellaneous Function <Category:Miscellaneous_Function>`__
