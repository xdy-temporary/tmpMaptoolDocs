==========================
macroLinkText - MapToolDoc
==========================

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

   .. rubric:: macroLinkText
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

            -  `1 macroLinkText()
               Function <#macroLinkText.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: macroLinkText() Function
            :name: macrolinktext-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Creates the text that would appear in a HTML tag for a link
            which will run the specified macro when clicked on. This is
            useful for callbacks in
            `[dialog():] </rptools/wiki/dialog_(roll_option)>`__ or
            `[frame():] </rptools/wiki/frame_(roll_option)>`__. If you
            just want to send a click-able link to someone use
            `macroLink() </rptools/wiki/macroLink>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     macroLinkText(macroName)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     macroLinkText(macroName, output)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     macroLinkText(macroName, output, args)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     macroLinkText(macroName, output, args, target)

         **Parameters**

         -  ``macroName`` - The name of the macro to run when the link
            is clicked. The ``macroName`` is in the standard macro
            reference format (e.g. ``Macro@Lib:Token``)
         -  ``output`` - Who the output of the macro should go to,
            values are (defaults to ``none``):

            -  ``self`` - Display only to person who clicked on the
               link.
            -  ``gm`` - Display to GM.
            -  ``all`` - Everyone (acts like a ``/say``)
            -  ``none`` - Discard any output.
            -  ``gm-self`` - Display to GM and the person executing the
               link.
            -  ``list`` - Displays to a list of players. When the
               ``output`` parameter is ``"list"`` then the macro link
               expects the ``args`` parameter to be a `JSON
               Object </rptools/wiki/JSON_Object>`__, that contains a
               field called ``mlOutputList`` which is a `JSON
               Array </rptools/wiki/JSON_Array>`__ containing the
               players to send the output to.

         -  ``args`` - Any arguments to be passed to the macro when it
            is called.
         -  ``target`` - Which tokens to run the macro on. Target can be
            one or more of the following separated by commas (defaults
            to ``impersonated``):

            -  ``impersonated`` - The impersonated
               `Token </rptools/wiki/Token>`__.
            -  ``selected`` - The selected
               `Token </rptools/wiki/Token>`__/s.
            -  `Token
               ID </maptool/index.php?title=Token_ID&action=edit&redlink=1>`__
               - The ``id`` of a `Token </rptools/wiki/Token>`__.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            To create the text that would go inside a form element as
            the ``action`` attribute, and that will call a macro named
            ``Test`` on the `Library
            Token </rptools/wiki/Library_Token>`__ named ``Lib:Test``:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [r: macroLinkText("Test@Lib:Test","", "gm")]

            Returns: ``macro://Test@Lib:Test/gm/impersonated?``

            To create the text that would go inside a form element as
            the ``action`` attribute and call the ``AddWeapon`` on the
            `Library Token </rptools/wiki/Library_Token>`__ named
            ``Lib:PC`` which will act upon the `Current
            Token </rptools/wiki/Current_Token>`__:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [r:macroLinkText('AddWeapon@Lib:PC', 'none', '', currentToken())]

            Returns: ``macro://AddWeapon@Lib:PC/none/#ID#?`` where
            ``#ID#`` is the ``id`` of the `Current
            Token </rptools/wiki/Current_Token>`__.

            Sending to multiple players and the GM in 1.3b55

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [h: outputTo = '["Fred", "Barney", "gm"]']

                  #. .. code:: de1

                        [h: args = json.set("{}", "mlOutputList", outputTo)]

                  #. .. code:: de1

                        [r: macroLinkText("Click on me!", "Test@Lib:Test", "list", args)]

            Correctly modifying the colour of the link, works both in
            the chat box and in forms:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [r: strformat('<a style="color:red" href="%s">Click Me</a>', macroLinkText("Click Me Macro@Lib:Test"))]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `macroLink() </rptools/wiki/macroLink>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b55** - Added ``gm-self`` and ``list`` output
               options.
            -  **1.3b56** - Links created using this function will no
               longer show a tooltip when displayed in a dialog or
               frame.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=macroLinkText&oldid=5798"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `Macro
               Function </rptools/wiki/Category:Macro_Function>`__
            -  `Miscellaneous
               Function </rptools/wiki/Category:Miscellaneous_Function>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__
         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__ >
         `Miscellaneous
         Function </rptools/wiki/Category:Miscellaneous_Function>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=macroLinkText>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/macroLinkText>`__
            -  `Discussion </maptool/index.php?title=Talk:macroLinkText&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/macroLinkText>`__
            -  `View
               source </maptool/index.php?title=macroLinkText&action=edit>`__
            -  `View
               history </maptool/index.php?title=macroLinkText&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/macroLinkText>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/macroLinkText>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=macroLinkText&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=macroLinkText&oldid=5798>`__
            -  `Page
               information </maptool/index.php?title=macroLinkText&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 4 November 2011, at 06:05.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
