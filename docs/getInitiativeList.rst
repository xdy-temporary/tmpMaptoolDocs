.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub|more examples.}}

.. raw:: mediawiki

   {{MacroFunction
   |name=getInitiativeList
   |version=1.3b57
   |description=
   Retrieves a list of all tokens currently in the Initiative Panel.  The return value is a JSON object with various information about initiative, including global information (round number, which map is current, which token is current) and token-specific information (token id, initiative value, whether the token is holding or not).

   When called from a [[Trusted_Macro|Trusted Macro]] or by a client with GM authority, it will return all information.  Otherwise it only returns information visible to the current player.  In other words, it respects the Initiative Panel's {{code|Hide NPCs}} and the token's {{code|Visible To Owner Only}} flags, among others.  (This is new in '''1.3b78'''.  Prior versions didn't have the check for trusted context at all.)

   |usage=
   <source lang="mtmacro" line>
   [ json = getInitiativeList() ]
   </source>
   '''Parameters'''
   None.

   |example=
   The following code will simply return a JSON object and print each property name one at a time on separate lines.  Refer to [[JSON_Object|JSON Object]] for more information about JSON object themselves and [[json.get|json.get]] for information on retrieving properties and their values.
   <source lang="mtmacro" line>
   [h: json = getInitiativeList() ]
   [ foreach(item, json, "<br>"): item ]
   </source>

   This example prints a nicely formatted output showing what the contents of the JSON object look like.
   <source lang="mtmacro" line>
   [h: json = getInitiativeList() ]
   <pre>[r: json.indent(json) ]</pre>
   </source>


   |changes=
   {{change|1.3b57|Added macro function.}}
   }}

`Category:Initiative Function <Category:Initiative_Function>`__
