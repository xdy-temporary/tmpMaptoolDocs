.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=REST.delete
   |trusted=true
   |version=1.5.0
   |description=
   Perform an HTTP delete request to the specified URL to delete the specified resource.

   |usage=
   <source lang="mtmacro" line>
   REST.delete(url, getFullResponse)
   REST.delete(url, headers, getFullResponse)
   </source>

   '''Parameters'''
   {{param|url|String containing the URL to the resource or collection of resources.}}
   {{param|headers|JSON object containing header key:value pairs.}}
   {{param|getFullResponse|Boolean (0:1). True(1) to get full response.}}
   '''Returns'''

   HTTP response as JSON (if full response) or server response, usually JSON but can be XML, HTML, or other formats.

   '''Note:''' The delete request returns an empty string for status 204 if the full response is not requested.

   |example=
   Delete the indicated resource.
   <source lang="mtmacro" line>
   [h: baseURL = "https://reqres.in"]
   [h: path = "/api/users/2"]

   [r: response = REST.delete(baseURL + path, 1)]
   </source>
   Returns:
   Note the 204 - No Content status and thus no "body" element in the JSON. If the second parameter had been 0, an empty string would have been returned.
   <source lang="mtmacro" line>
   Full Response: {
     "status": 204,
     "headers":   {
       "access-control-allow-origin": ["*"],
       "cf-ray": ["4b928693e9805414-LAX"],
       "date": ["Sun, 17 Mar 2019 22:50:25 GMT"],
       "etag": ["W/\"2-vyGp6PvFo4RvsFtPoIWeCReyIC8\""],
       "expect-ct": ["max-age=604800, report-uri=\"https://report-uri.cloudflare.com/cdn-cgi/beacon/expect-ct\""],
       "server": ["cloudflare"],
       "set-cookie": ["__cfduid=dc5a1bd174f8f46cb9721f3a3338cff631552863025; expires=Mon, 16-Mar-20 22:50:25 GMT; path=/; domain=.reqres.in; HttpOnly"],
       "x-powered-by": ["Express"]
     }
   }
   </source>

   |also=
   [[RESTful_Functions_Overview|RESTful Functions Overview]]

   }}

`Category:RESTful Function <Category:RESTful_Function>`__
