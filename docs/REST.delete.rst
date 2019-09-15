========================
REST.delete - MapToolDoc
========================

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

   .. rubric:: REST.delete
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

            -  `1 REST.delete()
               Function <#REST.delete.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: REST.delete() Function
            :name: rest.delete-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.5.0**

         .. container:: template_description

            Perform an HTTP delete request to the specified URL to
            delete the specified resource.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     REST.delete(url, getFullResponse)

               #. .. code-block:: none

                     REST.delete(url, headers, getFullResponse)

         **Parameters**

         -  ``url`` - String containing the URL to the resource or
            collection of resources.
         -  ``headers`` - JSON object containing header key:value pairs.
         -  ``getFullResponse`` - Boolean (0:1). True(1) to get full
            response.

         **Returns**

         HTTP response as JSON (if full response) or server response,
         usually JSON but can be XML, HTML, or other formats.

         **Note:** The delete request returns an empty string for status
         204 if the full response is not requested.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            Delete the indicated resource.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: baseURL = "https://reqres.in"]

                  #. .. code-block:: none

                        [h: path = "/api/users/2"]

                  #. .. code-block:: none

                         

                  #. .. code-block:: none

                        [r: response = REST.delete(baseURL + path, 1)]

            Returns: Note the 204 - No Content status and thus no "body"
            element in the JSON. If the second parameter had been 0, an
            empty string would have been returned.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        Full Response: {

                  #. .. code-block:: none

                          "status": 204,

                  #. .. code-block:: none

                          "headers":   {

                  #. .. code-block:: none

                            "access-control-allow-origin": ["*"],

                  #. .. code:: de2

                            "cf-ray": ["4b928693e9805414-LAX"],

                  #. .. code-block:: none

                            "date": ["Sun, 17 Mar 2019 22:50:25 GMT"],

                  #. .. code-block:: none

                            "etag": ["W/\"2-vyGp6PvFo4RvsFtPoIWeCReyIC8\""],

                  #. .. code-block:: none

                            "expect-ct": ["max-age=604800, report-uri=\"https://report-uri.cloudflare.com/cdn-cgi/beacon/expect-ct\""],

                  #. .. code-block:: none

                            "server": ["cloudflare"],

                  #. .. code:: de2

                            "set-cookie": ["__cfduid=dc5a1bd174f8f46cb9721f3a3338cff631552863025; expires=Mon, 16-Mar-20 22:50:25 GMT; path=/; domain=.reqres.in; HttpOnly"],

                  #. .. code-block:: none

                            "x-powered-by": ["Express"]

                  #. .. code-block:: none

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
         "http://lmwcs.com/maptool/index.php?title=REST.delete&oldid=7313"

