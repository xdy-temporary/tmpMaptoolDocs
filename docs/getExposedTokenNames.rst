=================================
getExposedTokenNames - MapToolDoc
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

   .. rubric:: getExposedTokenNames
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

            -  `1 getExposedTokenNames()
               Function <#getExposedTokenNames.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 Version Changes <#Version_Changes>`__

         .. rubric:: getExposedTokenNames() Function
            :name: getexposedtokennames-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Gets a list containing the names of all of the
            `tokens </rptools/wiki/Token:token>`__ on the current
            `map </maptool/index.php?title=Map:map&action=edit&redlink=1>`__
            that have been exposed, (i.e. not covered by `fog of
            war </maptool/index.php?title=Map:fog_of_war&action=edit&redlink=1>`__).
            The type of the value returned depends on the delimiter
            parameter.

            -  If the delimiter is not specified then a `string
               list </rptools/wiki/Macros:string_list>`__ is returned
               and the default value of ``","`` is used.
            -  If the delimiter ``"json"`` then a `JSON
               Array </rptools/wiki/JSON_Array>`__ is returned.
            -  Otherwise, a `string
               list </rptools/wiki/Macros:string_list>`__ is returned
               with the delimiter passed in.

             

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     getExposedTokenNames()

               #. .. code:: de1

                     getExposedTokenNames(delim)

         If delim is specified then it is used as the delimiter that
         separates the `token </rptools/wiki/Token:token>`__ names.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            The following example will print out the names of all the
            `tokens </rptools/wiki/Token:token>`__ on the current
            `map </maptool/index.php?title=Map:map&action=edit&redlink=1>`__
            not covered by `fog of
            war </maptool/index.php?title=Map:fog_of_war&action=edit&redlink=1>`__.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [h: names = getExposedTokenNames()]

                  #. .. code:: de1

                        [r: foreach(name, names, "<br>"): name]

            The following example will return the exposed tokens from
            the TOKEN layer only.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        <!-- get all tokens from the token layer and store in json array -->

                  #. .. code:: de1

                        [h:allToks        = getTokenNames("json",'{layer:["TOKEN"]}')]

                  #. .. code:: de1

                        <!-- get all exposed tokens from map -->

                  #. .. code:: de1

                        [h:allExposed = getExposedTokenNames("json")]

                  #. .. code:: de2

                        <!-- get the intersection of token layer tokens and all the exposed tokens, resulting in token layer exposed tokens only -->

                  #. .. code:: de1

                        [h:tokExposed   = json.intersection(allToks, allExp)]

                  #. .. code:: de1

                        <!-- sort the result ascending -->

                  #. .. code:: de1

                        [h:tokExposed  = json.sort(allToks, allExp,"a")]

            This is exactly the same example as the one above, but then
            nested, so you can have the result in one line of code.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [h:tokExposed   = json.sort(json.intersection(getTokenNames("json",'{layer:["TOKEN"]}'), getExposedTokenNames("json")),"a")]

         | 

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b49** - Added *"json"* delimiter option.
            -  **1.3b91** - Apparently now tokens from ALL layers are
               returned, instead of TOKEN LAYER only. Added example to
               correct this.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getExposedTokenNames&oldid=7142"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `Macro
               Function </rptools/wiki/Category:Macro_Function>`__
            -  `Find Function </rptools/wiki/Category:Find_Function>`__
            -  `Token
               Function </rptools/wiki/Category:Token_Function>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__
         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__ > `Find
         Function </rptools/wiki/Category:Find_Function>`__
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
            in </maptool/index.php?title=Special:UserLogin&returnto=getExposedTokenNames>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/getExposedTokenNames>`__
            -  `Discussion </maptool/index.php?title=Talk:getExposedTokenNames&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/getExposedTokenNames>`__
            -  `View
               source </maptool/index.php?title=getExposedTokenNames&action=edit>`__
            -  `View
               history </maptool/index.php?title=getExposedTokenNames&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/getExposedTokenNames>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/getExposedTokenNames>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=getExposedTokenNames&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=getExposedTokenNames&oldid=7142>`__
            -  `Page
               information </maptool/index.php?title=getExposedTokenNames&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 2 March 2019, at 23:23.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
