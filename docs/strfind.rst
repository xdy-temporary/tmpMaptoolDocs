====================
strfind - MapToolDoc
====================

.. contents::
   :depth: 3
..

.. container:: noprint
   :name: mw-page-base

.. container:: noprint
   :name: mw-head-base

.. container:: mw-body
   :name: content

   .. container:: mw-indicators

   .. rubric:: strfind
      :name: firstHeading
      :class: firstHeading

   .. container:: mw-body-content
      :name: bodyContent

      .. container::
         :name: siteSub

         From MapToolDoc

      .. container::
         :name: contentSub

      .. container:: mw-jump
         :name: jump-to-nav

         Jump to: `navigation <#mw-head>`__, `search <#p-search>`__

      .. container:: mw-content-ltr
         :name: mw-content-text

         .. rubric:: strfind() Function
            :name: strfind-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Finds and extracts substrings from a string. ``strfind()``
            is used to match a pattern against an input string and
            extract all of the capture groups. The function returns an
            id which can be used with other functions to extract the
            information. The supplied pattern is a `regular
            expression </rptools/wiki/Macros:regular_expression>`__.
            Functions related to ``strfind()``:

            -  `getFindCount(id) </rptools/wiki/Macros:Functions:getFindCount>`__
            -  `getGroupCount(id) </rptools/wiki/Macros:Functions:getGroupCount>`__
            -  `getGroup(id, matchNo,
               groupNo) </rptools/wiki/Macros:Functions:getGroup>`__
            -  `getGroupStart(id, matchNo,
               groupNo) </rptools/wiki/Macros:Functions:getGroupStart>`__
            -  `getGroupEnd(id, matchNo,
               groupNo) </rptools/wiki/Macros:Functions:getGroupEnd>`__

            Both ``groupNo`` and ``matchNo`` start at 1, the special
            group number ``0`` returns the whole pattern match.

            *Groups* are the regex parts in ``"("`` parenthesis ``")"``,
            so 1 returns the string that matches the first regex
            statement in ``()``, 2 returns the second, etc.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     strfind(str,  pattern)

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                            [h: id = strfind("This is a really useless test", "(\\S+)\\s+(\\S+)\\s*")] 

                  #. .. code-block:: none

                            [r: getGroupCount(id)]

                  #. .. code-block:: none

                            [r: getFindCount(id)] 

                  #. .. code-block:: none

                            [r: getGroup(id, 1, 1)]  

                  #. .. code:: de2

                            [r: getGroup(id, 2, 2)]

            Returns:

            ::

                  2 
                  3 
                  This 
                  really 
                  This is

            | 
            | A slightly more usefull and advanced example:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                     [h:id = strfind("Command-20, Sleight of Hand 10, Knowledge (Arcana) +5", "([^,]*?)\\s?([-+]?\\d+)(,|\$)")]
                     <b>First group</b><br>
                     [r,count(getFindCount(id), "<b>Next group</b><br>"), code: {
                       "[r:getGroup(id, roll.count+1, 0)]" <br>
                         "[r:getGroup(id, roll.count+1, 1)]" <br>
                         "[r:getGroup(id, roll.count+1, 2)]" <br>
                     } ]

            Returns:

            ::

                  First group 
                  "Command-20," 
                  "Command" 
                  "-20" 
                  Next group 
                  " Sleight of Hand 10," 
                  " Sleight of Hand" 
                  "10" 
                  Next group 
                  " Knowledge (Arcana) +5" 
                  " Knowledge (Arcana)" 

            "5"

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=strfind&oldid=5879"

