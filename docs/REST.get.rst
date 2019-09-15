=====================
REST.get - MapToolDoc
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

   .. rubric:: REST.get
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

            -  `1 REST.get() Function <#REST.get.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: REST.get() Function
            :name: rest.get-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.5.0**

         .. container:: template_description

            Perform an HTTP get request to the specified URL to retrieve
            a resource or information.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     REST.get(url, getFullResponse)

         **Parameters**

         -  ``url`` - String containing the URL to the resource or
            collection of resources.
         -  ``getFullResponse`` - Boolean (0:1). True(1) to get full
            response.

         **Returns**

         HTTP response as JSON (if full response) or server response,
         usually JSON but can be XML, HTML, or other formats.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            Get the specified user.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        [h: baseURL = "https://reqres.in"]

                  #. .. code:: de1

                        [h: path = "/api/users/2"]

                  #. .. code:: de1

                         

                  #. .. code:: de1

                        [h: response = REST.get(baseURL + path, 0)]

                  #. .. code:: de2

                         

                  #. .. code:: de1

                        <br>

                  #. .. code:: de1

                        Response: [r: baseURL + path]

                  #. .. code:: de1

                        <pre>

                  #. .. code:: de1

                        [r: json.indent(response, 2)]

                  #. .. code:: de2

                        </pre>

                  #. .. code:: de1

                         

                  #. .. code:: de1

                        <br><br>

                  #. .. code:: de1

                         

                  #. .. code:: de1

                        [h: response = REST.get(baseURL + path, 1)]

                  #. .. code:: de2

                         

                  #. .. code:: de1

                        <br>

                  #. .. code:: de1

                        Full Response: [r: baseURL + path]

                  #. .. code:: de1

                        <pre>

                  #. .. code:: de1

                        [r: json.indent(response, 2)]

                  #. .. code:: de2

                        </pre>

            Returns:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code:: de1

                        Response: https://reqres.in/api/users/2 

                  #. .. code:: de1

                        {"data": {

                  #. .. code:: de1

                          "id": 2,

                  #. .. code:: de1

                          "first_name": "Janet",

                  #. .. code:: de2

                          "last_name": "Weaver",

                  #. .. code:: de1

                          "avatar": "https://s3.amazonaws.com/uifaces/faces/twitter/josephstein/128.jpg"

                  #. .. code:: de1

                        }}

                  #. .. code:: de1

                         

                  #. .. code:: de1

                         

                  #. .. code:: de2

                        Full Response: https://reqres.in/api/users/2 

                  #. .. code:: de1

                        {

                  #. .. code:: de1

                          "status": 200,

                  #. .. code:: de1

                          "headers":   {

                  #. .. code:: de1

                            "access-control-allow-origin": ["*"],

                  #. .. code:: de2

                            "cf-ray": ["4b9244475b1b5432-LAX"],

                  #. .. code:: de1

                            "content-type": ["application/json; charset=utf-8"],

                  #. .. code:: de1

                            "date": ["Sun, 17 Mar 2019 22:05:09 GMT"],

                  #. .. code:: de1

                            "etag": ["W/\"89-bSBFK27ZbQL+K8fMuJn/jZrcUuk\""],

                  #. .. code:: de1

                            "expect-ct": ["max-age=604800, report-uri=\"https://report-uri.cloudflare.com/cdn-cgi/beacon/expect-ct\""],

                  #. .. code:: de2

                            "server": ["cloudflare"],

                  #. .. code:: de1

                            "set-cookie": ["__cfduid=d5f84a1d88f4b568cd9547d6f76b1712b1552860309; expires=Mon, 16-Mar-20 22:05:09 GMT; path=/; domain=.reqres.in; HttpOnly"],

                  #. .. code:: de1

                            "x-powered-by": ["Express"]

                  #. .. code:: de1

                          },

                  #. .. code:: de1

                          "body": {"data":   {

                  #. .. code:: de2

                            "id": 2,

                  #. .. code:: de1

                            "first_name": "Janet",

                  #. .. code:: de1

                            "last_name": "Weaver",

                  #. .. code:: de1

                            "avatar": "https://s3.amazonaws.com/uifaces/faces/twitter/josephstein/128.jpg"

                  #. .. code:: de1

                          }}

                  #. .. code:: de2

                        }

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `RESTful Functions
            Overview </rptools/wiki/RESTful_Functions_Overview>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=REST.get&oldid=7305"

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
            in </maptool/index.php?title=Special:UserLogin&returnto=REST.get>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/REST.get>`__
            -  `Discussion </maptool/index.php?title=Talk:REST.get&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/REST.get>`__
            -  `View
               source </maptool/index.php?title=REST.get&action=edit>`__
            -  `View
               history </maptool/index.php?title=REST.get&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/REST.get>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/REST.get>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=REST.get&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=REST.get&oldid=7305>`__
            -  `Page
               information </maptool/index.php?title=REST.get&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 18 March 2019, at 00:45.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
