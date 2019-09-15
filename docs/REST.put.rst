.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=REST.put
   |trusted=true
   |version=1.5.0
   |description=
   Perform an HTTP put request to the specified URL to update an existing resource.

   |usage=
   <source lang="mtmacro" line>
   REST.put(url, payload, mediaType, getFullResponse)
   REST.put(url, payload, mediaType, headers, getFullResponse)
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
   Update a user with a put request.
   <source lang="mtmacro" line>
   [h: baseURL = "https://reqres.in"]
   [h: path = "/api/users/2"]
   [h: mediaType = "application/json; charset=utf-8"]
   [h: getFullResponse = 0]

   [h: payload = '{ "name": "morpheus", "job": "zion resident" }']

   [h: response = REST.put(baseURL + path, payload, mediaType, getFullResponse)]

   <br>
   <pre>
   [r: json.indent(response, 2)]
   </pre></source>
   Returns:
   <source lang="mtmacro" line>
   {
     "name": "morpheus",
     "job": "zion resident",
     "updatedAt": "2019-03-17T22:49:52.188Z"
   }
   </source>

   |also=
   [[RESTful_Functions_Overview|RESTful Functions Overview]]
   }}

`Category:RESTful Function <Category:RESTful_Function>`__
