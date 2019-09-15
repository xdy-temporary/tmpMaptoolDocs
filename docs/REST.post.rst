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

