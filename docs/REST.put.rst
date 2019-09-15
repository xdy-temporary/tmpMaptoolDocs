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

