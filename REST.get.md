|name=REST.get |trusted=true |version=1.5.0 |description= Perform an
HTTP get request to the specified URL to retrieve a resource or
information.

|usage=

``` mtmacro numberLines
REST.get(url, getFullResponse)
```

**Parameters**   **Returns**

HTTP response as JSON (if full response) or server response, usually
JSON but can be XML, HTML, or other formats.

|example= Get the specified user.

``` mtmacro numberLines
[h: baseURL = "https://reqres.in"]
[h: path = "/api/users/2"]

[h: response = REST.get(baseURL + path, 0)]

<br>
Response: [r: baseURL + path]
<pre>
[r: json.indent(response, 2)]
</pre>

<br><br>

[h: response = REST.get(baseURL + path, 1)]

<br>
Full Response: [r: baseURL + path]
<pre>
[r: json.indent(response, 2)]
</pre>
```

Returns:

``` mtmacro numberLines

Response: https://reqres.in/api/users/2
{"data": {
  "id": 2,
  "first_name": "Janet",
  "last_name": "Weaver",
  "avatar": "https://s3.amazonaws.com/uifaces/faces/twitter/josephstein/128.jpg"
}}


Full Response: https://reqres.in/api/users/2
{
  "status": 200,
  "headers":   {
    "access-control-allow-origin": ["*"],
    "cf-ray": ["4b9244475b1b5432-LAX"],
    "content-type": ["application/json; charset=utf-8"],
    "date": ["Sun, 17 Mar 2019 22:05:09 GMT"],
    "etag": ["W/\"89-bSBFK27ZbQL+K8fMuJn/jZrcUuk\""],
    "expect-ct": ["max-age=604800, report-uri=\"https://report-uri.cloudflare.com/cdn-cgi/beacon/expect-ct\""],
    "server": ["cloudflare"],
    "set-cookie": ["__cfduid=d5f84a1d88f4b568cd9547d6f76b1712b1552860309; expires=Mon, 16-Mar-20 22:05:09 GMT; path=/; domain=.reqres.in; HttpOnly"],
    "x-powered-by": ["Express"]
  },
  "body": {"data":   {
    "id": 2,
    "first_name": "Janet",
    "last_name": "Weaver",
    "avatar": "https://s3.amazonaws.com/uifaces/faces/twitter/josephstein/128.jpg"
  }}
}
```

|also= [RESTful Functions
Overview](RESTful_Functions_Overview "wikilink")

[Category:RESTful Function](Category:RESTful_Function "wikilink")