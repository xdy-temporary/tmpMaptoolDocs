=========================================
Working With Two CODE Levels - MapToolDoc
=========================================

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

   .. rubric:: Working With Two CODE Levels
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

            -  `1 Working With Two CODE
               Levels <#Working_With_Two_CODE_Levels>`__

               -  `1.1 So what to do when you do need to go
                  deeper? <#So_what_to_do_when_you_do_need_to_go_deeper.3F>`__

                  -  `1.1.1 Trick 1: Create another
                     UDF <#Trick_1:_Create_another_UDF>`__
                  -  `1.1.2 Trick 2: Code
                     smarter <#Trick_2:_Code_smarter>`__
                  -  `1.1.3 Trick 3: Store
                     commands <#Trick_3:_Store_commands>`__
                  -  `1.1.4 Trick 4: More than 2 CODE
                     levels <#Trick_4:_More_than_2_CODE_levels>`__

         .. rubric:: Working With Two CODE Levels
            :name: working-with-two-code-levels

         One of the biggest limitations of the MT macro script is that
         the script parser can't handle more that 2 levels of ``{}``. So
         this will work:

         ::

             [If(condition), CODE:{
               [if(another_condition), CODE:{
                  [code to execute when true]
               };{}]
             };{}]

         And this won't:

         ::

             [If(condition), CODE:{
               [if(another_condition), CODE:{
                 [if(another_condition), CODE:{
                   [code to execute when true]
                 };{}]
               };{}]
             };{}]

         -  Note that this is an example, there are other occasions
            where one uses ``{}``, e.g. ``{myVar}`` instead of
            ``[r:myVar]``. This is subject to the same problem. The only
            exception I've encountered is with json objects:
            ``myVar = json.set("{}", "someKey", someVar)``. This is NOT
            subject to this problem. However I believe that if you use
            ``'{}'`` instead of ``"{}"`` it won't work (or the other way
            around).

         .. rubric:: So what to do when you do need to go deeper?
            :name: so-what-to-do-when-you-do-need-to-go-deeper

         Basically there are 3 general tricks you can use if you need to
         go deeper:

         .. rubric:: Trick 1: Create another UDF
            :name: trick-1-create-another-udf

         One of the most common *tricks* is to create a User Defined
         Function (UDF) and call this in the nested level. Within this
         UDF you can yet again go 2 CODE levels deep.

         .. rubric:: Trick 2: Code smarter
            :name: trick-2-code-smarter

         Many many examples can be given here, but you can achieve a lot
         by using roll options e.g.:

         ::

             [if(condition): if(another_condition, "show this", "else show this"); if(yet_another_condition, "show this"; "else show this")]

         You can also work with multiple roll options, but this *should*
         not work, but does sometimes work e.g.:

         ::

             [foreach(item,items), if(item == someVar), CODE:{};{}]

         works while:

         ::

             [if(listCount(items)>2), foreach(item,items), CODE:{};{}]

         won't work.

         A lot can be achieved by restructuring your code in this
         manner.

         .. rubric:: Trick 3: Store commands
            :name: trick-3-store-commands

         One final trick I recently learned from Ahzrei is a rather
         dirty trick but can be used in certain circumstances. In my
         case I have code that needs to be executed that is already two
         levels deep and then I ALSO want to execute this for certain
         selected tokens. In this case you can first store the
         to-execute-commands in a json object and then exit the two
         loops. Now you have a json object containing all code that
         needs to be executed onto certain tokens. For this you can
         start a new loop that uses
         `json.evaluate() </rptools/wiki/json.evaluate>`__ per json
         object per token id.

         .. container:: template_clarify

            | **Needs Clarification:**
            | (need to add example later on)

         .. rubric:: Trick 4: More than 2 CODE levels
            :name: trick-4-more-than-2-code-levels

         Officially this is NOT supported in MT and thus it *could*
         break your code if improperly used. That said, I've been using
         this trick for 6 (dd: 2017) years now and my code is flooded
         with it and have not yet encountered any issue, so its
         reasonable to assume that its safe to use. Disclaimer: Still
         this is at your own risk.

         As it turns out it IS possible to have more then 2 nested code
         levels but in order to do that you have to *mislead* the
         parser. This is done as follows:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [if(1), CODE:{

               #. .. code:: de1

                        [if(1), CODE:{

               #. .. code:: de1

                          [if(1), CODE:{

               #. .. code:: de1

                                    you should never see this in the chat...but you do!

               #. .. code:: de2

                           ''

               #. .. code:: de1

                             };{''}]

               #. .. code:: de1

                       ''

               #. .. code:: de1

                       };{''}]

               #. .. code:: de1

                     ''

               #. .. code:: de2

                     };{''}]

         Important notes:

         -  put the ``''`` in the ELSE statements as well when they're
            not empty.
         -  do NOT use the single quote ``'`` anywhere in the nested
            code!! It \*can\* be used, but it \*can\* also lead to
            errors! I've not been able to determine when it goes right
            and when wrong, so to be safe: don't use them.
         -  if you use multiple embedded if(),code statements, make sure
            that you use add the else: {} part as well (like in the
            above example), even if its empty. Due to this 'hack' its
            possible that if not all elses are given but some are that
            the an else is used of an embedded if statement instead of
            the one intended!!

         What it boils down to is to add two single quotes ``''`` at the
         END of EACH code block. This will fool the MT parser and it
         will accept this nesting. I've tried it upto 9 nestings without
         a problem (more is probly also no issue). Do keep in mind that
         this will SERIOUSLY impact the stack though, so don't go
         writing huge code blocks this way. I mainly use it for cases
         where you only have a few lines of code but are required to go
         3 or 4 nestings deep and its just annoying to create a separate
         macro for one or two lines of code.

         Note that if in the above example the ``''`` will show up in
         the chat. You can also use ``[h:'']`` instead to prevent this.

         --`Wolph42 </rptools/wiki/User:Wolph42>`__ 16:22, 19 March 2011
         (UTC)

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Working_With_Two_CODE_Levels&oldid=6968"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `Clarify </rptools/wiki/Category:Clarify>`__
            -  `Cookbook </rptools/wiki/Category:Cookbook>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ >
         `Cookbook </rptools/wiki/Category:Cookbook>`__
         `Review </rptools/wiki/Category:Review>`__ >
         `Clarify </rptools/wiki/Category:Clarify>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=Working+With+Two+CODE+Levels>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/Working_With_Two_CODE_Levels>`__
            -  `Discussion </maptool/index.php?title=Talk:Working_With_Two_CODE_Levels&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/Working_With_Two_CODE_Levels>`__
            -  `View
               source </maptool/index.php?title=Working_With_Two_CODE_Levels&action=edit>`__
            -  `View
               history </maptool/index.php?title=Working_With_Two_CODE_Levels&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/Working_With_Two_CODE_Levels>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/Working_With_Two_CODE_Levels>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=Working_With_Two_CODE_Levels&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=Working_With_Two_CODE_Levels&oldid=6968>`__
            -  `Page
               information </maptool/index.php?title=Working_With_Two_CODE_Levels&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 9 July 2018, at 08:25.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
