.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=herolab.XPath
   |trusted=true
   |version=1.5.0
   |description=
   Returns data results based on the passed in XPath expression from the XML statblock. This is a reliable and easier way to get stat data from a character than using regular expression parsing of Text stat blocks.
   |usage=
   <source lang="mtmacro" line>
   herolab.XPath(XPath)
   herolab.XPath(XPath, id)
   </source>

   '''Parameters'''
   {{param|XPath|The XPath expression to evaluate against the XML statblock.}}
   {{param|id|The id of the token. Defaults to the Current Token.}}

   Returns the requested data.

   |example=
   Get various values from Hero Lab data (which is in XML).
   <source lang="mtmacro" line>
   [race = herolab.XPath('/document/public/character/race/@name')]
   [alignment = herolab.XPath('/document/public/character/alignment/@name')]
   [improvedInit = herolab.XPath('boolean(/document/public/character/feats/feat[starts-with(@name,"Improved Initiative")])')]
   </source>
   Returns:
   <source lang="mtmacro">
   Human Neutral Good 1
   </source>

   |also=
   [[Hero_Lab_Integration|Hero Lab Integration]]
   }}

`Category:Hero Lab Function <Category:Hero_Lab_Function>`__
