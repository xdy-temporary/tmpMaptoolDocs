======================
REST.post - MapToolDoc
======================

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

   .. rubric:: REST.post
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

            -  `1 REST.post() Function <#REST.post.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: REST.post() Function
            :name: rest.post-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.5.0**

         .. container:: template_description

            Perform an HTTP post request to the specified URL to create
            a resource.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     REST.post(url, payload, mediaType, getFullResponse)

               #. .. code-block:: none

                     REST.post(url, payload, mediaType, headers, getFullResponse)

         **Parameters**

         -  ``url`` - String containing the URL to the resource or
            collection of resources.
         -  ``payload`` - JSON object containing the key:value pairs.
         -  ``mediaType`` - String containing a MIME type and charset.
            See example, but note that any character encoding other than
            ``UTF-8`` will be extremely difficult to produce in MapTool.
         -  ``headers`` - JSON object containing header key:value pairs.
         -  ``getFullResponse`` - Boolean (0:1). True(1) to get full
            response.

         **Returns**

         HTTP response as JSON (if full response) or server response,
         usually JSON but can be XML, HTML, or other formats.

         **Note:** If a post fails with ``getFullResponse`` set to
         false, an error will be produced with a Status Code of 400. Set
         ``getFullResponse`` to true(1) for more detail.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            Create a user with a post request.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: baseurl = "https://reqres.in"]

                  #. .. code-block:: none

                        [h: path = "/api/users"]

                  #. .. code-block:: none

                        [h: mediaType = "application/json; charset=utf-8"]

                  #. .. code-block:: none

                        [h: getFullResponse = 1]

                  #. .. code:: de2

                         

                  #. .. code-block:: none

                        [h: payload = '{ "name": "morpheus", "job": "leader" }']

                  #. .. code-block:: none

                         

                  #. .. code-block:: none

                        [h: response = REST.post(baseurl + path, payload, mediaType, getFullResponse)]

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

                          "status": 201,

                  #. .. code-block:: none

                          "headers":   {

                  #. .. code-block:: none

                            "access-control-allow-origin": ["*"],

                  #. .. code:: de2

                            "cf-ray": ["4b92503c1f49772a-LAX"],

                  #. .. code-block:: none

                            "content-length": ["84"],

                  #. .. code-block:: none

                            "content-type": ["application/json; charset=utf-8"],

                  #. .. code-block:: none

                            "date": ["Sun, 17 Mar 2019 22:13:19 GMT"],

                  #. .. code-block:: none

                            "etag": ["W/\"54-Iq8tAhIi7JekRXqEAyUkl9PsnwI\""],

                  #. .. code:: de2

                            "expect-ct": ["max-age=604800, report-uri=\"https://report-uri.cloudflare.com/cdn-cgi/beacon/expect-ct\""],

                  #. .. code-block:: none

                            "server": ["cloudflare"],

                  #. .. code-block:: none

                            "set-cookie": ["__cfduid=dd8f9e69613d9ab995b4365e36bcc2e181552860799; expires=Mon, 16-Mar-20 22:13:19 GMT; path=/; domain=.reqres.in; HttpOnly"],

                  #. .. code-block:: none

                            "x-powered-by": ["Express"]

                  #. .. code-block:: none

                          },

                  #. .. code:: de2

                          "body":   {

                  #. .. code-block:: none

                            "name": "morpheus",

                  #. .. code-block:: none

                            "job": "leader",

                  #. .. code-block:: none

                            "id": "996",

                  #. .. code-block:: none

                            "createdAt": "2019-03-17T22:17:50.616Z"

                  #. .. code:: de2

                          }

                  #. .. code-block:: none

                        }

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `RESTful Functions
            Overview </rptools/wiki/RESTful_Functions_Overview>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=REST.post&oldid=7310"

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
            in </maptool/index.php?title=Special:UserLogin&returnto=REST.post>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/REST.post>`__
            -  `Discussion </maptool/index.php?title=Talk:REST.post&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/REST.post>`__
            -  `View
               source </maptool/index.php?title=REST.post&action=edit>`__
            -  `View
               history </maptool/index.php?title=REST.post&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/REST.post>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/REST.post>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=REST.post&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=REST.post&oldid=7310>`__
            -  `Page
               information </maptool/index.php?title=REST.post&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 18 March 2019, at 01:43.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
