.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setOwner
   |version=1.3b48?
   |description=
   Changes the owners of a token (default is the [[Current_Token|Current Token]]) when given a [[String|String]] owner name or [[JSON_Array|JSON Array]] of owner names.  All other owners are removed.

   |usage=
   <source lang="mtmacro" line>
   setOwner(ownerName)
   setOwner(ownerName, id)
   setOwner(ownerName, id, mapname)
   setOwner(ownerNames)
   setOwner(ownerNames, id)
   setOwner(ownerNames, id, mapname)
   </source>
   '''Parameters'''
   {{param|ownerName|The player name to set the ownership on the token.  Ownership is not constrained to the client names currently connected, but only currently connected clients appear in the Token Editor Dialog.  This parameter is a [[String|String]].  An empty string here is treated as an empty JSON array (see next parameter). }}
   {{param|ownerNames|The player names to set the ownership on the token.  Ownership is not constrained to the client names currently connected, but only currently connected clients appear in the Token Editor Dialog.  This parameter is a [[JSON_Array|JSON Array]]. }}
   {{param|id|The token {{code|id}} of the token which has its owners changed, defaults to the [[Current_Token|Current Token]]. {{TrustedParameter}} }}
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}


   |examples=
   To change the [[Owners|owners]] of the [[Current_Token|Current Token]] to a single user use:
   <source lang="mtmacro" line>
   [h: setOwner("Frank")]
   </source>

   To change the [[Owners|owners]] of the [[Current_Token|Current Token]] to a list of three players use:
   <source lang="mtmacro" line>
   [h: setOwner("['Peter', 'Paul', 'Mary']")]
   </source>
   or:
   <source lang="mtmacro" line>
   [h: list = json.append("[]", "Peter", "Paul", "Mary")]
   [h: setOwner(list)]
   </source>

   To make all current players [[Owners|owners]] of the [[Current_Token|Current Token]] use:
   <source lang="mtmacro" line>
   [h: setOwner(getAllPlayerNames("json"))]
   </source>

   To remove all [[Owners|owners]] of the [[Current_Token|Current Token]] use:
   <source lang="mtmacro" line>
   [h: setOwner("")]
   </source>
   or:
   <source lang="mtmacro" line>
   [h: setOwner("[]")]
   </source>

   To display the current [[Owners|owners]] of the [[Current_Token|Current Token]] as checkboxes, then accept the user's changes to apply back onto the token, use the following.  Note that this example does not provide for adding owners to the list, only removing them.  (Adding owners would require the use of {{func|getAllPlayerNames}} and would make this example even more complex.)
   <source lang="mtmacro" line>
   [h: names = getOwners("json")]
   [h: input = "tab0 | OwnerList || TAB"]
   [h: count = 0]
   [h, foreach(name, names), code: {
       [input = input + strformat(" ## ckb_%{count}|1|%{name}|CHECK")]
       [count = count+1]
   } ]
   [h: cancel = input(input)]
   [h: abort(cancel)]
   [h: newOwners = "[]"]
   [h, for(x,0,count):
       newOwners = if(eval("ckb_"+x)==0, newOwners, json.append(newOwners, json.get(names, x))) ]
   [h: setOwner(newOwners)]
   </source>

   |also=
   {{func|isOwnedByAll}},
   {{func|setOwnerOnlyVisible}},
   {{func|isOwner}}.

   |changes=
   {{change|1.3b51|Added {{code|id}} parameter option.}}
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}

   }}

`Category:Token Function <Category:Token_Function>`__
