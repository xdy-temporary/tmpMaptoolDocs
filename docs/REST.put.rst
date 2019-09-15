=====================
REST.put - MapToolDoc
=====================

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

   .. rubric:: REST.put
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

            -  `1 REST.put() Function <#REST.put.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: REST.put() Function
            :name: rest.put-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.5.0**

         .. container:: template_description

            Perform an HTTP put request to the specified URL to update
            an existing resource.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     REST.put(url, payload, mediaType, getFullResponse)

               #. .. code-block:: none

                     REST.put(url, payload, mediaType, headers, getFullResponse)

         **Parameters**

         -  ``url`` - String containing the URL to the resource or
            collection of resources.
         -  ``payload`` - JSON object containing the key:value pairs.
         -  ``mediaType`` - String containing a MIME type and charset.
            See example.
         -  ``headers`` - JSON object containing header key:value pairs.
         -  ``getFullResponse`` - Boolean (0:1). Use true(1) to get full
            response.

         **Returns**

         HTTP response as JSON (if full response) or server response,
         usually JSON but can be XML, HTML, or other formats.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            Update a user with a put request.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: baseURL = "https://reqres.in"]

                  #. .. code-block:: none

                        [h: path = "/api/users/2"]

                  #. .. code-block:: none

                        [h: mediaType = "application/json; charset=utf-8"]

                  #. .. code-block:: none

                        [h: getFullResponse = 0]

                  #. .. code:: de2

                         

                  #. .. code-block:: none

                        [h: payload = '{ "name": "morpheus", "job": "zion resident" }']

                  #. .. code-block:: none

                         

                  #. .. code-block:: none

                        [h: response = REST.put(baseURL + path, payload, mediaType, getFullResponse)]

                  #. .. code-block:: none

                         

                  #. .. code:: de2

                        <br>

                  #. .. code-block:: none

                        <pre>

                  #. .. code-block:: none

                        [r: json.indent(response, 2)]

                  #. .. code-block:: none

                        </pre>

            Returns:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        {

                  #. .. code-block:: none

                          "name": "morpheus",

                  #. .. code-block:: none

                          "job": "zion resident",

                  #. .. code-block:: none

                          "updatedAt": "2019-03-17T22:49:52.188Z"

                  #. .. code:: de2

                        }

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `RESTful Functions
            Overview </rptools/wiki/RESTful_Functions_Overview>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=REST.put&oldid=7309"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `Macro
               Function </rptools/wiki/Category:Macro_Function>`__
            -  `RESTful
               Function </rptools/wiki/Category:RESTful_Function>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__
         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__ > `RESTful
         Function </rptools/wiki/Category:RESTful_Function>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=REST.put>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/REST.put>`__
            -  `Discussion </maptool/index.php?title=Talk:REST.put&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/REST.put>`__
            -  `View
               source </maptool/index.php?title=REST.put&action=edit>`__
            -  `View
               history </maptool/index.php?title=REST.put&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/REST.put>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/REST.put>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=REST.put&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=REST.put&oldid=7309>`__
            -  `Page
               information </maptool/index.php?title=REST.put&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 18 March 2019, at 00:55.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
