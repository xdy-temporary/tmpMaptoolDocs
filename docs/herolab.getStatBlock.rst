.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=herolab.getStatBlock
   |trusted=true
   |version=1.5
   |description=
   Returns associated statblock for the token as a string. Currently, Hero Lab stores three types of statblocks: Text, HTML, & XML.

   |usage=
   <source lang="mtmacro" line>
   herolab.getStatBlock(type)
   herolab.getStatBlock(type,id)
   </source>
   Note: The different formats may or may not contain the same information but it does reflects what is stored in the portfolio. If you find missing information, in the XML statblock for instance, you will need to report that to [http://www.wolflair.com/index.php?context=hero_lab&page=support Wolf Lair].

   '''Parameters'''
   {{param|type|A string containing either "text", "html", or "xml"}}
   {{param|id|The ID of the token. Defaults to the Current Token.}}

   Returns ''HeroLab data does not exist for this token'' if no data exists for the token and aborts the macro.

   |example=
   Get the Hero Lab Master character name associated with the current token.
   <source lang="mtmacro" line>
   [herolab.getStatBlock("text")]
   </source>
   Returns:
   <source lang="mtmacro" line>
   </source>

   |also=
   [[Hero_Lab_Integration|Hero Lab Integration]]

   |changes=
   * '''1.5''' - Added to main MapTool build.
   }}

`Category:Hero Lab Function <Category:Hero_Lab_Function>`__
