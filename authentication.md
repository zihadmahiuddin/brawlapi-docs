# Authentication

All API Requests has to be authenticated.

You can do so by providing the `Authorization` header with your token as the value.

## Getting the API Token

1. Join the [Discord Server](https://discord.gg/TaMU4Rz)
2. Head to the [dashboard](https://brawlapi.cf/dashboard) and generate a token.

## Code Samples

Here are some code snippets on how to add custom headers in different languages, adapted from [RoyaleAPI](https://docs.royaleapi.com/#/authentication)

| Endpoint | URL                                          | token         |
| -------- | -------------------------------------------- | ------------- |
| player   | https://api.brawlapi.cf/v1/player?tag=Y2QPGG | `a1234567890` |

### cURL

```bash
curl --header "Authorization: a1234567890" https://api.brawlapi.cf/v1/player?tag=Y2QPGG
```

```bash
curl -X GET \
  https://api.brawlapi.cf/v1/player?tag=Y2QPGG \
  -H 'Authorization: a1234567890' \
```

### C

```csharp
public string Get(string url)
{
    WebHeaderCollection headers = new WebHeaderCollection();
    headers.Add("Authorization: a1234567890");
    HttpWebRequest getRequest = (HttpWebRequest)WebRequest.Create(url);
    getRequest.Method = "GET";
    getRequest.Headers = headers;
    WebResponse apiResponse = getRequest.GetResponse();
    StreamReader reader = new StreamReader(apiResponse.GetResponseStream(), Encoding.UTF8);
    string responseString = reader.ReadToEnd();
    reader.Close();
    apiResponse.Close();

    return responseString;
}
```

### C# RestSharp

```csharp
var client = new RestClient("https://api.brawlapi.cf/v1/player?tag=Y2QPGG");
var request = new RestRequest(Method.GET);
request.AddHeader("Authorization", "a1234567890");
IRestResponse response = client.Execute(request);
```

### Java OK HTTP

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api.brawlapi.cf/v1/player?tag=Y2QPGG")
  .get()
  .addHeader("Authorization", "a1234567890")
  .build();

Response response = client.newCall(request).execute();
```

### Java Unirest

```java
HttpResponse<String> response = Unirest.get("https://api.brawlapi.cf/v1/player?tag=Y2QPGG")
  .header("Authorization", "a1234567890")
  .asString();
```

### Javascript jQuery AJAX

We don’t recommend that you access the API on the client side as you will be exposing your token publicly. However, this is how you would do it with [jQuery](https://api.jquery.com/):

```javascript
var settings = {
  async: true,
  crossDomain: true,
  url: "https://api.brawlapi.cf/v1/player?tag=Y2QPGG",
  method: "GET",
  headers: {
    Authorization: "a1234567890"
  }
};

$.ajax(settings).done(function(response) {
  console.log(response);
});
```

### Node.js

```javascript
const request = require("request");
request("https://api.brawlapi.cf/v1/player?tag=Y2QPGG", {
  headers: { Authorization: "a1234567890" }
});
```

Detailed example:

```javascript
var request = require("request");

var options = {
  method: "GET",
  url: "https://api.brawlapi.cf/v1/player?tag=Y2QPGG",
  headers: { Authorization: "a1234567890" }
};

request(options, function(error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

### PHP

```php
$token = "a1234567890";
$opts = [
    "http" => [
        "header" => "Authorization:" . $token
    ]
];

$context = stream_context_create($opts);

$test = file_get_contents("https://api.brawlapi.cf/v1/player?tag=Y2QPGG",true, $context);
```

### PHP HttpRequest

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api.brawlapi.cf/v1/player?tag=Y2QPGG');
$request->setMethod(HTTP_METH_GET);

$request->setHeaders(array(
  'Authorization' => 'a1234567890'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

### PHP pecl_http

```php
<?php

$client = new http\Client;
$request = new http\Client\Request;

$request->setRequestUrl('https://api.brawlapi.cf/v1/player?tag=Y2QPGG');
$request->setRequestMethod('GET');
$request->setHeaders(array(
  'Authorization' => 'a1234567890'
));

$client->enqueue($request)->send();
$response = $client->getResponse();

echo $response->getBody();
```

### Python http.client (Python 3)

```python
import http.client

conn = http.client.HTTPConnection("brawlapi.cf")

headers = {
    'Authorization': "a1234567890",
}

conn.request("GET", "/player?tag=Y2QPGG", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

### Python (aiohttp)

Asynchronous python using the [aiohttp](https://aiohttp.readthedocs.io/) library.

```python
import aiohttp
headers = {"Authorization": "a1234567890"}
url = "https://api.brawlapi.cf/v1/player?tag=Y2QPGG"
async with aiohttp.ClientSession() as session:
    async with session.get(url, headers=headers) as resp:
        data = await resp.json()
```

### Python (requests)

Synchronous (blocking) Python using the [requests](https://docs.python-requests.org) library.

```python
import requests

url = "https://api.brawlapi.cf/v1/player?tag=Y2QPGG"

headers = {
    'Authorization': "a1234567890"
    }

response = requests.request("GET", url, headers=headers)

data = response.json()
```

### Ruby (NET::Http)

```ruby

require 'uri'
require 'net/http'

url = URI("https://api.brawlapi.cf/v1/player?tag=Y2QPGG")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["Authorization"] = 'a1234567890'

response = http.request(request)
puts response.read_body
```

### Swift (NSURL)

```swift
import Foundation

let headers = [
  "Authorization": "a1234567890",
  "Cache-Control": "no-cache",
]

let request = NSMutableURLRequest(url: NSURL(string: "https://api.brawlapi.cf/v1/player?tag=Y2QPGG")! as URL,
                                        cachePolicy: .useProtocolCachePolicy,
                                    timeoutInterval: 10.0)
request.httpMethod = "GET"
request.allHTTPHeaderFields = headers

let session = URLSession.shared
let dataTask = session.dataTask(with: request as URLRequest, completionHandler: { (data, response, error) -> Void in
  if (error != nil) {
    print(error)
  } else {
    let httpResponse = response as? HTTPURLResponse
    print(httpResponse)
  }
})

dataTask.resume()
```
