=========================
log.setLevel - MapToolDoc
=========================

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

   .. rubric:: log.setLevel
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

            -  `1 log.setLevel()
               Function <#log.setLevel.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: log.setLevel() Function
            :name: log.setlevel-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.5.2**

         .. container:: template_description

            Set the logging level for the specified logger.
            The log file will be found in your user directory under
            ``.maptool-rptools/logs``.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     log.setLevel(logger, loglevel)

         **Parameters**

         -  ``logger`` - String containing a logger name.
         -  ``loglevel`` - String containing a log level:
            DEBUG,INFO,WARN,ERROR,FATAL

         The default level for all loggers is ERROR which means that
         only messages at ERROR or FATAL log level will be output. The
         levels noted above are in verbosity order from most(DEBUG) to
         least(FATAL).

         .. rubric:: Example
            :name: example

         .. container:: template_example

            Set the logging level for the MapToolLineParser to **WARN**.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: log.setLevel("net.rptools.maptool.client.MapToolLineParser","WARN")]

            **Returns:**

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        WARN

            Get a list of loggers and then, using
            `input() </rptools/wiki/input>`__, select a logging level
            for it.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: loggers = json.sort(log.getLoggers(),"a","name")]

                  #. .. code-block:: none

                        [h: loggerList = ""]

                  #. .. code-block:: none

                        [h, FOREACH(logger, loggers), CODE: {

                  #. .. code-block:: none

                            [h: loggerList = listAppend(loggerList,json.get(logger,"name"))]

                  #. .. code:: de2

                        }]

                  #. .. code-block:: none

                        [h:status=input(

                  #. .. code-block:: none

                            "junkVar|Select a Logger and Level||LABEL|SPAN=TRUE",

                  #. .. code-block:: none

                            "lname|"+loggerList+"|Logger|LIST|VALUE=STRING",

                  #. .. code-block:: none

                            "level|DEBUG,INFO,WARN,ERROR,FATAL|Level|LIST|VALUE=STRING")]

                  #. .. code:: de2

                        [h:abort(status)]

                  #. .. code-block:: none

                        [r: "Setting <i><b>" + lname + "</b></i> to <b>" + level + "</b>."]

                  #. .. code-block:: none

                        [h: log.setLevel(lname,level)]

            | 

            |SelectLoggerLevel.png|

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `log.getLoggers() </rptools/wiki/log.getLoggers>`__
             `Available Loggers </rptools/wiki/Available_Loggers>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=log.setLevel&oldid=7402"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `Macro
               Function </rptools/wiki/Category:Macro_Function>`__
            -  `Log Function </rptools/wiki/Category:Log_Function>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__
         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__ > `Log
         Function </rptools/wiki/Category:Log_Function>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=log.setLevel>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/log.setLevel>`__
            -  `Discussion </maptool/index.php?title=Talk:log.setLevel&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/log.setLevel>`__
            -  `View
               source </maptool/index.php?title=log.setLevel&action=edit>`__
            -  `View
               history </maptool/index.php?title=log.setLevel&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/log.setLevel>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/log.setLevel>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=log.setLevel&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=log.setLevel&oldid=7402>`__
            -  `Page
               information </maptool/index.php?title=log.setLevel&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 20 April 2019, at 21:58.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |SelectLoggerLevel.png| image:: /maptool/images/5/5d/SelectLoggerLevel.png
   :width: 475px
   :height: 225px
   :target: /rptools/wiki/File:SelectLoggerLevel.png
.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
