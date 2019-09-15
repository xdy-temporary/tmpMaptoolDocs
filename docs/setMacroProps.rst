==========================
setMacroProps - MapToolDoc
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

   .. rubric:: setMacroProps
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

         .. container:: template_stub

            | ** This article is a stub, you can help the RPTools Wiki
              project by contributing content to expand this article.**
            | ** This article needs:** *Examples using the new
              functionality.*

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 setMacroProps()
               Function <#setMacroProps.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 Version Changes <#Version_Changes>`__

         .. rubric:: setMacroProps() Function
            :name: setmacroprops-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Sets the properties for the specified `Macro
            Button </rptools/wiki/Token:Macro_Button>`__ on the `Current
            Token </rptools/wiki/Current_Token>`__ . The properties are
            passed to this function as a `String Property
            List </rptools/wiki/String_Property_List>`__. This function
            accepts either a `Macro Button
            Index </maptool/index.php?title=Token:Macro_Button_Index&action=edit&redlink=1>`__
            or the label of a `Macro
            Button </rptools/wiki/Token:Macro_Button>`__. If it is a
            label then all of `Macro
            Buttons </rptools/wiki/Token:Macro_Button>`__ on the
            `Current Token </rptools/wiki/Current_Token>`__ with a
            matching label are changed.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setMacroProps(index, props)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setMacroProps(index, props, delim)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setMacroProps(index, props, delim, id)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setMacroProps(label, props)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setMacroProps(label, props, delim)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     setMacroProps(label, props, delim, id)

         **Parameters**

         -  ``index`` - The index of the macro button.
         -  ``label`` - The label of the macro button.
         -  ``props`` - A `String Property
            List </rptools/wiki/String_Property_List>`__ or `JSON
            Object </rptools/wiki/JSON_Object>`__ containing the
            properties for the button.

            -  ``applyToSelected`` - Should the macro be applied to the
               selected tokens.
            -  ``autoExecute`` - If the macro will be automatically
               executed when the button is clicked, accepts
               ``true``\ (``1``) or ``false``\ (``0``).
            -  ``color`` - The name of the color for the button.
            -  ``command`` - The command for the macro (only when using
               JSON version of function).
            -  ``fontColor`` - The name of the font color for the
               button.
            -  ``fontSize`` - The size of the font for the button.
            -  ``includeLabel`` - If the label will be output when the
               button is clicked. Accepts ``true``\ (``1``) or
               ``false``\ (``0``).
            -  ``group`` - The name of the group that the button belongs
               to.
            -  ``sortBy`` - The sort by value of the macro button.
            -  ``label`` - The label for the button.
            -  ``maxWidth`` - The maximum width of the button.
            -  ``minWidth`` - The minimum width of the button.
            -  ``playerEditable`` - Is the button player editable,
               accepts ``true``\ (``1``) or ``false``\ (``0``).
            -  ``tooltip`` - The tool tip for the macro button.
            -  ``compare`` - Takes a `JSON
               Array </rptools/wiki/JSON_Array>`__ which can contain one
               or more of the following keywords (only usable with JSON
               version of the function).

               -  ``applyToSelected`` - Use the macro applyToSelected
                  for common macro comparisons.
               -  ``autoExecute`` - Use the macro autoExec for common
                  macro comparisons.
               -  ``command`` - Use the macro command for common macro
                  comparisons.
               -  ``group`` - Use the macro group for common macro
                  comparisons.
               -  ``includeLabel`` - Use the macro includeLabel for
                  common macro comparisons.
               -  ``sortPrefix`` - Use the macro sortPrefix for common
                  macro comparisons.

         -  ``delim`` - The delimiter used in the `String Property
            List </rptools/wiki/String_Property_List>`__ that is sent to
            the ``props`` parameter, defaults to ``";"`` and can be
            omitted if you are sending a `JSON
            Object </rptools/wiki/JSON_Object>`__ to the ``props``
            parameter. If you are sending a `JSON
            Object </rptools/wiki/JSON_Object>`__ to the ``props``
            parameter, and using the ``id`` parameter, you can set this
            to ``"json"``.
         -  ``id`` - The token ``id`` of the token that the macro button
            is located on.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro </rptools/wiki/Trusted_Macro>`__. 

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: setMacroProps(1, "color=red;fontColor=white")]

                  #. .. code-block:: none

                        [h: setMacroProps("Attack", "color=red;fontColor=white")]

         | 

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b49** - Added ability for ``props`` to accept a JSON
               object.
            -  **1.3b51** - Added ``id`` parameter option.
            -  **1.3b53** - Added ability for ``command``, ``compare``,
               ``playerEditable``, ``applyToSelected``, ``autoExecute``,
               ``group``, and ``tooltip`` parameters.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=setMacroProps&oldid=3729"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `Stub </rptools/wiki/Category:Stub>`__
            -  `Macro
               Function </rptools/wiki/Category:Macro_Function>`__
            -  `Metamacro
               Function </rptools/wiki/Category:Metamacro_Function>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__
         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__ >
         `Metamacro
         Function </rptools/wiki/Category:Metamacro_Function>`__
         `Review </rptools/wiki/Category:Review>`__ >
         `Stub </rptools/wiki/Category:Stub>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=setMacroProps>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/setMacroProps>`__
            -  `Discussion </maptool/index.php?title=Talk:setMacroProps&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/setMacroProps>`__
            -  `View
               source </maptool/index.php?title=setMacroProps&action=edit>`__
            -  `View
               history </maptool/index.php?title=setMacroProps&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/setMacroProps>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/setMacroProps>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=setMacroProps&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=setMacroProps&oldid=3729>`__
            -  `Page
               information </maptool/index.php?title=setMacroProps&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 23 July 2009, at 22:00.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
