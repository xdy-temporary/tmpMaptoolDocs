.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=strfind
   |version=1.3b48
   |description=
   Finds and extracts substrings from a string. {{code|strfind()}} is used to match a pattern against an input string and extract all of the capture groups. The function returns an id which can be used with other functions to extract the information. The supplied pattern is a [[Macros:regular_expression|regular expression]]. 

   Functions related to {{code|strfind()}}:
   * [[Macros:Functions:getFindCount|getFindCount(id)]]
   * [[Macros:Functions:getGroupCount|getGroupCount(id)]]
   * [[Macros:Functions:getGroup|getGroup(id, matchNo, groupNo)]]
   * [[Macros:Functions:getGroupStart|getGroupStart(id, matchNo, groupNo)]]
   * [[Macros:Functions:getGroupEnd|getGroupEnd(id, matchNo, groupNo)]]

   Both {{code|groupNo}} and {{code|matchNo}} start at 1, the special group number {{code|0}} returns the whole pattern match.
   ''Groups'' are the regex parts in {{code|"("}} parenthesis {{code|")"}}, so 1 returns the string that matches the first regex statement in {{code|()}}, 2 returns the second, etc.

   |usage=
   <source lang="mtmacro" line>
   strfind(str,  pattern)
   </source>

   |example=
   <source lang="mtmacro" line>
       [h: id = strfind("This is a really useless test", "(\\S+)\\s+(\\S+)\\s*")] 
       [r: getGroupCount(id)]
       [r: getFindCount(id)] 
       [r: getGroup(id, 1, 1)]  
       [r: getGroup(id, 2, 2)]
   </source>
   Returns:
       2 
       3 
       This 
       really 
       This is


   A slightly more usefull and advanced example:
   <source lang="mtmacro">
   [h:id = strfind("Command-20, Sleight of Hand 10, Knowledge (Arcana) +5", "([^,]*?)\\s?([-+]?\\d+)(,|\$)")]
   <b>First group</b><br>
   [r,count(getFindCount(id), "<b>Next group</b><br>"), code: {
       "[r:getGroup(id, roll.count+1, 0)]" <br>
       "[r:getGroup(id, roll.count+1, 1)]" <br>
       "[r:getGroup(id, roll.count+1, 2)]" <br>
   } ] </source>
   Returns:
       '''First group''' 
       "Command-20," 
       "Command" 
       "-20" 
       '''Next group''' 
       " Sleight of Hand 10," 
       " Sleight of Hand" 
       "10" 
       '''Next group''' 
       " Knowledge (Arcana) +5" 
       " Knowledge (Arcana)" 
       "5"
   }}

`Category:String Function <Category:String_Function>`__
