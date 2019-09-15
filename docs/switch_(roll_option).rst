=================================
switch (roll option) - MapToolDoc
=================================

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

   .. rubric:: switch (roll option)
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

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 [switch():] Roll
               Option <#.5Bswitch.28.29:.5D_Roll_Option>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: [switch():] Roll Option
            :name: switch-roll-option

         .. container::

            \* **Introduced in version 1.3b46**

         Chooses among several options and executes code based on the
         expression.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [switch(expression):

               #. .. code:: de1

                        case case1: body1;

               #. .. code:: de1

                        case case2: body2;

               #. .. code:: de1

                        default: defaultBody

               #. .. code:: de2

                     ]

         **Parameters**

         -  ``expression`` - The *regular expression* that determines
            which case is executed. Since this is a *regular
            expression*, metacharacters such as ``*`` and ``()`` will
            need to have backslashes in front of them if you want to
            match them literally.
         -  ``case`` - A potential match for the ``expression``,
            possesses a corresponding ``body`` that is executed if a
            match is made.
         -  ``default`` - If the ``expression`` finds no matches within
            the ``case``\ s, then the ``defaultBody`` is executed.

         **Notes**

         -  the ``case`` and ``default`` statements are the only
            case-sensitive statements in MapTool, thus ``CASE`` or
            ``Default`` will NOT work!
         -  strings in the ``case`` MUST be surrounded by "double
            quotes" as 'single quotes' will generate an error.

         .. rubric:: Examples
            :name: examples

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h:powerType="at-will"]

               #. .. code:: de1

                     [switch(powerType):

               #. .. code:: de1

                     case "at-will": "You may use this power as much as you like";

               #. .. code:: de1

                     case "encounter": "You may only use this power once per encounter";

               #. .. code:: de2

                     case "daily": "You may only use this power once per day"]

         Outputs:

         ::

            You may use this power as much as you like

         | 

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h:powerType=".*sword.*"]

               #. .. code:: de1

                     [switch(powerType):

               #. .. code:: de1

                     case "flail": "one-handed weapon; two-handed does Str*2 damage";

               #. .. code:: de1

                     case "shortsword": "used for jabs, so is a puncturing weapon";

               #. .. code:: de2

                     case "longsword": "a slashing weapon"]

         Outputs:

         ::

            used for jabs, so is a puncturing weapon

         Notice that the first matching clause was the one that the
         **[switch():]** option found.

         another example

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [abort(input("number|0|enter a number"))]

               #. .. code:: de1

                     [switch(number):

               #. .. code:: de1

                        case 0: "you did not enter a number";

               #. .. code:: de1

                       case 1: "you entered 1 as a number";

               #. .. code:: de2

                        case 2: "you entered 2 as a number";

               #. .. code:: de1

                        default: "you entered a number not equal to 1 or 2"

               #. .. code:: de1

                     ]

         When using the `[code():] </rptools/wiki/code_(roll_option)>`__
         option with a ``switch`` option, each ``case`` body has its own
         set of braces, like so:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [h,switch(class),code:

               #. .. code:: de1

                     case "Warrior": {

               #. .. code:: de1

                       [Armor = 6]

               #. .. code:: de1

                       [beginningPowers = "Sword, Shield Bash, Bow, Shield, Torch"]

               #. .. code:: de2

                     };

               #. .. code:: de1

                     case "Rogue": {

               #. .. code:: de1

                       [Armor = 2]

               #. .. code:: de1

                       [beginningPowers = "Dagger, Hide, Backstab, Pick Lock, Torch"]

               #. .. code:: de1

                     };

               #. .. code:: de2

                     case "Wizard": {

               #. .. code:: de1

                       [Armor = 1]

               #. .. code:: de1

                       [beginningPowers = "Dagger, Staff, Light, Lightning Bolt, Fire Ball"]

               #. .. code:: de1

                     };

               #. .. code:: de1

                     case "Priest": {

               #. .. code:: de2

                       [Armor = 4]

               #. .. code:: de1

                       [beginningPowers = "Mace, Heal, Protect, Banish Undead, Torch"]

               #. .. code:: de1

                     };

               #. .. code:: de1

                     default: {

               #. .. code:: de1

                       [Armor = 0]

               #. .. code:: de2

                       [beginningPowers = "Fists, Feet"]

               #. .. code:: de1

                     }]

         .. rubric:: See Also
            :name: see-also

         `if() </rptools/wiki/if>`__,
         `[if():] </rptools/wiki/if_(roll_option)>`__, `Introduction to
         Macro
         Branching </rptools/wiki/Introduction_to_Macro_Branching>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=switch_(roll_option)&oldid=6200"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `Roll Option </rptools/wiki/Category:Roll_Option>`__
            -  `Branching Roll
               Option </rptools/wiki/Category:Branching_Roll_Option>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Roll
         Option </rptools/wiki/Category:Roll_Option>`__
         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Roll
         Option </rptools/wiki/Category:Roll_Option>`__ > `Branching
         Roll Option </rptools/wiki/Category:Branching_Roll_Option>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=switch+%28roll+option%29>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/switch_(roll_option)>`__
            -  `Discussion </maptool/index.php?title=Talk:switch_(roll_option)&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/switch_(roll_option)>`__
            -  `View
               source </maptool/index.php?title=switch_(roll_option)&action=edit>`__
            -  `View
               history </maptool/index.php?title=switch_(roll_option)&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/switch_(roll_option)>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/switch_(roll_option)>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=switch_(roll_option)&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=switch_(roll_option)&oldid=6200>`__
            -  `Page
               information </maptool/index.php?title=switch_(roll_option)&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 24 September 2013, at 10:34.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
