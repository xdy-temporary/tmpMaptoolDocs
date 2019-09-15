.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getNPCNames
   |trusted=true
   |version=1.3b48
   |description=Returns a list containing the names of the [[NPC_Token{{!}}

NPC_token|NPC Token{{!}}NPC token]]s on the current
`Map{{!}}map <Map{{!}}map>`__. The type of the value returned depends on
the delimiter parameter.

-  If the delimiter is not specified then a `String List{{!}}string
   list <String_List{{!}}string_list>`__ is returned with the default
   value of is used.
-  If the delimiter then a `JSON Array <JSON_Array>`__ is returned.
-  Otherwise a `String List{{!}}string
   list <String_List{{!}}string_list>`__ is returned with the delimiter
   passed in.

 

\|usage=

.. code:: mtmacro
   :number-lines:

   [h: macros = getNPCNames()]
   [h: macros = getNPCNames(delim)]

.. raw:: mediawiki

   {{code|delim}}

is the delimiter used to separate the values in the `String
List{{!}}string list <String_List{{!}}string_list>`__ which defaults to
if not specified.

\|example= To display the names of all of the `NPC Token{{!}}NPC
tokens <NPC_Token{{!}}NPC_token>`__ on the current
`Map:map{{!}}map <Map:map{{!}}map>`__ use.

.. code:: mtmacro
   :number-lines:

   [h: names = getNPCNames()]
   [foreach(name, names, "<br>"): name]

\|changes=

-  **1.3b49** - Added delimiter option.

\|also= }}

`Category:Find Function <Category:Find_Function>`__
