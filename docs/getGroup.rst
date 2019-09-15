.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getGroup
   |version=1.3b48
   |description=Returns the specified capture group for the specified match that was found using [[strfind|strfind()]].

   |usage=
   <source lang="mtmacro" line>
   getGroup(id, match, group)
   </source>
   Where 
   {{param|id|is the id returned by [[strfind|strfind()]]}}
   {{param|match|is the number of the match found by [[strfind|strfind()]]}}
   {{param|group|is the number of the capture group found by [[strfind|strfind()]]}}

   |example=
   <source lang="mtmacro" line>
   [h: id = strfind("this is a test", "(\\S+)\\s(\\S+)\\s*")]
   match 1, group 0 = [getGroup(id, 1, 0)]<br>
   match 1, group 1 = [getGroup(id, 1, 1)]<br>
   match 1, group 2 = [getGroup(id, 1, 2)]<br>
   match 2, group 0 = [getGroup(id, 2, 0)]<br>
   match 2, group 1 = [getGroup(id, 2, 1)]<br>
   match 2, group 2 = [getGroup(id, 2, 2)]<br>
   </source>
   Returns:
   <pre>
   match 1, group 0 = this is
   match 1, group 1 = this 
   match 1, group 2 = is 
   match 2, group 0 = a test
   match 2, group 1 = a 
   match 2, group 2 = test 
   </pre>

   '''Example explained'''

   First off, escapes = "\" are used to let the character in question NOT be what it usually is. E.g. "d" is the alphabetical character "d"; "\d" however is thus NOT "d" and with that it gets a 'regex' meaning, in this case 'digit', so 1,2,3,4,5,6,7,8,9 or 0. The same the other way round, e.g. "." means "any character" if you actually want to find a "." (dot) in the text you thus use \. so its NOT the regex "any character" but just a ".". 

   Now the tricky bit: in maptool ALL escapes ("\") are eaten by the maptool parser UNLESS they are preceded by an escape themselves. This happens BEFORE the regex is parsed by the regex parser. THUS ALL ESCAPES MUST BE ESCAPED !! So in the above examples "\d" becomes "\\d" and "\." becomes "\\.". Really tricky it becomes when you want to find the "\" character. This is a regex symbol hence it needs to be escaped: "\\" but as its in maptool every escape must be escaped so it ultimately becomes "\\\\" !

   note that alternatively you can use [] ANY character in there will be looked at literally (and separately). So \\. == [.]. Obviously here too are exceptions, but read a regex tutorial for that.

   So back to the above example:

   *{{code|S}} = 'everything that is NOT a whitespace'
   *{{code|s}} = 'white-space'
   *{{code|+}} = '1 or more'
   *{{code|*}} = '0 or more'
   Have a look [http://www.addedbytes.com/download/regular-expressions-cheat-sheet-v2/png/ here] for an overview.

   Second important thing to know is that a group is defined by {{code|'('}}parenthesis{{code|')'}}: {{code|(group1)(group2)(etc.)}}, where group {{code|'0'}} returns the entire "match" result. 

   So {{code|\\S}} means grab the first none-whitespace you encounter, {{code|\\S+}} means grab the first none-whitespace you encounter AND ALL characters after that until you encounter a whitespace.
   Hence the regex statement looks for 
     ''{{code|(string of non-whitespace chars) whitespace (string of non-whitespace chars) 0 or more whitespaces}}''
   apply this to the text example and you get:
     MATCH 1: "(this) (is) " MATCH2: "(a) (code)"
   Hence in this example you have 2 MATCHES: Match 1 and Match 2 both consists out of 2 GROUPS: Group 1 and Group 2. Note that Group 0 will return the ENTIRE match.

   In summary: a search result can have multiple matches, and each match can consist out of 1 or more groups:
   * The first group {{code|'0'}} returns the ENTIRE match. 
   * Every group after that will return partial matches that are within {{code|()}}.

   [http://www.gskinner.com/RegExr/ Here a link] to test your regex statements (remember that for this applet you only use one {{code|\}} while in MT you need {{code|\\}}.


   '''Another Example'''
   <source lang="mtmacro" line>
   <!--
      (?i) - case insensative
      (d+) - number of dice (not optional)
      d - dice expression separator, upper or lower case
      (d+) - die sides (not optional)
      Optional:
         space* - space before modifier
         ([+-]*d+)* - roll modifier
         space* - space after modifier
         (w+)* - single word for damage type
         
      Example Groups: "(3)d(6)(+2) (Fire)"
   -->
   [H: regex = "(?i)(\\d+)d(\\d+) *([+-]*\\d+)* *(\\w+)*"]
   [H, while(1), code: {
      <!-- cancel input to break out of loop -->
      [H: abort(input("diceExp|3d6+2 Fire|Enter Dice Expression|TEXT"))]
      [H: id = strfind(diceExp,regex)]
      [H: valid = getFindCount(id)]
      [H, if(valid), code: {
         [H: numDice = getGroup(id,1,1)]
         [H: numSides = getGroup(id,1,2)]
         [H: dieMod = getGroup(id,1,3)]
         [H: dmgType = getGroup(id,1,4)]
         
         [H: output = strformat("Original: %{diceExp}<br>Dice Expression: %{numDice}d%{numSides}")]
         [H, if(! json.isEmpty(dieMod)): output = json.append(output,strformat("Modifier: %{dieMod}"))]
         [H, if(! json.isEmpty(dmgType)): output = json.append(output,strformat("Damage Type: %{dmgType}"))]
      };{
         [H: output = strformat("Invalid Dice Expression: [%{diceExp}]")]
      }]
      [H: broadcast(json.toList(output,"<br>"))]
   }] 

   </source>

   }}

`Category:String Function <Category:String_Function>`__
