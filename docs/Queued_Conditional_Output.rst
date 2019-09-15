======================================
Queued Conditional Output - MapToolDoc
======================================

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

   .. rubric:: Queued Conditional Output
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

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         | **Requires MapTool 1.3b55**
         | The following is a user defined function that allows you to
           queue output to various recipients. All of the queued output
           is then displayed to the intended recipient/s after the
           completion of the current macro.

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 Usage <#Usage>`__
            -  `2 Notes <#Notes>`__
            -  `3 Macros <#Macros>`__
            -  `4 See Also <#See_Also>`__

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     outputTo(who, what)

         **Parameters:**

         -  ``who`` - Expects a string containing the recipient/s; this
            string can be ``'self'``, ``'gm'``, ``'gm-self'``, or a JSON
            array of player names(e.g. ``'["Bob","Joe"]')``.
         -  ``what`` - Expects a string that contains the output; it is
            sent to the recipient as plain text, so HTML code works as
            intended.

         .. rubric:: Notes
            :name: notes

         -  When sending to a specific list of recipients, the output
            comes across as a whisper; that's just the way it is.
         -  Currently there is no error checking, if you want/need error
            checking, it shouldn't be hard to implement.
         -  There is theoretically no limit to the amount of outputs you
            can queue, but like any software your hardware will impose
            its own limits.

         .. rubric:: Macros
            :name: macros

         Place the following macros all on the same library token(or on
         different library tokens if you know what you're doing and what
         to change).

         --------------

         **onCampaignLoad**

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code:: de1

                  [defineFunction('outputTo', 'outputTo@this')]

         --------------

         --------------

         **outputTo**

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code:: de1

                  [h: toSend = '{}']
                  [h: argTest = json.type(arg(0))]
                  [h, if(argTest=='ARRAY'), code:
                  {
                      [h: toWho = 'list']
                      [h: toSend = json.set(toSend, 'mlOutputList', arg(0))]
                  };{
                      [h: toWho = arg(0)]
                  }]
                  [h: toSend = json.set(toSend, 'toSend', arg(1))]
                  [h: conditionalOutput = macroLinkText('conditionalOutput@this', toWho, toSend)]
                  [h: execLink(conditionalOutput, 1)]

         --------------

         --------------

         **conditionalOutput**

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code:: de1

                  [r: json.get(macro.args, 'toSend')]

         --------------

         .. rubric:: See Also
            :name: see-also

         `macroLinkText </rptools/wiki/macroLinkText>`__,
         `execLink </rptools/wiki/execLink>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Queued_Conditional_Output&oldid=3641"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Category </rptools/wiki/Special:Categories>`__:

            -  `Cookbook </rptools/wiki/Category:Cookbook>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ >
         `Cookbook </rptools/wiki/Category:Cookbook>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=Queued+Conditional+Output>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/Queued_Conditional_Output>`__
            -  `Discussion </maptool/index.php?title=Talk:Queued_Conditional_Output&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/Queued_Conditional_Output>`__
            -  `View
               source </maptool/index.php?title=Queued_Conditional_Output&action=edit>`__
            -  `View
               history </maptool/index.php?title=Queued_Conditional_Output&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/Queued_Conditional_Output>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/Queued_Conditional_Output>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=Queued_Conditional_Output&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=Queued_Conditional_Output&oldid=3641>`__
            -  `Page
               information </maptool/index.php?title=Queued_Conditional_Output&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 7 July 2009, at 14:58.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
