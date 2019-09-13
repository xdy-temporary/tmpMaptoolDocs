This user defined function redefines the standard  function, allowing it
to be given a number, empty string, or JSON object/array and not throw
an exception.

### Macros

Place both of these macros on the same library token.

**1.3b56+**

<hr>

**onCampaignLoad**

``` mtmacro numberLines
[ defineFunction( "eval", "evalFunction@this", 1, 0 ) ]
```

<hr>



<hr>

**evalFunction**

``` mtmacro numberLines
//  Error handling
[ assert( argCount() >= 1, "<b>eval()</b> - Invalid number of parameters <i>0</i>,
                            expected at least <i>1</i> parameter.", 0 ) ]

//  Initialise variables
[ X_Expression_X = arg( argCount()-1 ) ]
[ X_CancelEval_X = 0 ]
[ X_TypeTest_X = json.type( X_Expression_X ) ]

//  Handle all numbers
[ if( isNumber( X_Expression_X ) == 1 ), code:
{
   [ X_CancelEval_X = 1 ]
} ]

//  Handle empty strings
[ if( X_TypeTest_X == "UNKNOWN" ), code:
{
    [ if( X_Expression_X == "" ), code:
    {
        [ X_CancelEval_X = 1 ]
    } ]
} ]

//  Handle JSON types
[ if( X_TypeTest_X == "ARRAY" || X_TypeTest_X == "OBJECT" ), code:
{
    [ X_CancelEval_X = 1 ]
} ]

//  Evaluate or cancel, then return
[ if( X_CancelEval_X == 1 ), code:
{
    [ macro.return = X_Expression_X ]
};{
    [ macro.return = oldFunction( X_Expression_X ) ]
} ]
```

<hr>



[Category:Cookbook](Category:Cookbook "wikilink")