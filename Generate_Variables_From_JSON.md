When working with string properties, the function is an automated way to generate variables from the keys within a string property. For example, if you have the following string property:

``` mtmacro
[prop = "name=Axe; damage=1d12; proficiency=2;"]
```

You can use to generate a variable for each key - in other words, using the function to generate a list of locally accessible variables , , and .

There is no equivalent function for JSON objects. However, the following routine can be inserted into any macro to efficiently generate the variables in question.

<hr>
``` mtmacro
[h:varList=json.fields(testObj)]

[h,foreach(var,varList),CODE:
{
     [value = json.get(testObj,var)]
     [set(var,value)]
}]
```

<hr>
The variable represents the JSON object that is fed into the routine. The variables generated will be available within the scope of the running macro (but not outside).

<Category:Cookbook>