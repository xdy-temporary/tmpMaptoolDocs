==============================
Macros:Roll:types - MapToolDoc
==============================

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

   .. rubric:: Macros:Roll:types
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

         .. container:: template_languages

            Languages:  English
             • \ `日本語 </rptools/wiki/Macros:Roll:types/ja>`__\ 

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 []/{} Roll Types and
               Options <#.5B.5D.2F.7B.7D_Roll_Types_and_Options>`__

               -  `1.1 { } Rolls <#.7B_.7D_Rolls>`__
               -  `1.2 [ ] Rolls <#.5B_.5D_Rolls>`__
               -  `1.3 [ ] Hidden Rolls <#.5B_.5D_Hidden_Rolls>`__
               -  `1.4 [ ] Expanded Rolls <#.5B_.5D_Expanded_Rolls>`__
               -  `1.5 [ ] Result Rolls <#.5B_.5D_Result_Rolls>`__
               -  `1.6 [ ] Unformatted
                  Rolls <#.5B_.5D_Unformatted_Rolls>`__
               -  `1.7 [ ] Tool Tip Rolls <#.5B_.5D_Tool_Tip_Rolls>`__

            -  `2 Related Pages <#Related_Pages>`__

         .. rubric:: []/{} Roll Types and Options
            :name: roll-types-and-options

         Text that you type into MapTool or execute from a `macro
         button </rptools/wiki/Macro_Button>`__ is scanned for [ ] and {
         } blocks. The text within these blocks is evaluated and the
         output from this evaluation is placed into the string in its
         place.

         .. rubric:: { } Rolls
            :name: rolls

         When the text is contained within { } then the text is
         evaluated and the output copied in its place without any
         special formatting. For example {2 + 2} produces
         |Brace2Plus2.png|

         .. rubric:: [ ] Rolls
            :name: rolls-1

         Text that is within [ ] is evaluated, the output from [ ] is
         inserted with a tool tip that displays the details of the
         evaluation -- the tool tip can be displayed by leaving the
         mouse pointer over the result. For example [2 + 2] produces

         |2Plus2ToolTip.png|

         There are also several options that can be used within [ ] to
         change the formatting. Options are specified after the [ and
         the option string is terminated with a ':'. If you have more
         than one option then need to separate them with a ',' eg [opt1,
         opt2: ...], if there are any arguments for an option they are
         enclosed within (). All options are case insensitive, so [opt:
         ...] is the same [OPT: ...].

         .. rubric:: [ ] Hidden Rolls
            :name: hidden-rolls

         **[h: ]**, **[hide: ]**, **[hidden: ]** evaluates the text
         after the ':' but completely discards the output. This is
         useful for setting variables or other similar tasks where you
         want to change something but not display any output.

         If a chat message would appear empty because everything in it
         is hidden from the player, the message is not displayed.

         .. rubric:: [ ] Expanded Rolls
            :name: expanded-rolls

         **[e: ]**, **[expanded: ]** evaluates the text after the ':'
         and displays the detailed output of the evaluation. [e: 2 + 2 ]
         would display.

         | 
         | |2Plus2Expanded.png|

         | 

         .. rubric:: [ ] Result Rolls
            :name: result-rolls

         **[r: ]**, **[result: ]** evaluates the text after the ':' and
         displays the plain output without any formatting or tool tips,
         the result is the same as using { }. [r: 2 + 2] would display.

         |2Plus2Result.png|

         | 

         .. rubric:: [ ] Unformatted Rolls
            :name: unformatted-rolls

         **[u: ]**, **[unformatted: ]** evaluates the text after the ':'
         and displays the detailed output without coloring or tool tips.
         [u: 2 + 2 ] would display.

         |2Plus2Unformatted.png|

         | 

         .. rubric:: [ ] Tool Tip Rolls
            :name: tool-tip-rolls

         **[t: ]**, **[tooltip: ]** evaluates the text after the ':' and
         displays the result with a tool tip that displays the details
         of the evaluation -- the tool tip can be displayed by leaving
         the mouse pointer over the result. For example [t: 2 + 2]
         produces.

         |2Plus2T.png|

         You can also specify an argument for the tooltip option. If you
         specify an argument then this argument is evaluated and
         displayed, the text after the ':' is evaluated and used as the
         tool tip. [t("four"): 2 + 2] produces.

         |2Plus2T-Four.png|

         .. rubric:: Related Pages
            :name: related-pages

         -  `Dice Expressions </rptools/wiki/Dice_Expressions>`__
         -  `Roll Visibility
            Options </rptools/wiki/Macros:Roll:output>`__
         -  `Branching and Looping Roll
            Options </rptools/wiki/Macros:Branching_and_Looping>`__

         .. container:: template_languages

            Languages:  English
             • \ `日本語 </rptools/wiki/Macros:Roll:types/ja>`__\ 

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Macros:Roll:types&oldid=5588"

      .. container:: catlinks catlinks-allhidden
         :name: catlinks

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
            in </maptool/index.php?title=Special:UserLogin&returnto=Macros%3ARoll%3Atypes>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/Macros:Roll:types>`__
            -  `Discussion </maptool/index.php?title=Talk:Macros:Roll:types&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/Macros:Roll:types>`__
            -  `View
               source </maptool/index.php?title=Macros:Roll:types&action=edit>`__
            -  `View
               history </maptool/index.php?title=Macros:Roll:types&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/Macros:Roll:types>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/Macros:Roll:types>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=Macros:Roll:types&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=Macros:Roll:types&oldid=5588>`__
            -  `Page
               information </maptool/index.php?title=Macros:Roll:types&action=info>`__

      .. container:: portal
         :name: p-lang

         .. rubric:: In other languages
            :name: p-lang-label

         .. container:: body

            -  `日本語 <http://lmwcs.com/rptools/wiki/Macros:Roll:types/ja>`__

.. container::
   :name: footer

   -  This page was last modified on 19 July 2011, at 15:24.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Brace2Plus2.png| image:: /maptool/images/7/75/Brace2Plus2.png
   :width: 332px
   :height: 87px
   :target: /rptools/wiki/File:Brace2Plus2.png
.. |2Plus2ToolTip.png| image:: /maptool/images/1/14/2Plus2ToolTip.png
   :width: 332px
   :height: 87px
   :target: /rptools/wiki/File:2Plus2ToolTip.png
.. |2Plus2Expanded.png| image:: /maptool/images/2/2b/2Plus2Expanded.png
   :width: 332px
   :height: 87px
   :target: /rptools/wiki/File:2Plus2Expanded.png
.. |2Plus2Result.png| image:: /maptool/images/9/96/2Plus2Result.png
   :width: 332px
   :height: 87px
   :target: /rptools/wiki/File:2Plus2Result.png
.. |2Plus2Unformatted.png| image:: /maptool/images/b/b1/2Plus2Unformatted.png
   :width: 332px
   :height: 87px
   :target: /rptools/wiki/File:2Plus2Unformatted.png
.. |2Plus2T.png| image:: /maptool/images/a/ac/2Plus2T.png
   :width: 332px
   :height: 87px
   :target: /rptools/wiki/File:2Plus2T.png
.. |2Plus2T-Four.png| image:: /maptool/images/9/90/2Plus2T-Four.png
   :width: 332px
   :height: 87px
   :target: /rptools/wiki/File:2Plus2T-Four.png
.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
