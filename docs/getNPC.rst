.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getNPC
   |trusted=true
   |version=1.3b48
   |description=Returns a list containing the ids of the [[NPC_Token|NPC token]]s on the current [[Map|map]]. The type of the value returned depends on the delimiter parameter. 
   * If the delimiter is not specified then a [[String_List{{!}}

string_list|String List{{!}}string list]] is returned with the default
value of is used.

-  If the delimiter then a `json array <JSON_Array>`__ is returned.
-  Otherwise a `string list <Macros:string_list>`__ is returned with the
   delimiter passed in.

 

\|usage=

.. code:: mtmacro
   :number-lines:

   getNPC()
   getNPC(delim)

delim is the delimiter used to separate the values in the `string
list <Macros:string_list>`__ which defaults to if not specified.

\|example= To display the ids of all of the `NPC
tokens <Token:NPC_token>`__ on the current `map <Map:map>`__ use.

.. code:: mtmacro
   :number-lines:

   [h: ids = getNPC()]
   [foreach(id, ids, "<br>"): id]

\|changes=

-  **1.3b49** - Added delimiter option.

\|also= }}

`Category:Find Function <Category:Find_Function>`__
