.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=REST.patch
   |trusted=true
   |version=1.5.0
   |description=
   Perform an HTTP patch request, to the specified URL, to make a partial update to the specified resource.

   |usage=
   <source lang="mtmacro" line>
   REST.patch(url, payload, mediaType, getFullResponse)
   REST.patch(url, payload, mediaType, headers, getFullResponse)
   </source>

   '''Parameters'''
   {{param|url|String containing the URL to the resource or collection of resources.}}
   {{param|payload|JSON object containing the key:value pairs.}}
   {{param|mediaType|String containing a MIME type and charset. See example.}}
   {{param|headers|JSON object containing header key:value pairs.}}
   {{param|getFullResponse|Boolean (0:1). Use true(1) to get full response.}}
   '''Returns'''

   HTTP response as JSON (if full response) or server response, usually JSON but can be XML, HTML, or other formats.

   |example=
   Update user data with contents of payload.
   <source lang="mtmacro" line>
   [h: baseURL = "https://reqres.in"]
   [h: path = "/api/users/2"]
   [h: mediaType = "application/json; charset=utf-8"]
   [h: getFullResponse = 1]

   [h: payload = '{ "name": "morpheus", "job": "zion resident" }']

   [h: response = REST.patch(baseURL + path, payload, mediaType, getFullResponse)]

   <br>
   <pre>
   [r: json.indent(response, 2)]
   </pre></source>
   Returns:
   <source lang="mtmacro" line>
   {
     "status": 200,
     "headers":   {
       "access-control-allow-origin": ["*"],
       "cf-ray": ["4b927aa4ea915414-LAX"],
       "content-type": ["application/json; charset=utf-8"],
       "date": ["Sun, 17 Mar 2019 22:42:16 GMT"],
       "etag": ["W/\"50-xvMYBAeY4FNOMM/22NyIcimiIYc\""],
       "expect-ct": ["max-age=604800, report-uri=\"https://report-uri.cloudflare.com/cdn-cgi/beacon/expect-ct\""],
       "server": ["cloudflare"],
       "set-cookie": ["__cfduid=d97966d3e9434720192d81096687475ff1552862536; expires=Mon, 16-Mar-20 22:42:16 GMT; path=/; domain=.reqres.in; HttpOnly"],
       "x-powered-by": ["Express"]
     },
     "body":   {
       "name": "morpheus",
       "job": "zion resident",
       "updatedAt": "2019-03-17T22:46:47.729Z"
     }
   }</source>

   |also=
   [[RESTful_Functions_Overview|RESTful Functions Overview]]

   }}

`Category:RESTful Function <Category:RESTful_Function>`__
