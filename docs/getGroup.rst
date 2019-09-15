=====================
getGroup - MapToolDoc
=====================

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

   .. rubric:: getGroup
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

         .. rubric:: getGroup() Function
            :name: getgroup-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Returns the specified capture group for the specified match
            that was found using `strfind() <strfind>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getGroup(id, match, group)

         Where

         -  ``id`` - is the id returned by
            `strfind() <strfind>`__
         -  ``match`` - is the number of the match found by
            `strfind() <strfind>`__
         -  ``group`` - is the number of the capture group found by
            `strfind() <strfind>`__

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: id = strfind("this is a test", "(\\S+)\\s(\\S+)\\s*")]

                  #. .. code-block:: none

                        match 1, group 0 = [getGroup(id, 1, 0)]<br>

                  #. .. code-block:: none

                        match 1, group 1 = [getGroup(id, 1, 1)]<br>

                  #. .. code-block:: none

                        match 1, group 2 = [getGroup(id, 1, 2)]<br>

                  #. .. code:: de2

                        match 2, group 0 = [getGroup(id, 2, 0)]<br>

                  #. .. code-block:: none

                        match 2, group 1 = [getGroup(id, 2, 1)]<br>

                  #. .. code-block:: none

                        match 2, group 2 = [getGroup(id, 2, 2)]<br>

            Returns:

            ::

               match 1, group 0 = this is
               match 1, group 1 = this 
               match 1, group 2 = is 
               match 2, group 0 = a test
               match 2, group 1 = a 
               match 2, group 2 = test 

            **Example explained**

            First off, escapes = "\" are used to let the character in
            question NOT be what it usually is. E.g. "d" is the
            alphabetical character "d"; "\d" however is thus NOT "d" and
            with that it gets a 'regex' meaning, in this case 'digit',
            so 1,2,3,4,5,6,7,8,9 or 0. The same the other way round,
            e.g. "." means "any character" if you actually want to find
            a "." (dot) in the text you thus use \\. so its NOT the
            regex "any character" but just a ".".

            Now the tricky bit: in maptool ALL escapes ("\") are eaten
            by the maptool parser UNLESS they are preceded by an escape
            themselves. This happens BEFORE the regex is parsed by the
            regex parser. THUS ALL ESCAPES MUST BE ESCAPED !! So in the
            above examples "\d" becomes "\\d" and "\." becomes "\\.".
            Really tricky it becomes when you want to find the "\"
            character. This is a regex symbol hence it needs to be
            escaped: "\\" but as its in maptool every escape must be
            escaped so it ultimately becomes "\\\\" !

            note that alternatively you can use [] ANY character in
            there will be looked at literally (and separately). So \\\.
            == [.]. Obviously here too are exceptions, but read a regex
            tutorial for that.

            So back to the above example:

            -  ``S`` = 'everything that is NOT a whitespace'
            -  ``s`` = 'white-space'
            -  ``+`` = '1 or more'
            -  ``*`` = '0 or more'

            Have a look
            `here <http://www.addedbytes.com/download/regular-expressions-cheat-sheet-v2/png/>`__
            for an overview.

            Second important thing to know is that a group is defined by
            ``'('``\ parenthesis\ ``')'``: ``(group1)(group2)(etc.)``,
            where group ``'0'`` returns the entire "match" result.

            So ``\\S`` means grab the first none-whitespace you
            encounter, ``\\S+`` means grab the first none-whitespace you
            encounter AND ALL characters after that until you encounter
            a whitespace. Hence the regex statement looks for

            ::

                (string of non-whitespace chars) whitespace (string of non-whitespace chars) 0 or more whitespaces

            apply this to the text example and you get:

            ::

                MATCH 1: "(this) (is) " MATCH2: "(a) (code)"

            Hence in this example you have 2 MATCHES: Match 1 and Match
            2 both consists out of 2 GROUPS: Group 1 and Group 2. Note
            that Group 0 will return the ENTIRE match.

            In summary: a search result can have multiple matches, and
            each match can consist out of 1 or more groups:

            -  The first group ``'0'`` returns the ENTIRE match.
            -  Every group after that will return partial matches that
               are within ``()``.

            `Here a link <http://www.gskinner.com/RegExr/>`__ to test
            your regex statements (remember that for this applet you
            only use one ``\`` while in MT you need ``\\``.

            | 
            | **Another Example**

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        <!--

                  #. .. code-block:: none

                           (?i) - case insensative

                  #. .. code-block:: none

                           (d+) - number of dice (not optional)

                  #. .. code-block:: none

                           d - dice expression separator, upper or lower case

                  #. .. code:: de2

                           (d+) - die sides (not optional)

                  #. .. code-block:: none

                           Optional:

                  #. .. code-block:: none

                              space* - space before modifier

                  #. .. code-block:: none

                              ([+-]*d+)* - roll modifier

                  #. .. code-block:: none

                              space* - space after modifier

                  #. .. code:: de2

                              (w+)* - single word for damage type

                  #. .. code-block:: none

                         

                  #. .. code-block:: none

                           Example Groups: "(3)d(6)(+2) (Fire)"

                  #. .. code-block:: none

                        -->

                  #. .. code-block:: none

                        [H: regex = "(?i)(\\d+)d(\\d+) *([+-]*\\d+)* *(\\w+)*"]

                  #. .. code:: de2

                        [H, while(1), code: {

                  #. .. code-block:: none

                           <!-- cancel input to break out of loop -->

                  #. .. code-block:: none

                           [H: abort(input("diceExp|3d6+2 Fire|Enter Dice Expression|TEXT"))]

                  #. .. code-block:: none

                           [H: id = strfind(diceExp,regex)]

                  #. .. code-block:: none

                           [H: valid = getFindCount(id)]

                  #. .. code:: de2

                           [H, if(valid), code: {

                  #. .. code-block:: none

                              [H: numDice = getGroup(id,1,1)]

                  #. .. code-block:: none

                              [H: numSides = getGroup(id,1,2)]

                  #. .. code-block:: none

                              [H: dieMod = getGroup(id,1,3)]

                  #. .. code-block:: none

                              [H: dmgType = getGroup(id,1,4)]

                  #. .. code:: de2

                         

                  #. .. code-block:: none

                              [H: output = strformat("Original: %{diceExp}<br>Dice Expression: %{numDice}d%{numSides}")]

                  #. .. code-block:: none

                              [H, if(! json.isEmpty(dieMod)): output = json.append(output,strformat("Modifier: %{dieMod}"))]

                  #. .. code-block:: none

                              [H, if(! json.isEmpty(dmgType)): output = json.append(output,strformat("Damage Type: %{dmgType}"))]

                  #. .. code-block:: none

                           };{

                  #. .. code:: de2

                              [H: output = strformat("Invalid Dice Expression: [%{diceExp}]")]

                  #. .. code-block:: none

                           }]

                  #. .. code-block:: none

                           [H: broadcast(json.toList(output,"<br>"))]

                  #. .. code-block:: none

                        }]

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getGroup&oldid=6904"

