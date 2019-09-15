================================
getAllPropertyNames - MapToolDoc
================================

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

   .. rubric:: getAllPropertyNames
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

            -  `1 getAllPropertyNames()
               Function <#getAllPropertyNames.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 Version Changes <#Version_Changes>`__

         .. rubric:: getAllPropertyNames() Function
            :name: getallpropertynames-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Gets a list containing the `token
            property </rptools/wiki/Token:token_property>`__ names that
            are defined in the `campaign
            properties </maptool/index.php?title=Campaign:campaign_properties&action=edit&redlink=1>`__.
            The type of the value returned depends on the delimiter
            parameter.

            -  If the delimiter is not specified then a `string
               list </rptools/wiki/Macros:string_list>`__ is returned
               and the default value of ``","`` is used.
            -  If the delimiter is ``"json"`` then a `JSON
               Array </rptools/wiki/JSON_Array>`__ is returned.
            -  Otherwise, a `string
               list </rptools/wiki/Macros:string_list>`__ is returned
               with the delimiter passed in.

             

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getAllPropertyNames()

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getAllPropertyNames(type)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getAllPropertyNames(type, delim)

         If type is specified then the `string
         list </rptools/wiki/Macros:string_list>`__ contains the
         `property </rptools/wiki/Token:token_property>`__ names for
         that `token property
         type </rptools/wiki/Token:token_property_type>`__, otherwise it
         will contain the `token
         property </rptools/wiki/Token:token_property>`__ names for all
         `token property
         types </rptools/wiki/Token:token_property_type>`__. If delim is
         specified then it is used to separate the values in the `string
         list </rptools/wiki/Macros:string_list>`__, if it is not
         specified then it defaults to ','.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            You can use the following code to print out all of the
            properties in the `campaign
            properties </maptool/index.php?title=Campaign:campaign_properties&action=edit&redlink=1>`__
            list..

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        Campaign Properties<br>

                  #. .. code-block:: none

                        [h: props = getAllPropertyNames()]

                  #. .. code-block:: none

                        [foreach(name, props, "<br>"): name]

            If you have two token property sets, for instance "PC" and
            "NPC", you could print out all of the properties for the
            "PC" property set like so:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        PC Properties<br>

                  #. .. code-block:: none

                        [h: props=getAllPropertyNames("PC")]

                  #. .. code-block:: none

                        [foreach(name, props, "<br>"): name]

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b49** - Added ``json`` delimiter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getAllPropertyNames&oldid=7141"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `Macro
               Function </rptools/wiki/Category:Macro_Function>`__
            -  `Token
               Function </rptools/wiki/Category:Token_Function>`__
            -  `Property
               Function </rptools/wiki/Category:Property_Function>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__
         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__ > `Property
         Function </rptools/wiki/Category:Property_Function>`__
         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__ > `Token
         Function </rptools/wiki/Category:Token_Function>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=getAllPropertyNames>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/getAllPropertyNames>`__
            -  `Discussion </maptool/index.php?title=Talk:getAllPropertyNames&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/getAllPropertyNames>`__
            -  `View
               source </maptool/index.php?title=getAllPropertyNames&action=edit>`__
            -  `View
               history </maptool/index.php?title=getAllPropertyNames&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/getAllPropertyNames>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/getAllPropertyNames>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=getAllPropertyNames&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=getAllPropertyNames&oldid=7141>`__
            -  `Page
               information </maptool/index.php?title=getAllPropertyNames&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 2 March 2019, at 23:22.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
