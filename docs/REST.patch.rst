=======================
REST.patch - MapToolDoc
=======================

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

   .. rubric:: REST.patch
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

            -  `1 REST.patch() Function <#REST.patch.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: REST.patch() Function
            :name: rest.patch-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro <Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.5.0**

         .. container:: template_description

            Perform an HTTP patch request, to the specified URL, to make
            a partial update to the specified resource.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     REST.patch(url, payload, mediaType, getFullResponse)

               #. .. code-block:: none

                     REST.patch(url, payload, mediaType, headers, getFullResponse)

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

            Update user data with contents of payload.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: baseURL = "https://reqres.in"]

                  #. .. code-block:: none

                        [h: path = "/api/users/2"]

                  #. .. code-block:: none

                        [h: mediaType = "application/json; charset=utf-8"]

                  #. .. code-block:: none

                        [h: getFullResponse = 1]

                  #. .. code:: de2

                         

                  #. .. code-block:: none

                        [h: payload = '{ "name": "morpheus", "job": "zion resident" }']

                  #. .. code-block:: none

                         

                  #. .. code-block:: none

                        [h: response = REST.patch(baseURL + path, payload, mediaType, getFullResponse)]

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

                          "status": 200,

                  #. .. code-block:: none

                          "headers":   {

                  #. .. code-block:: none

                            "access-control-allow-origin": ["*"],

                  #. .. code:: de2

                            "cf-ray": ["4b927aa4ea915414-LAX"],

                  #. .. code-block:: none

                            "content-type": ["application/json; charset=utf-8"],

                  #. .. code-block:: none

                            "date": ["Sun, 17 Mar 2019 22:42:16 GMT"],

                  #. .. code-block:: none

                            "etag": ["W/\"50-xvMYBAeY4FNOMM/22NyIcimiIYc\""],

                  #. .. code-block:: none

                            "expect-ct": ["max-age=604800, report-uri=\"https://report-uri.cloudflare.com/cdn-cgi/beacon/expect-ct\""],

                  #. .. code:: de2

                            "server": ["cloudflare"],

                  #. .. code-block:: none

                            "set-cookie": ["__cfduid=d97966d3e9434720192d81096687475ff1552862536; expires=Mon, 16-Mar-20 22:42:16 GMT; path=/; domain=.reqres.in; HttpOnly"],

                  #. .. code-block:: none

                            "x-powered-by": ["Express"]

                  #. .. code-block:: none

                          },

                  #. .. code-block:: none

                          "body":   {

                  #. .. code:: de2

                            "name": "morpheus",

                  #. .. code-block:: none

                            "job": "zion resident",

                  #. .. code-block:: none

                            "updatedAt": "2019-03-17T22:46:47.729Z"

                  #. .. code-block:: none

                          }

                  #. .. code-block:: none

                        }

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `RESTful Functions
            Overview <RESTful_Functions_Overview>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=REST.patch&oldid=7311"

