.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getGroupCount
   |version=1.3b48
   |description=Returns the number of capture groups for the match performed by [[strfind|strfind()]].

   |usage=
   <source lang="mtmacro" line>
   [h: text = getGroupCount(id)]
   </source>
   id is the id returned by [[strfind|strfind()]]
   |example=
   <source lang="mtmacro" line>
   [h: id = strfind("this is a test", "(\\S+)\\s(\\S+)\\s*")]
   [r: getGroupCount(id)]
   </source>
   Returns 2.
   }}

`Category:String Function <Category:String_Function>`__
