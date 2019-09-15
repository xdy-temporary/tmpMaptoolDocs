.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=REST.post
   |trusted=true
   |version=1.5.0
   |description=
   Perform an HTTP post request to the specified URL to create a resource.

   |usage=
   <source lang="mtmacro" line>
   REST.post(url, payload, mediaType, getFullResponse)
   REST.post(url, payload, mediaType, headers, getFullResponse)
   </source>

   '''Parameters'''
   {{param|url|String containing the URL to the resource or collection of resources.}}
   {{param|payload|JSON object containing the key:value pairs.}}
   {{param|mediaType|String containing a MIME type and charset. See example, but note that any character encoding other than {{code|UTF-8}} will be extremely difficult to produce in MapTool.}}
   {{param|headers|JSON object containing header key:value pairs.}}
   {{param|getFullResponse|Boolean (0:1). True(1) to get full response.}}
   '''Returns'''

   HTTP response as JSON (if full response) or server response, usually JSON but can be XML, HTML, or other formats.

   '''Note:''' If a post fails with {{code|getFullResponse}} set to false, an error will be produced with a Status Code of 400.  Set {{code|getFullResponse}} to true(1) for more detail.

   |example=
   Create a user with a post request.
   <source lang="mtmacro" line>
   [h: baseurl = "https://reqres.in"]
   [h: path = "/api/users"]
   [h: mediaType = "application/json; charset=utf-8"]
   [h: getFullResponse = 1]

   [h: payload = '{ "name": "morpheus", "job": "leader" }']

   [h: response = REST.post(baseurl + path, payload, mediaType, getFullResponse)]

   <br>
   <pre>
   [r: json.indent(response, 2)]
   </pre>
   </source>
   Returns:
   <source lang="mtmacro" line>
   {
     "status": 201,
     "headers":   {
       "access-control-allow-origin": ["*"],
       "cf-ray": ["4b92503c1f49772a-LAX"],
       "content-length": ["84"],
       "content-type": ["application/json; charset=utf-8"],
       "date": ["Sun, 17 Mar 2019 22:13:19 GMT"],
       "etag": ["W/\"54-Iq8tAhIi7JekRXqEAyUkl9PsnwI\""],
       "expect-ct": ["max-age=604800, report-uri=\"https://report-uri.cloudflare.com/cdn-cgi/beacon/expect-ct\""],
       "server": ["cloudflare"],
       "set-cookie": ["__cfduid=dd8f9e69613d9ab995b4365e36bcc2e181552860799; expires=Mon, 16-Mar-20 22:13:19 GMT; path=/; domain=.reqres.in; HttpOnly"],
       "x-powered-by": ["Express"]
     },
     "body":   {
       "name": "morpheus",
       "job": "leader",
       "id": "996",
       "createdAt": "2019-03-17T22:17:50.616Z"
     }
   }
   </source>

   |also=
   [[RESTful_Functions_Overview|RESTful Functions Overview]]
   }}

`Category:RESTful Function <Category:RESTful_Function>`__
