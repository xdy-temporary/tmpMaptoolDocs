.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=replace
   |version=1.3b48
   |description=
   Returns the string with the occurrences of a pattern replaced by the specified value. If the number of times to perform the replacement is not specified then all occurrences of the pattern are replaced. Pattern can be a [[Macros:regular_expression|regular expression]]. This means if the pattern string contains any regular expression special characters they must be escaped.

   |usage=
   <source lang="mtmacro" line>
   replace(str, pattern, value)
   </source>
   <source lang="mtmacro" line>
   replace(str, pattern, value, times)
   </source>

   |example=

   '''Example 1'''
   <source lang="mtmacro" line>
       [r: replace("This is a test", " ", "-")]
       [r: replace("This is a test", " ", "-", 2)]
   </source>
   Returns:
       This-is-a-test
       This-is-a test

   '''Example 2'''<br>
   This is useful for search+replace of any string you feed to {{code|replace()}} that might have regex codes in it like parenthesis:
   <source lang="mtmacro" line>
       [r: tString = "is (a) t"]
       [r: replace("This is (a) test", "\\Q" + tString + "\\E", "-")]
   </source>
   Returns:
       This-est

   '''Example 3'''
   <source lang="mtmacro" line>
       [r: name = replace("wolph 5","(.*?) [0-9]+","\$1 42")]
   </source>
   returns:
       wolph 42
   The {{code|$}} normally means to match end-of-line, but only when it's at the end of the pattern. In this case, it's at the beginning of the pattern. And that means if the character immediately following is a digit (such as {{code|$1}}), those characters are replaced by the source string matched by the corresponding set of parentheses in the regular expression.

   '''Example 4'''<br>
   Note that multiple {{code|.*}} in the search string correspond with multiple {{code|$#}}:
   <source lang="mtmacro" line>
     [h:lastPath = [{"x":1,"y":0},{"x":1,"y":1},{"x":1,"y":2}]]
     [r:result = replace(lastPath, '\\{"x":(.*?),"y":(.*?)\\}', '"X\$1Y\$2"')] 
   </source>
   returns:
     ["X1Y0","X1Y1","X1Y2"]

   }}

`Category:String Function <Category:String_Function>`__
