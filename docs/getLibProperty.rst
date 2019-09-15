===========================
getLibProperty - MapToolDoc
===========================

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

   .. rubric:: getLibProperty
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

         .. rubric:: getLibProperty() Function
            :name: getlibproperty-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Returns the value of a `token
            property </rptools/wiki/Token:token_property>`__ from a
            `library token </rptools/wiki/Token:library_token>`__. If
            the lib argument is not specified then the `token
            property </rptools/wiki/Token:token_property>`__ will be
            retrieved from the `library
            token </rptools/wiki/Token:library_token>`__ that the macro
            is currently running from. Unlike
            `getProperty() </rptools/wiki/getProperty>`__, this function
            will not retrieve the default value of a campaign property.
            Default values are generally programmed as local variables
            in a macro, then overridden with the result of this function
            if this function returns a value. An example is shown below.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     getLibProperty(name)

               #. .. code:: de1

                     getLibProperty(name, lib)

         **Important Note** As mentioned in the introduction, if the
         value of the property on the Token equals the default value,
         the function will return nothing! This means that if e.g. you
         set the default property to

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     Weapons : Shotgun, Pistol, Revolver

         And you leave the e.g. the value on the token lib:Compendium
         unchanged, so it will also contain the value "Shotgun, Pistol,
         Revolver", then

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     [getLibProperty("Weapons", "lib:Compendium")]

         will return nothing!

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            To get the "init" `token
            property </rptools/wiki/Token:token_property>`__ from the
            `library token </rptools/wiki/Token:library_token>`__ that a
            macro is running from use.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [getLibProperty("init")]

            To get the "init" `token
            property </rptools/wiki/Token:token_property>`__ from the
            `library token </rptools/wiki/Token:library_token>`__ if the
            library token has such a property. If not, use a default
            value of "default".

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [result = getLibProperty("init")]

                  #. .. code:: de1

                        [IF(result == ""): result = "default" ]

            To get the "init" `token
            property </rptools/wiki/Token:token_property>`__ from a
            `library token </rptools/wiki/Token:library_token>`__ called
            "lib:Attacks" use.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [getLibProperty("init", "lib:Attacks")]

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getLibProperty&oldid=4137"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `Macro
               Function </rptools/wiki/Category:Macro_Function>`__
            -  `Token Library
               Function </rptools/wiki/Category:Token_Library_Function>`__
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
         Library
         Function </rptools/wiki/Category:Token_Library_Function>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=getLibProperty>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/getLibProperty>`__
            -  `Discussion </maptool/index.php?title=Talk:getLibProperty&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/getLibProperty>`__
            -  `View
               source </maptool/index.php?title=getLibProperty&action=edit>`__
            -  `View
               history </maptool/index.php?title=getLibProperty&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/getLibProperty>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/getLibProperty>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=getLibProperty&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=getLibProperty&oldid=4137>`__
            -  `Page
               information </maptool/index.php?title=getLibProperty&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 5 February 2010, at 20:09.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
