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
            Macro <Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.5.0**

         .. container:: template_description

            Perform an HTTP get request to the specified URL to retrieve
            a resource or information.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

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

                  #. .. code-block:: none

                        [h: baseURL = "https://reqres.in"]

                  #. .. code-block:: none

                        [h: path = "/api/users/2"]

                  #. .. code-block:: none

                         

                  #. .. code-block:: none

                        [h: response = REST.get(baseURL + path, 0)]

                  #. .. code:: de2

                         

                  #. .. code-block:: none

                        <br>

                  #. .. code-block:: none

                        Response: [r: baseURL + path]

                  #. .. code-block:: none

                        <pre>

                  #. .. code-block:: none

                        [r: json.indent(response, 2)]

                  #. .. code:: de2

                        </pre>

                  #. .. code-block:: none

                         

                  #. .. code-block:: none

                        <br><br>

                  #. .. code-block:: none

                         

                  #. .. code-block:: none

                        [h: response = REST.get(baseURL + path, 1)]

                  #. .. code:: de2

                         

                  #. .. code-block:: none

                        <br>

                  #. .. code-block:: none

                        Full Response: [r: baseURL + path]

                  #. .. code-block:: none

                        <pre>

                  #. .. code-block:: none

                        [r: json.indent(response, 2)]

                  #. .. code:: de2

                        </pre>

            Returns:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        Response: https://reqres.in/api/users/2 

                  #. .. code-block:: none

                        {"data": {

                  #. .. code-block:: none

                          "id": 2,

                  #. .. code-block:: none

                          "first_name": "Janet",

                  #. .. code:: de2

                          "last_name": "Weaver",

                  #. .. code-block:: none

                          "avatar": "https://s3.amazonaws.com/uifaces/faces/twitter/josephstein/128.jpg"

                  #. .. code-block:: none

                        }}

                  #. .. code-block:: none

                         

                  #. .. code-block:: none

                         

                  #. .. code:: de2

                        Full Response: https://reqres.in/api/users/2 

                  #. .. code-block:: none

                        {

                  #. .. code-block:: none

                          "status": 200,

                  #. .. code-block:: none

                          "headers":   {

                  #. .. code-block:: none

                            "access-control-allow-origin": ["*"],

                  #. .. code:: de2

                            "cf-ray": ["4b9244475b1b5432-LAX"],

                  #. .. code-block:: none

                            "content-type": ["application/json; charset=utf-8"],

                  #. .. code-block:: none

                            "date": ["Sun, 17 Mar 2019 22:05:09 GMT"],

                  #. .. code-block:: none

                            "etag": ["W/\"89-bSBFK27ZbQL+K8fMuJn/jZrcUuk\""],

                  #. .. code-block:: none

                            "expect-ct": ["max-age=604800, report-uri=\"https://report-uri.cloudflare.com/cdn-cgi/beacon/expect-ct\""],

                  #. .. code:: de2

                            "server": ["cloudflare"],

                  #. .. code-block:: none

                            "set-cookie": ["__cfduid=d5f84a1d88f4b568cd9547d6f76b1712b1552860309; expires=Mon, 16-Mar-20 22:05:09 GMT; path=/; domain=.reqres.in; HttpOnly"],

                  #. .. code-block:: none

                            "x-powered-by": ["Express"]

                  #. .. code-block:: none

                          },

                  #. .. code-block:: none

                          "body": {"data":   {

                  #. .. code:: de2

                            "id": 2,

                  #. .. code-block:: none

                            "first_name": "Janet",

                  #. .. code-block:: none

                            "last_name": "Weaver",

                  #. .. code-block:: none

                            "avatar": "https://s3.amazonaws.com/uifaces/faces/twitter/josephstein/128.jpg"

                  #. .. code-block:: none

                          }}

                  #. .. code:: de2

                        }

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `RESTful Functions
            Overview <RESTful_Functions_Overview>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=REST.get&oldid=7305"

