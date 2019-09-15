=============================
Dice Expressions - MapToolDoc
=============================

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

   .. rubric:: Dice Expressions
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

         MapTool's chat window and macro system supports several of the
         most common dice expressions based on the formats **XdY** and
         **dY**.

         In the tables below, the variable *Y* is described as the
         "number of sides" on the dice being rolled; in reality the dice
         roller is picking a random number between 1 and *Y*. The end
         result is the same.

         Additionally, in the expressions, capital letters signify an
         argument you must provide, while the lower-case letters are a
         fixed part of the dice expression. For example, in the
         expression **XdYsS**, you replace *X*, *Y*, and *S* with
         numbers to indicate the number of dice, how many sides the dice
         have, and what number indicates a success, respectively. The
         lower case "d" and "s" are left alone. Also, only one
         expression may be used at a time. For example, you could not
         combine the expressions of dropping low dice and keeping high
         dice.

         Finally, note that when entering a dice roll directly in chat,
         you need to use the /roll `Chat
         Command </rptools/wiki/Chat:Commands>`__ to execute the roll.
         In a macro, you would enclose the roll expression in square
         brackets. For example, if you wanted to roll one twenty sided
         die, one six sided die, and add 8 to the result:

         *Directly in chat*:
         ::

            /roll 1d20+1d6+8

         *In a*\ `macro </rptools/wiki/Macros:introduction>`__:
         ::

            [1d20+1d6+8]

         You may also access these dice expressions directly using macro
         functions, see `Category:Dice
         Function </rptools/wiki/Category:Dice_Function>`__.

         .. rubric:: General Dice Expressions
            :name: general-dice-expressions

         =========== ================= ====================================================================================================================================== ==============================================================================================================================================================================================
         Expression  Function          Description                                                                                                                            Example
         =========== ================= ====================================================================================================================================== ==============================================================================================================================================================================================
         **XdY**                       Roll *X* dice with *Y* sides each. If X is not included, roll 1 die with *Y* sides and present the sum of all rolls in chat            */roll 1d20* rolls one twenty-sided die and presents the total roll in chat
         **XdYdN**   drop              Roll *X* dice with *Y* sides each, and drop the lowest *N* dice afterwards                                                             */roll 4d6d1* rolls four six-sided dice, drops the lowest roll, and presents the total in the chat window
         **XdYkN**   keep              Roll *X* dice with *Y* sides each, and keep the highest *N* dice afterwards                                                            */roll 4d6k3* rolls four six-sided dice, keeps the highest 3 rolls, and presents the total in the chat window
         **XdYrL**   reroll            Roll *X* dice with *Y* sides each, rerolling any results lower than *L*                                                                */roll 3d8r2* rolls three eight-sided dice, repeatedly rerolls any dice that are lower than 2 until all dice rolls are higher than or equal to 2, and then sums and presents the total in chat
         **XdYsT**   success           Roll *X* dice with *Y* sides each, and count any rolls that meet or exceed *T* (the "target number")                                   */roll 4d6s4* rolls four six-sided dice, and counts any individual roll that exceeds four, presenting the number of "successes" in chat
         **XdYe**    explode           Roll *X* dice with *Y* sides each, and reroll any dice that roll *Y*, add the new roll to the total                                    */roll 2d6e* rolls two six-sided dice, and if either rolls a 6, it is rerolled and added to the total (this continues until neither die rolls a 6).
         **XdYesT**  exploding success As success rolls, above, but the individual dice can "explode" (*i.e.*, they are rerolled if they roll their maximum value)            */roll 4d6es8* will roll 4 six-sided dice, explode any that roll their maximum, and then total the rolls that exceed 8
         **XdYo**    open              Roll *X* dice with *Y* sides each, and explode any dice that roll *Y*, then return the value of all rolls, as well as the highest roll */roll 5d6o* rolls 5 six-sided dice, and explodes any that roll 6
         **XdYdhZ**  drop high         Roll *X* dice of *Y* sides, and drop the *Z* highest                                                                                   */roll 5d10DH2* rolls five ten-sided dice, drops the two highest, and presents the total in the chat window
         **XdYklZ**  keep low          Roll *X* dice of *Y* sides, and keep the *Z* lowest                                                                                    */roll 5d6kl3* rolls five six-sided dice, keeping the three lowest, and presents the total in the chat window
         **XdYsZlW** subtract          Roll *X* dice of *Y* sides, subtract *Z* from each roll with a lower bound of *W*                                                      */roll 5d6s1l2* rolls five six-sided dice, subtracting 1 from each with a lower bound of 2, and presents the total in the chat window
         **XdYaZuW** add               Roll *X* dice of *Y* sides, add *Z* to each roll with an upper bound of *W*                                                            */roll 5d6a1u6* rolls five six-sided dice, adding 1 to each with an upper bound of 6, and presents the total in the chat window
         **XdYlZ**   lower bound       Roll *X* dice of *Y* sides, with a lower bound of *Z*                                                                                  */roll 5d6l2* rolls five six-sided dice with a lower bound of 2, and presents the total in the chat window
         **XdYuZ**   upper bound       Roll *X* dice of *Y* sides, with an upper bound of *Z*                                                                                 */roll 5d6u4* rolls five six-sided dice with an upper bound of 4, and presents the total in the chat window
         =========== ================= ====================================================================================================================================== ==============================================================================================================================================================================================

         .. rubric:: Game-Specific Dice Expressions
            :name: game-specific-dice-expressions

         +-----------------+-----------------+-----------------+-----------------+
         | Expression      | Game System     | Function        | Description     |
         +=================+=================+=================+=================+
         | **XdYh**        | Hero            | Stun Dice       | Rolls *X* dice  |
         |                 |                 |                 | with *Y* sides  |
         |                 |                 |                 | each, keeping   |
         |                 |                 |                 | track of the    |
         |                 |                 |                 | results for     |
         |                 |                 |                 | hero rolls for  |
         |                 |                 |                 | body damage.    |
         |                 |                 |                 | Where a roll of |
         |                 |                 |                 | 1 = 0 body      |
         |                 |                 |                 | damage, a roll  |
         |                 |                 |                 | of *Y* = 2 body |
         |                 |                 |                 | damage and a    |
         |                 |                 |                 | roll in between |
         |                 |                 |                 | these two       |
         |                 |                 |                 | values = 1 body |
         |                 |                 |                 | damage.         |
         +-----------------+-----------------+-----------------+-----------------+
         | **XdYb**        | Hero            | Body Dice       | Returns the     |
         |                 |                 |                 | body damage     |
         |                 |                 |                 | from the last   |
         |                 |                 |                 | XdYb Hero Stun  |
         |                 |                 |                 | Dice roll as    |
         |                 |                 |                 | long as *X* and |
         |                 |                 |                 | *Y*             |
         |                 |                 |                 | matches the     |
         |                 |                 |                 | Stun Dice roll  |
         +-----------------+-----------------+-----------------+-----------------+
         | **Xdf**         | Fudge           | Fudge Dice      | Rolls *X*       |
         |                 |                 |                 | `Fudge <http:// |
         |                 |                 |                 | www.fudgerpg.co |
         |                 |                 |                 | m/fudge.html>`_ |
         |                 |                 |                 | _               |
         |                 |                 |                 | dice (which     |
         |                 |                 |                 | return -1, 0,   |
         |                 |                 |                 | or 1), summing  |
         |                 |                 |                 | the dice and    |
         |                 |                 |                 | returning the   |
         |                 |                 |                 | sum             |
         +-----------------+-----------------+-----------------+-----------------+
         | **Xdu**         | Ubiquity        | Ubiquity Dice   | Rolls *X*       |
         |                 |                 |                 | Ubiquity dice,  |
         |                 |                 |                 | which return 0  |
         |                 |                 |                 | or 1, summing   |
         |                 |                 |                 | the result and  |
         |                 |                 |                 | returning that  |
         |                 |                 |                 | value to chat   |
         +-----------------+-----------------+-----------------+-----------------+
         | **Xsr4**        | Shadowrun 4th   | Shadowrun Basic | Roll *X* number |
         |                 | Ed.             | Roll            | of 6 sided      |
         |                 |                 |                 | dice. Output    |
         |                 |                 |                 | the number of   |
         |                 |                 |                 | Hits (Rolls 5   |
         |                 |                 |                 | or above) and   |
         |                 |                 |                 | the numbers of  |
         |                 |                 |                 | Ones rolled. If |
         |                 |                 |                 | the number of   |
         |                 |                 |                 | Ones is half or |
         |                 |                 |                 | more of *X*,    |
         |                 |                 |                 | display         |
         |                 |                 |                 | **Glitch**. If  |
         |                 |                 |                 | the number of   |
         |                 |                 |                 | Ones is half or |
         |                 |                 |                 | more of *X* and |
         |                 |                 |                 | there are no    |
         |                 |                 |                 | Hits, display   |
         |                 |                 |                 | **Critical      |
         |                 |                 |                 | Glitch**.       |
         +-----------------+-----------------+-----------------+-----------------+
         | **Xsr4gT**      | Shadowrun 4th   | Shadowrun       | Roll *X* number |
         |                 | Ed.             | Gremlin Roll    | of 6 sided      |
         |                 |                 |                 | dice. Output    |
         |                 |                 |                 | the number of   |
         |                 |                 |                 | Hits (Rolls 5   |
         |                 |                 |                 | or above) and   |
         |                 |                 |                 | the numbers of  |
         |                 |                 |                 | Ones rolled. If |
         |                 |                 |                 | the number of   |
         |                 |                 |                 | Ones is half or |
         |                 |                 |                 | more of *X*     |
         |                 |                 |                 | minus *T*,      |
         |                 |                 |                 | display         |
         |                 |                 |                 | **Glitch**. If  |
         |                 |                 |                 | the number of   |
         |                 |                 |                 | Ones is half or |
         |                 |                 |                 | more of *X*     |
         |                 |                 |                 | minus *Y* and   |
         |                 |                 |                 | there are no    |
         |                 |                 |                 | Hits, display   |
         |                 |                 |                 | **Critical      |
         |                 |                 |                 | Glitch**.       |
         +-----------------+-----------------+-----------------+-----------------+
         | **Xsr4e**       | Shadowrun 4th   | Shadowrun       | Roll *X* number |
         |                 | Ed.             | Exploding Roll  | of 6 sided      |
         |                 |                 |                 | dice. Output    |
         |                 |                 |                 | the number of   |
         |                 |                 |                 | Hits (Rolls 5   |
         |                 |                 |                 | or above) and   |
         |                 |                 |                 | the numbers of  |
         |                 |                 |                 | Ones rolled.    |
         |                 |                 |                 | Reroll any 6    |
         |                 |                 |                 | adding it to    |
         |                 |                 |                 | the pool. If    |
         |                 |                 |                 | the number of   |
         |                 |                 |                 | Ones is half or |
         |                 |                 |                 | more of *X*,    |
         |                 |                 |                 | display         |
         |                 |                 |                 | **Glitch**. If  |
         |                 |                 |                 | the number of   |
         |                 |                 |                 | Ones is half or |
         |                 |                 |                 | more of *X* and |
         |                 |                 |                 | there are no    |
         |                 |                 |                 | Hits, display   |
         |                 |                 |                 | **Critical      |
         |                 |                 |                 | Glitch**.       |
         +-----------------+-----------------+-----------------+-----------------+
         | **Xsr4egT**     | Shadowrun 4th   | Shadowrun       | Roll *X* number |
         |                 | Ed.             | Exploding       | of 6 sided      |
         |                 |                 | Gremlin Roll    | dice. Output    |
         |                 |                 |                 | the number of   |
         |                 |                 |                 | Hits (Rolls 5   |
         |                 |                 |                 | or above) and   |
         |                 |                 |                 | the numbers of  |
         |                 |                 |                 | Ones rolled.    |
         |                 |                 |                 | Reroll any 6    |
         |                 |                 |                 | adding it to    |
         |                 |                 |                 | the pool. If    |
         |                 |                 |                 | the number of   |
         |                 |                 |                 | Ones is half or |
         |                 |                 |                 | more of *X*     |
         |                 |                 |                 | minus *T*,      |
         |                 |                 |                 | display         |
         |                 |                 |                 | **Glitch**. If  |
         |                 |                 |                 | the number of   |
         |                 |                 |                 | Ones is half or |
         |                 |                 |                 | more of *X*     |
         |                 |                 |                 | minus *T* and   |
         |                 |                 |                 | there are no    |
         |                 |                 |                 | Hits, display   |
         |                 |                 |                 | **Critical      |
         |                 |                 |                 | Glitch**.       |
         +-----------------+-----------------+-----------------+-----------------+
         | **XdYq#+Z**     | DragonQuest     | -               | Rolls *X* dice  |
         |                 |                 |                 | of *Y* sides,   |
         |                 |                 |                 | adding *Z* to   |
         |                 |                 |                 | each die,       |
         |                 |                 |                 | summing the     |
         |                 |                 |                 | result and      |
         |                 |                 |                 | returning that  |
         |                 |                 |                 | value to chat   |
         +-----------------+-----------------+-----------------+-----------------+
         | **XdYq#-Z**     | DragonQuest     | -               | Rolls *X* dice  |
         |                 |                 |                 | of *Y* sides,   |
         |                 |                 |                 | subtracting *Z* |
         |                 |                 |                 | from each die   |
         |                 |                 |                 | with a minimum  |
         |                 |                 |                 | of 1, summing   |
         |                 |                 |                 | the result and  |
         |                 |                 |                 | returning that  |
         |                 |                 |                 | value to chat   |
         +-----------------+-----------------+-----------------+-----------------+

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Dice_Expressions&oldid=7419"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Category </rptools/wiki/Special:Categories>`__:

            -  `MapTool </rptools/wiki/Category:MapTool>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__

      .. container:: visualClear

.. container::
   :name: mw-navigation

   .. rubric:: Navigation menu
      :name: navigation-menu

   .. container::
      :name: mw-head

      .. container::
         :name: p-personal

         .. rubric:: Personal tools
            :name: p-personal-label

         -  `Log
            in </maptool/index.php?title=Special:UserLogin&returnto=Dice+Expressions>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/Dice_Expressions>`__
            -  `Discussion </maptool/index.php?title=Talk:Dice_Expressions&action=edit&redlink=1>`__

         .. container:: vectorMenu emptyPortlet
            :name: p-variants

            .. rubric:: Variants\ ` <#>`__
               :name: p-variants-label

            .. container:: menu

      .. container::
         :name: right-navigation

         .. container:: vectorTabs
            :name: p-views

            .. rubric:: Views
               :name: p-views-label

            -  `Read </rptools/wiki/Dice_Expressions>`__
            -  `View
               source </maptool/index.php?title=Dice_Expressions&action=edit>`__
            -  `View
               history </maptool/index.php?title=Dice_Expressions&action=history>`__

         .. container:: vectorMenu emptyPortlet
            :name: p-cactions

            .. rubric:: More\ ` <#>`__
               :name: p-cactions-label

            .. container:: menu

         .. container::
            :name: p-search

            .. rubric:: Search
               :name: search

            .. container::
               :name: simpleSearch

   .. container::
      :name: mw-panel

      .. container::
         :name: p-logo

         ` </rptools/wiki/Main_Page>`__

      .. container:: portal
         :name: p-navigation

         .. rubric:: Navigation
            :name: p-navigation-label

         .. container:: body

            -  `Main page </rptools/wiki/Main_Page>`__
            -  `Random page </rptools/wiki/Special:Random>`__
            -  `Help <https://www.mediawiki.org/wiki/Special:MyLanguage/Help:Contents>`__

      .. container:: portal
         :name: p-Basic_Usage

         .. rubric:: Basic Usage
            :name: p-Basic_Usage-label

         .. container:: body

            -  `Tutorials </rptools/wiki/Category:Tutorial>`__
            -  `Chat Commands </rptools/wiki/Chat_Commands>`__
            -  `Dice Expressions </rptools/wiki/Dice_Expressions>`__
            -  `Glossary </rptools/wiki/Glossary>`__

      .. container:: portal
         :name: p-Macro_Reference

         .. rubric:: Macro Reference
            :name: p-Macro_Reference-label

         .. container:: body

            -  `List of
               Functions </rptools/wiki/Category:Macro_Function>`__
            -  `Roll Options </rptools/wiki/Category:Roll_Option>`__
            -  `Special
               Variables </rptools/wiki/Category:Special_Variable>`__
            -  `Macro Cookbook </rptools/wiki/Category:Cookbook>`__

      .. container:: portal
         :name: p-Editors

         .. rubric:: Editors
            :name: p-Editors-label

         .. container:: body

            -  `Editor Discussion </rptools/wiki/Editor>`__
            -  `Recent Changes </rptools/wiki/Special:RecentChanges>`__

      .. container:: portal
         :name: p-tb

         .. rubric:: Tools
            :name: p-tb-label

         .. container:: body

            -  `What links
               here </rptools/wiki/Special:WhatLinksHere/Dice_Expressions>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/Dice_Expressions>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=Dice_Expressions&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=Dice_Expressions&oldid=7419>`__
            -  `Page
               information </maptool/index.php?title=Dice_Expressions&action=info>`__

      .. container:: portal
         :name: p-lang

         .. rubric:: In other languages
            :name: p-lang-label

         .. container:: body

            -  `日本語 <http://lmwcs.com/rptools/wiki/Dice_Expressions/ja>`__

.. container::
   :name: footer

   -  This page was last modified on 3 May 2019, at 20:24.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
