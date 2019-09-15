.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{RollOption
   |name=switch
   |version=1.3b46
   |description=
   Chooses among several options and executes code based on the expression.

   |usage=
   <source lang="mtmacro" line>
   [switch(expression):
      case case1: body1;
      case case2: body2;
      default: defaultBody
   ]
   </source>
   '''Parameters'''
   {{param|expression|The ''regular expression'' that determines which case is executed. Since this is a ''regular expression'', metacharacters such as {{code|*}} and {{code|()}} will need to have backslashes in front of them if you want to match them literally.}}
   {{param|case|A potential match for the {{code|expression}}, possesses a corresponding  {{code|body}} that is executed if a match is made.}}
   {{param|default|If the {{code|expression}} finds no matches within the {{code|case}}s, then the {{code|defaultBody}} is executed.}}
   '''Notes''' 
   * the {{code|case}} and {{code|default}} statements are the only case-sensitive statements in MapTool, thus {{code|CASE}} or {{code|Default}} will NOT work!
   * strings in the {{code|case}} MUST be surrounded by "double quotes" as 'single quotes' will generate an error.

   |examples=
   <source lang="mtmacro" line>
   [h:powerType="at-will"]
   [switch(powerType):
   case "at-will": "You may use this power as much as you like";
   case "encounter": "You may only use this power once per encounter";
   case "daily": "You may only use this power once per day"]
   </source>
   Outputs:
    You may use this power as much as you like


   <source lang="mtmacro" line>
   [h:powerType=".*sword.*"]
   [switch(powerType):
   case "flail": "one-handed weapon; two-handed does Str*2 damage";
   case "shortsword": "used for jabs, so is a puncturing weapon";
   case "longsword": "a slashing weapon"]
   </source>
   Outputs:
    used for jabs, so is a puncturing weapon
   Notice that the first matching clause was the one that the {{roll|switch}} option found.

   another example
   <source lang="mtmacro" line>
   [abort(input("number|0|enter a number"))]
   [switch(number):
       case 0: "you did not enter a number";
       case 1: "you entered 1 as a number";
       case 2: "you entered 2 as a number";
       default: "you entered a number not equal to 1 or 2"
   ]
   </source>

   When using the {{roll|code}} option with a {{code|switch}} option, each {{code|case}} body has its own set of braces, like so:
   <source lang="mtmacro" line>
   [h,switch(class),code:
   case "Warrior": {
     [Armor = 6]
     [beginningPowers = "Sword, Shield Bash, Bow, Shield, Torch"]
   };
   case "Rogue": {
     [Armor = 2]
     [beginningPowers = "Dagger, Hide, Backstab, Pick Lock, Torch"]
   };
   case "Wizard": {
     [Armor = 1]
     [beginningPowers = "Dagger, Staff, Light, Lightning Bolt, Fire Ball"]
   };
   case "Priest": {
     [Armor = 4]
     [beginningPowers = "Mace, Heal, Protect, Banish Undead, Torch"]
   };
   default: {
     [Armor = 0]
     [beginningPowers = "Fists, Feet"]
   }]
   </source>

   |also=
   {{func|if}}, 
   {{roll|if}},
   [[Introduction_to_Macro_Branching|Introduction to Macro Branching]]
   }}

`Category:Branching Roll Option <Category:Branching_Roll_Option>`__
