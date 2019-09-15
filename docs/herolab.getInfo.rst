.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=herolab.getInfo
   |trusted=true
   |version=1.5
   |description=
   Get basic information about the Hero Lab data associated with this token. Returns a JSON object containing various metadata about the character.

   |usage=
   <source lang="mtmacro" line>
   herolab.getInfo(id)
   herolab.getInfo(id,field)
   </source>

   '''Parameters'''
   {{param|id|The token id of the token to name, defaults to the Current Token.}}
   {{param|field|A particular field from the metadata.}}

   |example=
   Get the Hero Lab data associated with the current token.
   <source lang="mtmacro" line>
   [herolab.getInfo()]
   </source>
   Returns:
   <source lang="javascript" line>
   {
       "summary": "Young red dragon - CE Large dragon",
       "masterIndex": null,
       "isAlly": false,
       "images": ["asset://8799bd3b26bc614cf0a0f33675f5e77d", "asset://80b3ea5b47f5f1c7aec06a28219cde47"],
       "portfolioPath": "C:\\Users\\John\\Documents\\Pathfinder\\Giantslayer\\Episode 5 tokens\\",
       "playerName": "Joe",
       "isMinion": false,
       "portfolioFile": "C:\\Users\\John\\Documents\\Pathfinder\\Giantslayer\\Episode 5 tokens\\Part 3 GS 5.por",
       "gameSystem": "Pathfinder Roleplaying Game",
       "heroLabIndex": "11",
       "isDirty": true,
       "name": "Young Red Dragon #3",
       "lastModified": "Fri Nov 02 16:28:33 CDT 2018",
       "masterName": ""
   }</source>
   Get the status of the {{code|isMinion}} field from the Hero Lab data for the token named ''Orc 23''.
   <source lang="mtmacro" line>
   [r: isMinion = herolab.getInfo("Orc 23","isMinion")]
   </source>
   Returns:
   <source lang="mtmacro" line>
   1
   </source>

   |also=
   [[Hero_Lab_Integration|Hero Lab Integration]]

   |changes=
   * '''1.5''' - Added to main MapTool build.
   }}

`Category:Hero Lab Function <Category:Hero_Lab_Function>`__
