====================
getInfo - MapToolDoc
====================

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

   .. rubric:: getInfo
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

            -  `1 getInfo() Function <#getInfo.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 Retrieve client
                  Information <#Retrieve_client_Information>`__
               -  `1.4 Retrieve server
                  Information <#Retrieve_server_Information>`__
               -  `1.5 Retrieve campaign
                  Information <#Retrieve_campaign_Information>`__
               -  `1.6 Version Changes <#Version_Changes>`__

         .. rubric:: getInfo() Function
            :name: getinfo-function

         .. container:: template_version

            • **Introduced in version 1.3b69**

         .. container:: template_description

            Returns a `JSON Object </rptools/wiki/JSON_Object>`__ with
            lots of information about a specified topic.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     getInfo(topic)

         **Parameter**

         -  ``topic`` - A string specifying the topic of the retrieved
            information. Can be ``"map"``, ``"client"``, ``"server"``,
            or ``"campaign"``.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            ===Retrieve ``map`` Information===

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        <!-- print the JSON Object about the current map to the chat window -->

                  #. .. code:: de1

                        <pre>

                  #. .. code:: de1

                        [r: json.indent(getInfo("map"), 2)]

                  #. .. code:: de1

                        </pre>

            Sample output:

            ::

               map
               {
                 "id": "0A00010782897D2C3700000008000102",
                 "image y scale": 1,
                 "height": 0,
                 "largest Z order": 2,
                 "width": 0,
                 "name": "Grasslands",
                 "creation time": 1276351711618,
                 "grid":     {
                   "cell offset height": 0,
                   "cell width": 50,
                   "color": "ff000000",
                   "cell offset width": 0,
                   "units per cell": 5,
                   "cell height": 50,
                  "second dimension": 0,
                   "type": "Square",
                   "x offset": 0,
                   "y offset": 0,
                   "size": 50
                 },
                 "vision type": "off",
                 "image x scale": 1,
                 "player visible": 1
               }

            .. rubric:: Retrieve ``client`` Information
               :name: retrieve-client-information

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        <!-- print the JSON Object about client information to the chat window -->

                  #. .. code:: de1

                        <pre>

                  #. .. code:: de1

                        [r: json.indent(getInfo("client"), 2)]

                  #. .. code:: de1

                        </pre>

            Sample output:

            ::

               client
               {
                 "movement metric": "ONE_TWO_ONE",
                 "library tokens": {
                   "Lib:cifMacroIO": "unknown"
                 },
                 "portrait size": 175,
                 "user defined functions": [
                   "getMacroGroups",
                    "redefined_1_getMacroGroups",
                    "l.decode",
                    "redefined_0_l.decode"
                 ],
                 "timeDate": "2010-10-13 19:03:38",
                 "timeInMs": 1286989418105,
                 "show stat sheet": true,
                 "face vertex": 1,
                 "version": "DEVELOPMENT",
                 "face edge": 1
               }

            **Note:** The ``getInfo("client")`` function returns the
            names of all Lib: tokens. As a bonus if the Lib: token has a
            property called ``libversion``, the value of this property
            will be reported as the value.

            .. rubric:: Retrieve ``server`` Information
               :name: retrieve-server-information

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        <!-- print the JSON Object about server information to the chat window -->

                  #. .. code:: de1

                        <pre>

                  #. .. code:: de1

                        [r: json.indent(getInfo("server"), 2)]

                  #. .. code:: de1

                        </pre>

            .. container:: template_proposed

               |  **Note: This refers to a proposed change that has not
                 been implemented in the main code base yet.**
               | ** Details:**
               | *\**\ **1.3b90**\ *- Added value ``"gm"`` to ``server``
                 return value that holds an array of logged in game
                 masters*

            Sample output:

            ::

               server
               {
                 "initiative owner permissions": 0,
                 "players can reveal": 0,
                 "movement locked": 0,
                 "tooltips for default roll format": 1,
                 "individual views": 0,
                 "players receive campaign macros": 0,
                 "strict token management": 0,
                 "restricted impersonation": 0
               }

            .. rubric:: Retrieve ``campaign`` Information
               :name: retrieve-campaign-information

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        <!-- print the JSON Object about the campaign to the chat window -->

                  #. .. code:: de1

                        <pre>

                  #. .. code:: de1

                        [r: json.indent(getInfo("campaign"), 2)]

                  #. .. code:: de1

                        </pre>

            | 
            | Sample output:

            ::

               campaign
               {
                   "tables": [],
                   "initiative owner permissions": 1,
                   "id": "C0A8001E7F7E199B0B0000008008001E",
                   "sight": {
                   "Darkvision": {
                       "distance": 0,
                       "arc": 0,
                       "shape": "CIRCLE",
                       "type": 0,
                       "multiplier": 1 },
                   "Normal Vision - Short Range": {
                       "distance": 0,
                       "arc": 0,
                       "shape": "CIRCLE",
                       "type": 0,
                       "multiplier": 1 },
                   "Normal": {
                       "distance": 0,
                       "arc": 0,
                       "shape": "CIRCLE",
                       "type": 0,
                       "multiplier": 1 },
                   "Square Vision": {
                       "distance": 0,
                       "arc": 0,
                       "shape": "SQUARE",
                       "type": 0,
                       "multiplier": 1 },
                   "Lowlight": {
                       "distance": 0,
                       "arc": 0,
                       "shape": "CIRCLE",
                       "type": 0,
                       "multiplier": 2 },
                   "Conic Vision": {
                       "distance": 120,
                       "arc": 120,
                       "shape": "CONE",
                       "type": 0,
                       "multiplier": 1 }
                   },
                   "initiative movement locked": 1,
                   "light sources": {
                   "D20": [
                       {
                       "name": "Lantern, Hooded - 30",
                       "light segments": [
                           {
                           "GM": false,
                           "arcAngle": 360,
                           "facingOffset": 0,
                           "ownerOnly": false,
                           "paint": null,
                           "radius": 30,
                           "shape": null },
                           {
                           "GM": false,
                           "arcAngle": 360,
                           "facingOffset": 0,
                           "ownerOnly": false,
                           "paint": {"color":1677721600},
                           "radius": 60,
                           "shape": null } ],
                       "type": "NORMAL",
                       "max range": 60 },
                       {
                       "name": "Candle - 5",
                       "light segments": [
                           {
                           "GM": false,
                           "arcAngle": 360,
                           "facingOffset": 0,
                           "ownerOnly": false,
                           "paint": null,
                           "radius": 5,
                           "shape": null },
                           {
                           "GM": false,
                           "arcAngle": 360,
                           "facingOffset": 0,
                           "ownerOnly": false,
                           "paint": {"color":1677721600},
                           "radius": 10,
                           "shape": null } ],
                       "type": "NORMAL",
                       "max range": 10 },
                       {
                       "name": "Lamp - 15",
                       "light segments": [
                           {
                           "GM": false,
                           "arcAngle": 360,
                           "facingOffset": 0,
                           "ownerOnly": false,
                           "paint": null,
                           "radius": 15,
                           "shape": null },
                           {
                           "GM": false,
                           "arcAngle": 360,
                           "facingOffset": 0,
                           "ownerOnly": false,
                           "paint": {"color":1677721600},
                           "radius": 30,
                           "shape": null } ],
                       "type": "NORMAL",
                       "max range": 30 },
                       {
                       "name": "Torch - 20",
                       "light segments": [
                           {
                           "GM": false,
                           "arcAngle": 360,
                           "facingOffset": 0,
                           "ownerOnly": false,
                           "paint": null,
                           "radius": 20,
                           "shape": null },
                           {
                           "GM": false,
                           "arcAngle": 360,
                           "facingOffset": 0,
                           "ownerOnly": false,
                           "paint": {"color":1677721600},
                           "radius": 40,
                           "shape": null } ],
                       "type": "NORMAL",
                       "max range": 40 },
                       {
                       "name": "Sunrod - 30",
                       "light segments": [
                           {
                           "GM": false,
                           "arcAngle": 360,
                           "facingOffset": 0,
                           "ownerOnly": false,
                           "paint": null,
                           "radius": 30,
                           "shape": null },
                           {
                           "GM": false,
                           "arcAngle": 360,
                           "facingOffset": 0,
                           "ownerOnly": false,
                           "paint": {"color":1677721600},
                           "radius": 60,
                           "shape": null } ],
                       "type": "NORMAL",
                       "max range": 60 },
                       {
                       "name": "Everburning - 20",
                       "light segments": [
                           {
                           "GM": false,
                           "arcAngle": 360,
                           "facingOffset": 0,
                           "ownerOnly": false,
                           "paint": null,
                           "radius": 20,
                           "shape": null },
                           {
                           "GM": false,
                           "arcAngle": 360,
                           "facingOffset": 0,
                           "ownerOnly": false,
                           "paint": {"color":1677721600},
                           "radius": 40,
                           "shape": null } ],
                       "type": "NORMAL",
                       "max range": 40 } ],
                   "Generic": [
                       {
                       "name": "5",
                       "light segments": [
                           {
                           "GM": false,
                           "arcAngle": 360,
                           "facingOffset": 0,
                           "ownerOnly": false,
                           "paint": null,
                           "radius": 5,
                           "shape": null } ],
                       "type": "NORMAL",
                       "max range": 5 },
                       {
                       "name": "40",
                       "light segments": [
                           {
                           "GM": false,
                           "arcAngle": 360,
                           "facingOffset": 0,
                           "ownerOnly": false,
                           "paint": null,
                           "radius": 40,
                           "shape": null } ],
                       "type": "NORMAL",
                       "max range": 40 },
                       {
                       "name": "20",
                       "light segments": [
                           {
                           "GM": false,
                           "arcAngle": 360,
                           "facingOffset": 0,
                           "ownerOnly": false,
                           "paint": null,
                           "radius": 20,
                           "shape": null } ],
                       "type": "NORMAL",
                       "max range": 20 },
                       {
                       "name": "60",
                       "light segments": [
                           {
                           "GM": false,
                           "arcAngle": 360,
                           "facingOffset": 0,
                           "ownerOnly": false,
                           "paint": null,
                           "radius": 60,
                           "shape": null } ],
                       "type": "NORMAL",
                       "max range": 60 },
                       {
                       "name": "15",
                       "light segments": [
                           {
                           "GM": false,
                           "arcAngle": 360,
                           "facingOffset": 0,
                           "ownerOnly": false,
                           "paint": null,
                           "radius": 15,
                           "shape": null } ],
                       "type": "NORMAL",
                       "max range": 15 },
                       {
                       "name": "30",
                       "light segments": [
                           {
                           "GM": false,
                           "arcAngle": 360,
                           "facingOffset": 0,
                           "ownerOnly": false,
                           "paint": null,
                           "radius": 30,
                           "shape": null } ],
                       "type": "NORMAL",
                       "max range": 30 } ] },
                   "bars": {
                   "no group": [
                       {
                       "increment": 0,
                       "side": "TOP",
                       "name": "Health" } ] },
                   "states": {
                   "no group": [
                       "Incapacitated",
                       "Disabled",
                       "Other2",
                       "Other",
                       "Other3",
                       "Prone",
                       "Hidden",
                       "Dead",
                       "Other4" ] },
                   "remote repository": [],
                   "zones": {
                   "Grasslands": "C0A8001E7E7F199B0C0000008008001E" }
               }

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b70** - Added "``campaign"`` option for ``topic``
            -  **1.3b76** - Added values ``"timeInMS"`` and
               "``timeDate"`` to both ``client`` and ``server`` return
               values

            .. container:: template_proposed

               |  **Note: This refers to a proposed change that has not
                 been implemented in the main code base yet.**
               | ** Details:**
               | *\**\ **1.3b90**\ *- Added value ``"gm"`` to ``server``
                 return value that holds an array of logged in game
                 masters*

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getInfo&oldid=6190"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `Proposed
               Change </rptools/wiki/Category:Proposed_Change>`__
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
         `Review </rptools/wiki/Category:Review>`__ > `Proposed
         Change </rptools/wiki/Category:Proposed_Change>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=getInfo>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/getInfo>`__
            -  `Discussion </maptool/index.php?title=Talk:getInfo&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/getInfo>`__
            -  `View
               source </maptool/index.php?title=getInfo&action=edit>`__
            -  `View
               history </maptool/index.php?title=getInfo&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/getInfo>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/getInfo>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=getInfo&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=getInfo&oldid=6190>`__
            -  `Page
               information </maptool/index.php?title=getInfo&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 12 July 2013, at 06:43.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
