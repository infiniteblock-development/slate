---
title: WaaS API Documentation v1.0.0
language_tabs:
  - shell: Shell
  - java: Java
  - javascript: Node
  - ruby: Ruby
  - php: PHP
  - python: Python
language_clients:
  - shell: ""
  - java: ""
  - javascript: ""
  - ruby: ""
  - php: ""
  - python: ""
toc_footers: []
includes: []
search: false
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: widdershins v4.0.1

---

<h1 id="waas-api-documentation">WaaS API Documentation v1.0.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

WaaS API 문서

Base URLs:

* <a href="https://waas.inbl-dev.site">https://waas.inbl-dev.site</a>

# Authentication

* API Key (x-api-key)
    - Parameter Name: **x-api-key**, in: header. WaaS api key

<h1 id="waas-api-documentation-1-network">1. Network</h1>

## 1.1 지원 네트워크 전체 목록 조회

<a id="opIdgetPocketNetworks"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://waas.inbl-dev.site/api/waas/v1/networks \
  -H 'Accept: application/json' \
  -H 'x-api-key: API_KEY'

```

```java
URL obj = new URL("https://waas.inbl-dev.site/api/waas/v1/networks");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-api-key':'API_KEY'
};

fetch('https://waas.inbl-dev.site/api/waas/v1/networks',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-api-key' => 'API_KEY'
}

result = RestClient.get 'https://waas.inbl-dev.site/api/waas/v1/networks',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-api-key' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://waas.inbl-dev.site/api/waas/v1/networks', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-api-key': 'API_KEY'
}

r = requests.get('https://waas.inbl-dev.site/api/waas/v1/networks', headers = headers)

print(r.json())

```

`GET /api/waas/v1/networks`

WaaS에서 사용할 수 있는 블록체인 네트워크 목록을 조회합니다.

<h3 id="1.1-지원-네트워크-전체-목록-조회-parameters">Parameters</h3>

|Name|In|Type|Required|Description|Examples|
|---|---|---|---|---|---|
|chainDisplayId|query|string|false|네트워크 ID|9407131a-25f9-4cd4-a3a3-81795856c58f|
|name|query|string|false|네트워크 이름|go|
|symbol|query|string|false|네트워크 심볼|BTC|
|page|query|int|false|페이지 번호|2|
|size|query|int|false|페이지 크기|15|
|sort|query|string|false|정렬 기준|CHAIN_ID,DESC|

> Example responses

> 200 Response

```json
{
  "count": 22,
  "networks": [
    {
      "networkName": "비트코인 메인넷",
      "chainDisplayId": "099590c1-dafb-4055-8f7d-d88995654bb2",
      "symbol": "BTC"
    }
  ]
}
```

<h3 id="1.1-지원-네트워크-전체-목록-조회-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[지원네트워크 리스트 응답](#schema지원네트워크 리스트 응답)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[ErrorResDTO](#schemaerrorresdto)|

<h3 id="1.1-지원-네트워크-전체-목록-조회-responseschema">Response Schema</h3>

<h1 id="waas-api-documentation-2-coin-token">2. Coin/Token</h1>

## 2.1 코인/토큰 목록 조회

<a id="opIdgetPocketCoinsCurrency"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://waas.inbl-dev.site/api/waas/v1/coins/-/currency?request=isMainnet,true \
  -H 'Accept: application/json' \
  -H 'x-api-key: API_KEY'

```

```java
URL obj = new URL("https://waas.inbl-dev.site/api/waas/v1/coins/-/currency?request=isMainnet,true");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-api-key':'API_KEY'
};

fetch('https://waas.inbl-dev.site/api/waas/v1/coins/-/currency?request=isMainnet,true',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-api-key' => 'API_KEY'
}

result = RestClient.get 'https://waas.inbl-dev.site/api/waas/v1/coins/-/currency',
  params: {
  'request' => '[코인 목록 조회 요청](#schema코인 목록 조회 요청)'
}, headers: headers

p JSON.parse(result)

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-api-key' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://waas.inbl-dev.site/api/waas/v1/coins/-/currency', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-api-key': 'API_KEY'
}

r = requests.get('https://waas.inbl-dev.site/api/waas/v1/coins/-/currency', params={
  'request': {
  "isMainnet": true
}
}, headers = headers)

print(r.json())

```

`GET /api/waas/v1/coins/-/currency`

WaaS에서 사용할 수 있는 코인과 토큰 목록을 조회합니다.

<h3 id="2.1-코인/토큰-목록-조회-parameters">Parameters</h3>

|Name|In|Type|Required|Description|Examples|
|---|---|---|---|---|---|
|isMainnet|query|boolean|false|메인넷 여부|true|
|page|query|int|false|페이지 번호|2|
|size|query|int|false|페이지 크기|15|
|sort|query|string|false|정렬 기준|COIN_CREATED_DT,DESC|
|request|query|[코인 목록 조회 요청](#schema코인 목록 조회 요청)|true|none|none|

> Example responses

> 200 Response

```json
[
  {
    "coinDisplayId": "8130e0f5-64b6-48c0-a10c-1d1d668810e5",
    "koreanName": "이더리움",
    "englishName": "Ethereum",
    "symbol": "ETH",
    "networkName": "비트코인 메인넷",
    "web3NetworkName": "mainnet",
    "price": 4153947.3674999517
  }
]
```

<h3 id="2.1-코인/토큰-목록-조회-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[ErrorResDTO](#schemaerrorresdto)|

<h3 id="2.1-코인/토큰-목록-조회-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Description|
|---|---|---|---|---|
|*anonymous*|[[코인별 원화 가격 응답](#schema코인별 원화 가격 응답)]|false|none|
|» coinDisplayId|string|false|코인 ID|
|» koreanName|string|false|코인 한글명|
|» englishName|string|false|코인 영문명|
|» symbol|string|false|코인 심볼|
|» networkName|string|false|지원네트워크 이름|
|» web3NetworkName|string|false|지원네트워크 Web3 이름|
|» price|number(double)|false|코인 원화 가격|

<h1 id="waas-api-documentation-3-wallet">3. Wallet</h1>

## 3.1 전체 지갑 목록 조회

<a id="opIdgetPocketWallets"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://waas.inbl-dev.site/api/waas/v1/wallets \
  -H 'Accept: application/json' \
  -H 'x-api-key: API_KEY'

```

```java
URL obj = new URL("https://waas.inbl-dev.site/api/waas/v1/wallets");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-api-key':'API_KEY'
};

fetch('https://waas.inbl-dev.site/api/waas/v1/wallets',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-api-key' => 'API_KEY'
}

result = RestClient.get 'https://waas.inbl-dev.site/api/waas/v1/wallets',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-api-key' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://waas.inbl-dev.site/api/waas/v1/wallets', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-api-key': 'API_KEY'
}

r = requests.get('https://waas.inbl-dev.site/api/waas/v1/wallets', headers = headers)

print(r.json())

```

`GET /api/waas/v1/wallets`

고객사가 보유한 지갑 목록을 조회합니다.

<h3 id="3.1-전체-지갑-목록-조회-parameters">Parameters</h3>

|Name|In|Type|Required|Description|Examples|
|---|---|---|---|---|---|
|type|query|string|false|지갑 종류|HOT|
|page|query|int|false|페이지 번호|2|
|size|query|int|false|페이지 크기|15|
|sort|query|string|false|정렬 기준|WALLET_CREATED_DT,DESC|

#### Enumerated Values

|Parameter|Value|
|---|---|
|type|HOT|
|type|COLD|

> Example responses

> 200 Response

```json
{
  "count": 1,
  "wallets": [
    {
      "walletDisplayId": "00478460-b277-455f-94d9-c370d2b9c929",
      "walletName": "이더리움홀스키지갑",
      "krwAmount": 3861940,
      "status": "ACTIVATED",
      "addresses": [
        {
          "addressDisplayId": "4b5fd0fd-34ab-4039-8fec-922560c5d130",
          "address": "0x4C9F7a11D789A0ed2623d4D83614dDe80bdCF16B",
          "totalKrwBalance": 384710,
          "withdrawableKrwBalance": 78390,
          "assets": [
            {}
          ]
        }
      ],
      "createdAt": "2019-08-24T14:15:22Z",
      "updatedAt": "2019-08-24T14:15:22Z",
      "deletedAt": "2019-08-24T14:15:22Z"
    }
  ]
}
```

<h3 id="3.1-전체-지갑-목록-조회-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[지갑 조회 리스트 응답](#schema지갑 조회 리스트 응답)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[ErrorResDTO](#schemaerrorresdto)|

<h3 id="3.1-전체-지갑-목록-조회-responseschema">Response Schema</h3>

## 3.2 지갑 생성

<a id="opIdpostPocketWallet"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://waas.inbl-dev.site/api/waas/v1/wallets \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-api-key: API_KEY'

```

```java
URL obj = new URL("https://waas.inbl-dev.site/api/waas/v1/wallets");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```javascript
const inputBody = '{
  "walletName": "이더리움 지갑2",
  "coinDisplayId": [
    "8130e0f5-64b6-48c0-a10c-1d1d668810e5"
  ],
  "isMainnet": true
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-api-key':'API_KEY'
};

fetch('https://waas.inbl-dev.site/api/waas/v1/wallets',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-api-key' => 'API_KEY'
}

result = RestClient.post 'https://waas.inbl-dev.site/api/waas/v1/wallets',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-api-key' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','https://waas.inbl-dev.site/api/waas/v1/wallets', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-api-key': 'API_KEY'
}

r = requests.post('https://waas.inbl-dev.site/api/waas/v1/wallets', headers = headers)

print(r.json())

```

`POST /api/waas/v1/wallets`

멀티체인 지갑을 생성합니다.

> Body parameter

```json
{
  "walletName": "이더리움 지갑2",
  "coinDisplayId": [
    "8130e0f5-64b6-48c0-a10c-1d1d668810e5"
  ],
  "isMainnet": true
}
```

<h3 id="3.2-지갑-생성-parameters">Parameters</h3>

|Name|In|Type|Required|Description|Examples|
|---|---|---|---|---|---|
|body|body|[지갑 생성 요청](#schema지갑 생성 요청)|true|none|none|

> Example responses

> 400 Response

```json
{
  "error": "string",
  "message": "string",
  "data": "string"
}
```

<h3 id="3.2-지갑-생성-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[ErrorResDTO](#schemaerrorresdto)|

<h3 id="3.2-지갑-생성-responseschema">Response Schema</h3>

## 3.3 지갑 내 자산 추가

<a id="opIdpostPocketWalletAsset"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://waas.inbl-dev.site/api/waas/v1/wallets/{walletDisplayId}/assets \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-api-key: API_KEY'

```

```java
URL obj = new URL("https://waas.inbl-dev.site/api/waas/v1/wallets/{walletDisplayId}/assets");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```javascript
const inputBody = '{
  "coinDisplayIds": [
    "9dae86ce-958e-47bb-9681-ae5e8e91c48d"
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-api-key':'API_KEY'
};

fetch('https://waas.inbl-dev.site/api/waas/v1/wallets/{walletDisplayId}/assets',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-api-key' => 'API_KEY'
}

result = RestClient.post 'https://waas.inbl-dev.site/api/waas/v1/wallets/{walletDisplayId}/assets',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-api-key' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','https://waas.inbl-dev.site/api/waas/v1/wallets/{walletDisplayId}/assets', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-api-key': 'API_KEY'
}

r = requests.post('https://waas.inbl-dev.site/api/waas/v1/wallets/{walletDisplayId}/assets', headers = headers)

print(r.json())

```

`POST /api/waas/v1/wallets/{walletDisplayId}/assets`

지갑 내 네트워크 추가 또는 토큰 추가합니다.

> Body parameter

```json
{
  "coinDisplayIds": [
    "9dae86ce-958e-47bb-9681-ae5e8e91c48d"
  ]
}
```

<h3 id="3.3-지갑-내-자산-추가-parameters">Parameters</h3>

|Name|In|Type|Required|Description|Examples|
|---|---|---|---|---|---|
|walletDisplayId|path|string|true|지갑 ID|00478460-b277-455f-94d9-c370d2b9c929|
|body|body|[자산 추가 요청](#schema자산 추가 요청)|true|none|none|

> Example responses

> 400 Response

```json
{
  "error": "string",
  "message": "string",
  "data": "string"
}
```

<h3 id="3.3-지갑-내-자산-추가-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[ErrorResDTO](#schemaerrorresdto)|

<h3 id="3.3-지갑-내-자산-추가-responseschema">Response Schema</h3>

## 3.4 지갑 상세 정보 조회

<a id="opIdgetPocketWalletByWalletDisplayId"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://waas.inbl-dev.site/api/waas/v1/wallets/{walletDisplayId} \
  -H 'Accept: application/json' \
  -H 'x-api-key: API_KEY'

```

```java
URL obj = new URL("https://waas.inbl-dev.site/api/waas/v1/wallets/{walletDisplayId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-api-key':'API_KEY'
};

fetch('https://waas.inbl-dev.site/api/waas/v1/wallets/{walletDisplayId}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-api-key' => 'API_KEY'
}

result = RestClient.get 'https://waas.inbl-dev.site/api/waas/v1/wallets/{walletDisplayId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-api-key' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://waas.inbl-dev.site/api/waas/v1/wallets/{walletDisplayId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-api-key': 'API_KEY'
}

r = requests.get('https://waas.inbl-dev.site/api/waas/v1/wallets/{walletDisplayId}', headers = headers)

print(r.json())

```

`GET /api/waas/v1/wallets/{walletDisplayId}`

지갑 내 자산 정보를 조회합니다.

<h3 id="3.4-지갑-상세-정보-조회-parameters">Parameters</h3>

|Name|In|Type|Required|Description|Examples|
|---|---|---|---|---|---|
|walletDisplayId|path|string|true|지갑 ID|00478460-b277-455f-94d9-c370d2b9c929|

> Example responses

> 200 Response

```json
{
  "walletDisplayId": "00478460-b277-455f-94d9-c370d2b9c929",
  "walletName": "이더리움홀스키지갑",
  "krwAmount": 3861940,
  "status": "ACTIVATED",
  "addresses": [
    {
      "addressDisplayId": "4b5fd0fd-34ab-4039-8fec-922560c5d130",
      "address": "0x4C9F7a11D789A0ed2623d4D83614dDe80bdCF16B",
      "totalKrwBalance": 384710,
      "withdrawableKrwBalance": 78390,
      "assets": [
        {
          "assetDisplayId": "9c6dc0cc-c4a5-4a12-9c1f-1330621f8abb",
          "koreanName": "이더리움",
          "englishName": "Ethereum",
          "symbol": "ETH",
          "networkName": "이더리움 holesky 테스트넷",
          "totalVolume": 0.33,
          "withdrawableVolume": 0.134,
          "krwPrice": 4157141.637500035
        }
      ]
    }
  ],
  "createdAt": "2019-08-24T14:15:22Z",
  "updatedAt": "2019-08-24T14:15:22Z",
  "deletedAt": "2019-08-24T14:15:22Z"
}
```

<h3 id="3.4-지갑-상세-정보-조회-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[지갑 조회 응답](#schema지갑 조회 응답)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[ErrorResDTO](#schemaerrorresdto)|

<h3 id="3.4-지갑-상세-정보-조회-responseschema">Response Schema</h3>

## 3.5 지갑 정보 변경

<a id="opIdputPocketWallet"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://waas.inbl-dev.site/api/waas/v1/wallets/{walletDisplayId} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-api-key: API_KEY'

```

```java
URL obj = new URL("https://waas.inbl-dev.site/api/waas/v1/wallets/{walletDisplayId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```javascript
const inputBody = '{
  "walletName": "이더리움 지갑2",
  "status": "STOP",
  "description": "이더리움 지갑 ( 사내용 )"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-api-key':'API_KEY'
};

fetch('https://waas.inbl-dev.site/api/waas/v1/wallets/{walletDisplayId}',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-api-key' => 'API_KEY'
}

result = RestClient.post 'https://waas.inbl-dev.site/api/waas/v1/wallets/{walletDisplayId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-api-key' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','https://waas.inbl-dev.site/api/waas/v1/wallets/{walletDisplayId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-api-key': 'API_KEY'
}

r = requests.post('https://waas.inbl-dev.site/api/waas/v1/wallets/{walletDisplayId}', headers = headers)

print(r.json())

```

`POST /api/waas/v1/wallets/{walletDisplayId}`

지갑명, 지갑 설명, 지갑 상태를 변경합니다.

> Body parameter

```json
{
  "walletName": "이더리움 지갑2",
  "status": "STOP",
  "description": "이더리움 지갑 ( 사내용 )"
}
```

<h3 id="3.5-지갑-정보-변경-parameters">Parameters</h3>

|Name|In|Type|Required|Description|Examples|
|---|---|---|---|---|---|
|walletDisplayId|path|string|true|지갑 ID|00478460-b277-455f-94d9-c370d2b9c929|
|body|body|[지갑 변경 요청](#schema지갑 변경 요청)|true|none|none|

> Example responses

> 400 Response

```json
{
  "error": "string",
  "message": "string",
  "data": "string"
}
```

<h3 id="3.5-지갑-정보-변경-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[ErrorResDTO](#schemaerrorresdto)|

<h3 id="3.5-지갑-정보-변경-responseschema">Response Schema</h3>

## 3.7 지갑 삭제하기

<a id="opIddeletePocketWallet"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://waas.inbl-dev.site/api/waas/v1/wallets/{walletDisplayId}/delete \
  -H 'Accept: application/json' \
  -H 'x-api-key: API_KEY'

```

```java
URL obj = new URL("https://waas.inbl-dev.site/api/waas/v1/wallets/{walletDisplayId}/delete");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-api-key':'API_KEY'
};

fetch('https://waas.inbl-dev.site/api/waas/v1/wallets/{walletDisplayId}/delete',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-api-key' => 'API_KEY'
}

result = RestClient.post 'https://waas.inbl-dev.site/api/waas/v1/wallets/{walletDisplayId}/delete',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-api-key' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','https://waas.inbl-dev.site/api/waas/v1/wallets/{walletDisplayId}/delete', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-api-key': 'API_KEY'
}

r = requests.post('https://waas.inbl-dev.site/api/waas/v1/wallets/{walletDisplayId}/delete', headers = headers)

print(r.json())

```

`POST /api/waas/v1/wallets/{walletDisplayId}/delete`

지갑을 삭제합니다.

<h3 id="3.7-지갑-삭제하기-parameters">Parameters</h3>

|Name|In|Type|Required|Description|Examples|
|---|---|---|---|---|---|
|walletDisplayId|path|string|true|지갑 ID|00478460-b277-455f-94d9-c370d2b9c929|

> Example responses

> 400 Response

```json
{
  "error": "string",
  "message": "string",
  "data": "string"
}
```

<h3 id="3.7-지갑-삭제하기-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No Content|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[ErrorResDTO](#schemaerrorresdto)|

<h3 id="3.7-지갑-삭제하기-responseschema">Response Schema</h3>

## 3.8 자산 비중 조회

<a id="opIdgetPocketAssetPercentageByCoin"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://waas.inbl-dev.site/api/waas/v1/wallets/-/percentage \
  -H 'Accept: application/json' \
  -H 'x-api-key: API_KEY'

```

```java
URL obj = new URL("https://waas.inbl-dev.site/api/waas/v1/wallets/-/percentage");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-api-key':'API_KEY'
};

fetch('https://waas.inbl-dev.site/api/waas/v1/wallets/-/percentage',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-api-key' => 'API_KEY'
}

result = RestClient.get 'https://waas.inbl-dev.site/api/waas/v1/wallets/-/percentage',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-api-key' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://waas.inbl-dev.site/api/waas/v1/wallets/-/percentage', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-api-key': 'API_KEY'
}

r = requests.get('https://waas.inbl-dev.site/api/waas/v1/wallets/-/percentage', headers = headers)

print(r.json())

```

`GET /api/waas/v1/wallets/-/percentage`

코인/토큰별로 자산 비중을 조회합니다.

> Example responses

> 200 Response

```json
[
  {
    "coinDisplayId": "3b907b85-9ab9-4a88-85c3-d052b5386c39",
    "coinKoreanName": "이더리움",
    "coinEnglishName": "Ethereum",
    "symbol": "ETH",
    "networkName": "holesky",
    "balance": 0.3343,
    "krwAmount": 18473.54,
    "percentage": 38.31
  }
]
```

<h3 id="3.8-자산-비중-조회-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[ErrorResDTO](#schemaerrorresdto)|

<h3 id="3.8-자산-비중-조회-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Description|
|---|---|---|---|---|
|*anonymous*|[[코인 별 원화 기준 자산 비중 응답](#schema코인 별 원화 기준 자산 비중 응답)]|false|none|
|» coinDisplayId|string|false|코인 ID|
|» coinKoreanName|string|false|코인 한글명|
|» coinEnglishName|string|false|코인 영문명|
|» symbol|string|false|코인 심볼|
|» networkName|string|false|네트워크명|
|» balance|number|false|코인 양|
|» krwAmount|number|false|자산 코인 원화 가치|
|» percentage|number|false|자산 코인 비중|

<h1 id="waas-api-documentation-4-address">4. Address</h1>

## 4.1 주소별로 잔액 조회

<a id="opIdgetPocketAddresses"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://waas.inbl-dev.site/api/waas/v1/wallets/-/addresses \
  -H 'Accept: application/json' \
  -H 'x-api-key: API_KEY'

```

```java
URL obj = new URL("https://waas.inbl-dev.site/api/waas/v1/wallets/-/addresses");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-api-key':'API_KEY'
};

fetch('https://waas.inbl-dev.site/api/waas/v1/wallets/-/addresses',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-api-key' => 'API_KEY'
}

result = RestClient.get 'https://waas.inbl-dev.site/api/waas/v1/wallets/-/addresses',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-api-key' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://waas.inbl-dev.site/api/waas/v1/wallets/-/addresses', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-api-key': 'API_KEY'
}

r = requests.get('https://waas.inbl-dev.site/api/waas/v1/wallets/-/addresses', headers = headers)

print(r.json())

```

`GET /api/waas/v1/wallets/-/addresses`

주소별로 잔액을 조회합니다.

<h3 id="4.1-주소별로-잔액-조회-parameters">Parameters</h3>

|Name|In|Type|Required|Description|Examples|
|---|---|---|---|---|---|
|page|query|int|false|페이지 번호|2|
|size|query|int|false|페이지 크기|15|
|sort|query|string|false|정렬 기준|ADDRESS_CREATED_DT,DESC|

> Example responses

> 200 Response

```json
{
  "count": 0,
  "addresses": [
    {
      "addressDisplayId": "4b5fd0fd-34ab-4039-8fec-922560c5d130",
      "address": "0x4C9F7a11D789A0ed2623d4D83614dDe80bdCF16B",
      "totalKrwBalance": 384710,
      "withdrawableKrwBalance": 78390,
      "assets": [
        {
          "assetDisplayId": "9c6dc0cc-c4a5-4a12-9c1f-1330621f8abb",
          "koreanName": "이더리움",
          "englishName": "Ethereum",
          "symbol": "ETH",
          "networkName": "이더리움 holesky 테스트넷",
          "totalVolume": 0.33,
          "withdrawableVolume": 0.134,
          "krwPrice": 4157141.637500035
        }
      ]
    }
  ]
}
```

<h3 id="4.1-주소별로-잔액-조회-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[주소 리스트 조회 응답](#schema주소 리스트 조회 응답)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[ErrorResDTO](#schemaerrorresdto)|

<h3 id="4.1-주소별로-잔액-조회-responseschema">Response Schema</h3>

## 4.2 주소 생성하기

<a id="opIdpostPocketAddress"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://waas.inbl-dev.site/api/waas/v1/wallets/{walletDisplayId}/addresses \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-api-key: API_KEY'

```

```java
URL obj = new URL("https://waas.inbl-dev.site/api/waas/v1/wallets/{walletDisplayId}/addresses");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```javascript
const inputBody = '{
  "chainDisplayIds": [
    "a3836ad6-d507-4960-a1c8-78c4909db3f4"
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-api-key':'API_KEY'
};

fetch('https://waas.inbl-dev.site/api/waas/v1/wallets/{walletDisplayId}/addresses',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-api-key' => 'API_KEY'
}

result = RestClient.post 'https://waas.inbl-dev.site/api/waas/v1/wallets/{walletDisplayId}/addresses',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-api-key' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','https://waas.inbl-dev.site/api/waas/v1/wallets/{walletDisplayId}/addresses', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-api-key': 'API_KEY'
}

r = requests.post('https://waas.inbl-dev.site/api/waas/v1/wallets/{walletDisplayId}/addresses', headers = headers)

print(r.json())

```

`POST /api/waas/v1/wallets/{walletDisplayId}/addresses`

지갑 내 주소를 생성할 수 있습니다.
- 멀티체인 주소 형식
- 1체인 - N 주소 가능

> Body parameter

```json
{
  "chainDisplayIds": [
    "a3836ad6-d507-4960-a1c8-78c4909db3f4"
  ]
}
```

<h3 id="4.2-주소-생성하기-parameters">Parameters</h3>

|Name|In|Type|Required|Description|Examples|
|---|---|---|---|---|---|
|walletDisplayId|path|string|true|지갑 ID|00478460-b277-455f-94d9-c370d2b9c929|
|body|body|[주소 생성 요청](#schema주소 생성 요청)|true|none|none|

> Example responses

> 400 Response

```json
{
  "error": "string",
  "message": "string",
  "data": "string"
}
```

<h3 id="4.2-주소-생성하기-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[ErrorResDTO](#schemaerrorresdto)|

<h3 id="4.2-주소-생성하기-responseschema">Response Schema</h3>

<h1 id="waas-api-documentation-5-withdrawal">5. Withdrawal</h1>

## 5.1 출금 신청

<a id="opIdpostWithdraw_1"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://waas.inbl-dev.site/api/waas/v1/assets/{assetDisplayId}/withdrawals \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-api-key: API_KEY'

```

```java
URL obj = new URL("https://waas.inbl-dev.site/api/waas/v1/assets/{assetDisplayId}/withdrawals");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```javascript
const inputBody = '{
  "depositAddresses": [
    {
      "address": "0x705C4c94B0440a19Fd0C4805ED3b5631E923384d",
      "dstTag": "string",
      "amount": 0.0045
    }
  ],
  "memo": "피자 값",
  "feePriority": "FAST"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-api-key':'API_KEY'
};

fetch('https://waas.inbl-dev.site/api/waas/v1/assets/{assetDisplayId}/withdrawals',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-api-key' => 'API_KEY'
}

result = RestClient.post 'https://waas.inbl-dev.site/api/waas/v1/assets/{assetDisplayId}/withdrawals',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-api-key' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','https://waas.inbl-dev.site/api/waas/v1/assets/{assetDisplayId}/withdrawals', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-api-key': 'API_KEY'
}

r = requests.post('https://waas.inbl-dev.site/api/waas/v1/assets/{assetDisplayId}/withdrawals', headers = headers)

print(r.json())

```

`POST /api/waas/v1/assets/{assetDisplayId}/withdrawals`

코인/토큰 출금을 신청합니다.

> Body parameter

```json
{
  "depositAddresses": [
    {
      "address": "0x705C4c94B0440a19Fd0C4805ED3b5631E923384d",
      "dstTag": "string",
      "amount": 0.0045
    }
  ],
  "memo": "피자 값",
  "feePriority": "FAST"
}
```

<h3 id="5.1-출금-신청-parameters">Parameters</h3>

|Name|In|Type|Required|Description|Examples|
|---|---|---|---|---|---|
|assetDisplayId|path|string|true|자산 ID|9f194931-12de-466d-9b03-d25e2a51686d|
|body|body|[자산 출금 신청 요청](#schema자산 출금 신청 요청)|true|none|none|

> Example responses

> 400 Response

```json
{
  "error": "string",
  "message": "string",
  "data": "string"
}
```

<h3 id="5.1-출금-신청-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[ErrorResDTO](#schemaerrorresdto)|

<h3 id="5.1-출금-신청-responseschema">Response Schema</h3>

## 5.2 네트워크 수수료 조회

<a id="opIdgetWithdrawalFee_1"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://waas.inbl-dev.site/api/waas/v1/assets/{assetDisplayId}/withdrawals/-/fee \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-api-key: API_KEY'

```

```java
URL obj = new URL("https://waas.inbl-dev.site/api/waas/v1/assets/{assetDisplayId}/withdrawals/-/fee");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```javascript
const inputBody = '{
  "counterparties": [
    {
      "address": "0x705C4c94B0440a19Fd0C4805ED3b5631E923384d",
      "dstTag": "string",
      "amount": 0.0045
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-api-key':'API_KEY'
};

fetch('https://waas.inbl-dev.site/api/waas/v1/assets/{assetDisplayId}/withdrawals/-/fee',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-api-key' => 'API_KEY'
}

result = RestClient.post 'https://waas.inbl-dev.site/api/waas/v1/assets/{assetDisplayId}/withdrawals/-/fee',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-api-key' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','https://waas.inbl-dev.site/api/waas/v1/assets/{assetDisplayId}/withdrawals/-/fee', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-api-key': 'API_KEY'
}

r = requests.post('https://waas.inbl-dev.site/api/waas/v1/assets/{assetDisplayId}/withdrawals/-/fee', headers = headers)

print(r.json())

```

`POST /api/waas/v1/assets/{assetDisplayId}/withdrawals/-/fee`

네트워크 수수료를 조회합니다.
수수료는 느림, 중간, 빠름 수수료를 조회할 수 있습니다.

> Body parameter

```json
{
  "counterparties": [
    {
      "address": "0x705C4c94B0440a19Fd0C4805ED3b5631E923384d",
      "dstTag": "string",
      "amount": 0.0045
    }
  ]
}
```

<h3 id="5.2-네트워크-수수료-조회-parameters">Parameters</h3>

|Name|In|Type|Required|Description|Examples|
|---|---|---|---|---|---|
|assetDisplayId|path|string|true|자산 ID|9f194931-12de-466d-9b03-d25e2a51686d|
|body|body|[자산 출금 수수료 조회 요청](#schema자산 출금 수수료 조회 요청)|true|none|none|

> Example responses

> 200 Response

```json
{
  "fast": 0.000085978712308125,
  "standard": 0.000085978712308125,
  "slow": 0.000085978712308125
}
```

<h3 id="5.2-네트워크-수수료-조회-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[자산 출금 수수료 조회 응답](#schema자산 출금 수수료 조회 응답)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[ErrorResDTO](#schemaerrorresdto)|

<h3 id="5.2-네트워크-수수료-조회-responseschema">Response Schema</h3>

## 5.3 네트워크 수수료 재설정

<a id="opIdputTransactionFee_1"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://waas.inbl-dev.site/api/waas/v1/assets/-/withdrawals/{transactionDisplayId}/replace-fee \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-api-key: API_KEY'

```

```java
URL obj = new URL("https://waas.inbl-dev.site/api/waas/v1/assets/-/withdrawals/{transactionDisplayId}/replace-fee");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```javascript
const inputBody = '{
  "accelerateFee": 0.0001
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-api-key':'API_KEY'
};

fetch('https://waas.inbl-dev.site/api/waas/v1/assets/-/withdrawals/{transactionDisplayId}/replace-fee',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-api-key' => 'API_KEY'
}

result = RestClient.post 'https://waas.inbl-dev.site/api/waas/v1/assets/-/withdrawals/{transactionDisplayId}/replace-fee',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-api-key' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','https://waas.inbl-dev.site/api/waas/v1/assets/-/withdrawals/{transactionDisplayId}/replace-fee', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-api-key': 'API_KEY'
}

r = requests.post('https://waas.inbl-dev.site/api/waas/v1/assets/-/withdrawals/{transactionDisplayId}/replace-fee', headers = headers)

print(r.json())

```

`POST /api/waas/v1/assets/-/withdrawals/{transactionDisplayId}/replace-fee`

네트워크 수수료를 재설정합니다.

> Body parameter

```json
{
  "accelerateFee": 0.0001
}
```

<h3 id="5.3-네트워크-수수료-재설정-parameters">Parameters</h3>

|Name|In|Type|Required|Description|Examples|
|---|---|---|---|---|---|
|transactionDisplayId|path|string|true|트랜잭션 ID|b0797a66-37d3-4d88-8351-7810c6561858|
|body|body|[자산 출금 수수료 재설정 요청](#schema자산 출금 수수료 재설정 요청)|true|none|none|

> Example responses

> 400 Response

```json
{
  "error": "string",
  "message": "string",
  "data": "string"
}
```

<h3 id="5.3-네트워크-수수료-재설정-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[ErrorResDTO](#schemaerrorresdto)|

<h3 id="5.3-네트워크-수수료-재설정-responseschema">Response Schema</h3>

<h1 id="waas-api-documentation-6-transaction">6. Transaction</h1>

## 6.1 전체 입출금 내역 조회

<a id="opIdgetTransactions_1"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://waas.inbl-dev.site/api/waas/v1/coin-transactions \
  -H 'Accept: application/json' \
  -H 'x-api-key: API_KEY'

```

```java
URL obj = new URL("https://waas.inbl-dev.site/api/waas/v1/coin-transactions");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-api-key':'API_KEY'
};

fetch('https://waas.inbl-dev.site/api/waas/v1/coin-transactions',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-api-key' => 'API_KEY'
}

result = RestClient.get 'https://waas.inbl-dev.site/api/waas/v1/coin-transactions',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-api-key' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://waas.inbl-dev.site/api/waas/v1/coin-transactions', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-api-key': 'API_KEY'
}

r = requests.get('https://waas.inbl-dev.site/api/waas/v1/coin-transactions', headers = headers)

print(r.json())

```

`GET /api/waas/v1/coin-transactions`

전체 입출금 내역을 조회합니다.

<h3 id="6.1-전체-입출금-내역-조회-parameters">Parameters</h3>

|Name|In|Type|Required|Description|Examples|
|---|---|---|---|---|---|
|walletType|query|string|false|지갑 종류|HOT|
|walletName|query|string|false|지갑 이름|사내용|
|address|query|string|false|주소|0xD3|
|transactionHash|query|string|false|트랜잭션 해시값|0xb43d6ec31|
|startDt|query|string(yyyy-MM-dd HH:mm:ss)|false|트랜잭션 발생 시작일|2024-04-10 12:35:10|
|endDt|query|string(yyyy-MM-dd HH:mm:ss)|false|트랜잭션 발생 종료일|2024-04-25 07:31:45|
|statuses|query|array[string]|false|트랜잭션 상태|none|
|page|query|int|false|페이지 번호|2|
|size|query|int|false|페이지 크기|15|
|sort|query|string|false|정렬 기준|TRANSACTION_UPDATED_DT,DESC|

#### Enumerated Values

|Parameter|Value|
|---|---|
|walletType|HOT|
|walletType|COLD|
|statuses|WITHDRAW_WAIT|
|statuses|WITHDRAW_IN_PROGRESS|
|statuses|WITHDRAW_CANCEL|
|statuses|WITHDRAW_FAIL|
|statuses|WITHDRAW_COMPLETE|
|statuses|DEPOSIT_COMPLETE|

> Example responses

> 200 Response

```json
{
  "count": 53,
  "transactions": [
    {
      "transactionDisplayId": "b9fa192c-56c5-4cf2-a8ac-d65fd94bbc73",
      "walletName": "사내용 지갑",
      "coinName": "이더리움",
      "symbol": "ETH",
      "network": "HOLESKY",
      "type": "WITHDRAW",
      "stat": "COMPLETE_WITHDRAW",
      "transactionHash": "0xff257541bb08497180c6087acf822ad7ac0cb9b473eb8c1d183d80d826ca6fdb",
      "amount": 0.001,
      "fee": 0.000082355175273,
      "coinToUsd": 3254.4606600225,
      "usdToKrw": 1375.9,
      "amountKrw": 4496,
      "feeKrw": 368,
      "completedAt": "2019-08-24T14:15:22Z",
      "counterparties": [
        {
          "address": "0x9F1229D97F17BB45f4598195B36b667b01Bc6495",
          "dstTag": "string",
          "amount": 0.001
        }
      ]
    }
  ]
}
```

<h3 id="6.1-전체-입출금-내역-조회-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[자산 트랜잭션 리스트 조회 응답](#schema자산 트랜잭션 리스트 조회 응답)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[ErrorResDTO](#schemaerrorresdto)|

<h3 id="6.1-전체-입출금-내역-조회-responseschema">Response Schema</h3>

## 6.2 입출금 상세 정보 조회

<a id="opIdgetTransaction_1"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://waas.inbl-dev.site/api/waas/v1/coin-transactions/{transactionDisplayId} \
  -H 'Accept: application/json' \
  -H 'x-api-key: API_KEY'

```

```java
URL obj = new URL("https://waas.inbl-dev.site/api/waas/v1/coin-transactions/{transactionDisplayId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-api-key':'API_KEY'
};

fetch('https://waas.inbl-dev.site/api/waas/v1/coin-transactions/{transactionDisplayId}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-api-key' => 'API_KEY'
}

result = RestClient.get 'https://waas.inbl-dev.site/api/waas/v1/coin-transactions/{transactionDisplayId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-api-key' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://waas.inbl-dev.site/api/waas/v1/coin-transactions/{transactionDisplayId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-api-key': 'API_KEY'
}

r = requests.get('https://waas.inbl-dev.site/api/waas/v1/coin-transactions/{transactionDisplayId}', headers = headers)

print(r.json())

```

`GET /api/waas/v1/coin-transactions/{transactionDisplayId}`

특정 입출금건에 대한 상세 정보를 조회합니다.

<h3 id="6.2-입출금-상세-정보-조회-parameters">Parameters</h3>

|Name|In|Type|Required|Description|Examples|
|---|---|---|---|---|---|
|transactionDisplayId|path|string|true|트랜잭션 ID|b9fa192c-56c5-4cf2-a8ac-d65fd94bbc73|

> Example responses

> 200 Response

```json
{
  "transactionDisplayId": "b9fa192c-56c5-4cf2-a8ac-d65fd94bbc73",
  "walletName": "사내용 지갑",
  "coinName": "이더리움",
  "symbol": "ETH",
  "network": "HOLESKY",
  "type": "WITHDRAW",
  "stat": "COMPLETE_WITHDRAW",
  "transactionHash": "0xff257541bb08497180c6087acf822ad7ac0cb9b473eb8c1d183d80d826ca6fdb",
  "amount": 0.001,
  "fee": 0.000082355175273,
  "coinToUsd": 3254.4606600225,
  "usdToKrw": 1375.9,
  "amountKrw": 4496,
  "feeKrw": 368,
  "completedAt": "2019-08-24T14:15:22Z",
  "counterparties": [
    {
      "address": "0x9F1229D97F17BB45f4598195B36b667b01Bc6495",
      "dstTag": "string",
      "amount": 0.001
    }
  ]
}
```

<h3 id="6.2-입출금-상세-정보-조회-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[자산 트랜잭션 조회 응답](#schema자산 트랜잭션 조회 응답)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[ErrorResDTO](#schemaerrorresdto)|

<h3 id="6.2-입출금-상세-정보-조회-responseschema">Response Schema</h3>

<h1 id="waas-api-documentation-7-nft">7. NFT</h1>

## 7.1 전체 NFT 보유 목록 조회

<a id="opIdgetNfts"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://waas.inbl-dev.site/api/waas/v1/nfts \
  -H 'Accept: application/json' \
  -H 'x-api-key: API_KEY'

```

```java
URL obj = new URL("https://waas.inbl-dev.site/api/waas/v1/nfts");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-api-key':'API_KEY'
};

fetch('https://waas.inbl-dev.site/api/waas/v1/nfts',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-api-key' => 'API_KEY'
}

result = RestClient.get 'https://waas.inbl-dev.site/api/waas/v1/nfts',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-api-key' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://waas.inbl-dev.site/api/waas/v1/nfts', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-api-key': 'API_KEY'
}

r = requests.get('https://waas.inbl-dev.site/api/waas/v1/nfts', headers = headers)

print(r.json())

```

`GET /api/waas/v1/nfts`

전체 NFT 보유 목록을 조회합니다.

<h3 id="7.1-전체-nft-보유-목록-조회-parameters">Parameters</h3>

|Name|In|Type|Required|Description|Examples|
|---|---|---|---|---|---|
|walletName|query|string|false|지갑 명|사내용|
|standard|query|string|false|표준명|ERC-720|
|contractName|query|string|false|컨트랙트 이름|JINUNF7|
|contractAddress|query|string|false|컨트랙트 주소|ad3Q|
|network|query|string|false|네트워크 종류|TEST_NET|
|tokenId|query|string|false|토큰 아이디|21|
|tokenName|query|string|false|토큰 명|21|
|symbol|query|string|false|토큰 심볼|JI8|
|page|query|int|false|페이지 번호|2|
|size|query|int|false|페이지 크기|15|
|sort|query|string|false|정렬 기준|NFT_CREATED_DT,DESC|

> Example responses

> 200 Response

```json
{
  "count": 3,
  "nfts": [
    {
      "nftDisplayId": "8472572f-8c99-4e5e-8c0c-8066ba8f7bb8",
      "koreanName": "29",
      "addressDisplayId": "b5d3cbdf-42d8-4b5f-96b4-9ffcd7850f6a",
      "walletName": "첫번째 지갑",
      "standard": "ERC-721",
      "contractAddress": "0xad34a40cee2df54e7669f2c3848237496717c099",
      "contractName": "JINUNFT",
      "symbol": "JINU",
      "tokenId": 29,
      "tokenName": "29",
      "totalVolume": 2,
      "withdrawableVolume": 1,
      "depositDt": "2019-08-24T14:15:22Z"
    }
  ]
}
```

<h3 id="7.1-전체-nft-보유-목록-조회-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[NFT 리스트 조회 응답](#schemanft 리스트 조회 응답)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[ErrorResDTO](#schemaerrorresdto)|

<h3 id="7.1-전체-nft-보유-목록-조회-responseschema">Response Schema</h3>

## 7.2 NFT 상세 정보 조회

<a id="opIdgetNft"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://waas.inbl-dev.site/api/waas/v1/nfts/{nftDisplayIdId} \
  -H 'Accept: application/json' \
  -H 'x-api-key: API_KEY'

```

```java
URL obj = new URL("https://waas.inbl-dev.site/api/waas/v1/nfts/{nftDisplayIdId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-api-key':'API_KEY'
};

fetch('https://waas.inbl-dev.site/api/waas/v1/nfts/{nftDisplayIdId}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-api-key' => 'API_KEY'
}

result = RestClient.get 'https://waas.inbl-dev.site/api/waas/v1/nfts/{nftDisplayIdId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-api-key' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://waas.inbl-dev.site/api/waas/v1/nfts/{nftDisplayIdId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-api-key': 'API_KEY'
}

r = requests.get('https://waas.inbl-dev.site/api/waas/v1/nfts/{nftDisplayIdId}', headers = headers)

print(r.json())

```

`GET /api/waas/v1/nfts/{nftDisplayIdId}`

특정 NFT에 대한 상세 정보를 조회합니다.

<h3 id="7.2-nft-상세-정보-조회-parameters">Parameters</h3>

|Name|In|Type|Required|Description|Examples|
|---|---|---|---|---|---|
|nftDisplayIdId|path|string|true|NFT ID|8472572f-8c99-4e5e-8c0c-8066ba8f7bb8|

> Example responses

> 200 Response

```json
{
  "nftDisplayId": "8472572f-8c99-4e5e-8c0c-8066ba8f7bb8",
  "koreanName": "29",
  "addressDisplayId": "b5d3cbdf-42d8-4b5f-96b4-9ffcd7850f6a",
  "walletName": "첫번째 지갑",
  "standard": "ERC-721",
  "contractAddress": "0xad34a40cee2df54e7669f2c3848237496717c099",
  "contractName": "JINUNFT",
  "symbol": "JINU",
  "tokenId": 29,
  "tokenName": "29",
  "totalVolume": 2,
  "withdrawableVolume": 1,
  "depositDt": "2019-08-24T14:15:22Z"
}
```

<h3 id="7.2-nft-상세-정보-조회-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[NFT 조회 응답](#schemanft 조회 응답)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[ErrorResDTO](#schemaerrorresdto)|

<h3 id="7.2-nft-상세-정보-조회-responseschema">Response Schema</h3>

## 7.4 NFT 출금 신청

<a id="opIdpostWithdraw"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://waas.inbl-dev.site/api/waas/v1/nfts/{nftDisplayId}/withdrawals \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-api-key: API_KEY'

```

```java
URL obj = new URL("https://waas.inbl-dev.site/api/waas/v1/nfts/{nftDisplayId}/withdrawals");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```javascript
const inputBody = '{
  "depositAddresses": [
    {
      "address": "0x705C4c94B0440a19Fd0C4805ED3b5631E923384d",
      "dstTag": "string",
      "amount": 0.0045
    }
  ],
  "memo": "피자 값",
  "feePriority": "FAST"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-api-key':'API_KEY'
};

fetch('https://waas.inbl-dev.site/api/waas/v1/nfts/{nftDisplayId}/withdrawals',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-api-key' => 'API_KEY'
}

result = RestClient.post 'https://waas.inbl-dev.site/api/waas/v1/nfts/{nftDisplayId}/withdrawals',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-api-key' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','https://waas.inbl-dev.site/api/waas/v1/nfts/{nftDisplayId}/withdrawals', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-api-key': 'API_KEY'
}

r = requests.post('https://waas.inbl-dev.site/api/waas/v1/nfts/{nftDisplayId}/withdrawals', headers = headers)

print(r.json())

```

`POST /api/waas/v1/nfts/{nftDisplayId}/withdrawals`

NFT 출금 신청을 합니다.

> Body parameter

```json
{
  "depositAddresses": [
    {
      "address": "0x705C4c94B0440a19Fd0C4805ED3b5631E923384d",
      "dstTag": "string",
      "amount": 0.0045
    }
  ],
  "memo": "피자 값",
  "feePriority": "FAST"
}
```

<h3 id="7.4-nft-출금-신청-parameters">Parameters</h3>

|Name|In|Type|Required|Description|Examples|
|---|---|---|---|---|---|
|nftDisplayId|path|string|true|NFT ID|780dc62e-5c1a-4014-935d-7a0ce243d4e5|
|body|body|[NFT 출금 신청 요청](#schemanft 출금 신청 요청)|true|none|none|

> Example responses

> 400 Response

```json
{
  "error": "string",
  "message": "string",
  "data": "string"
}
```

<h3 id="7.4-nft-출금-신청-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[ErrorResDTO](#schemaerrorresdto)|

<h3 id="7.4-nft-출금-신청-responseschema">Response Schema</h3>

## 7.5 네트워크 수수료 조회

<a id="opIdgetWithdrawalFee"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://waas.inbl-dev.site/api/waas/v1/nfts/{nftDisplayId}/withdrawals/-/fee \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-api-key: API_KEY'

```

```java
URL obj = new URL("https://waas.inbl-dev.site/api/waas/v1/nfts/{nftDisplayId}/withdrawals/-/fee");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```javascript
const inputBody = '{
  "counterparties": [
    {
      "address": "0x705C4c94B0440a19Fd0C4805ED3b5631E923384d",
      "dstTag": "string",
      "amount": 0.0045
    }
  ]
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-api-key':'API_KEY'
};

fetch('https://waas.inbl-dev.site/api/waas/v1/nfts/{nftDisplayId}/withdrawals/-/fee',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-api-key' => 'API_KEY'
}

result = RestClient.post 'https://waas.inbl-dev.site/api/waas/v1/nfts/{nftDisplayId}/withdrawals/-/fee',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-api-key' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','https://waas.inbl-dev.site/api/waas/v1/nfts/{nftDisplayId}/withdrawals/-/fee', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-api-key': 'API_KEY'
}

r = requests.post('https://waas.inbl-dev.site/api/waas/v1/nfts/{nftDisplayId}/withdrawals/-/fee', headers = headers)

print(r.json())

```

`POST /api/waas/v1/nfts/{nftDisplayId}/withdrawals/-/fee`

네트워크 수수료를 조회합니다.
수수료는 느림, 중간, 빠름 수수료를 조회할 수 있습니다.

> Body parameter

```json
{
  "counterparties": [
    {
      "address": "0x705C4c94B0440a19Fd0C4805ED3b5631E923384d",
      "dstTag": "string",
      "amount": 0.0045
    }
  ]
}
```

<h3 id="7.5-네트워크-수수료-조회-parameters">Parameters</h3>

|Name|In|Type|Required|Description|Examples|
|---|---|---|---|---|---|
|nftDisplayId|path|string|true|NFT ID|780dc62e-5c1a-4014-935d-7a0ce243d4e5|
|body|body|[NFT 출금 수수료 조회 요청](#schemanft 출금 수수료 조회 요청)|true|none|none|

> Example responses

> 200 Response

```json
{
  "fast": 0.000085978712308125,
  "standard": 0.000085978712308125,
  "slow": 0.000085978712308125
}
```

<h3 id="7.5-네트워크-수수료-조회-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[자산 출금 수수료 조회 응답](#schema자산 출금 수수료 조회 응답)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[ErrorResDTO](#schemaerrorresdto)|

<h3 id="7.5-네트워크-수수료-조회-responseschema">Response Schema</h3>

## 7.6 네트워크 수수료 재설정

<a id="opIdputTransactionFee"></a>

> Code samples

```shell
# You can also use wget
curl -X POST https://waas.inbl-dev.site/api/waas/v1/nfts/-/withdrawals/{transactionDisplayId}/replace-fee \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'x-api-key: API_KEY'

```

```java
URL obj = new URL("https://waas.inbl-dev.site/api/waas/v1/nfts/-/withdrawals/{transactionDisplayId}/replace-fee");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```javascript
const inputBody = '{
  "accelerateFee": 0.0001
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'x-api-key':'API_KEY'
};

fetch('https://waas.inbl-dev.site/api/waas/v1/nfts/-/withdrawals/{transactionDisplayId}/replace-fee',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'x-api-key' => 'API_KEY'
}

result = RestClient.post 'https://waas.inbl-dev.site/api/waas/v1/nfts/-/withdrawals/{transactionDisplayId}/replace-fee',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'x-api-key' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','https://waas.inbl-dev.site/api/waas/v1/nfts/-/withdrawals/{transactionDisplayId}/replace-fee', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'x-api-key': 'API_KEY'
}

r = requests.post('https://waas.inbl-dev.site/api/waas/v1/nfts/-/withdrawals/{transactionDisplayId}/replace-fee', headers = headers)

print(r.json())

```

`POST /api/waas/v1/nfts/-/withdrawals/{transactionDisplayId}/replace-fee`

네트워크 수수료를 재설정합니다.

> Body parameter

```json
{
  "accelerateFee": 0.0001
}
```

<h3 id="7.6-네트워크-수수료-재설정-parameters">Parameters</h3>

|Name|In|Type|Required|Description|Examples|
|---|---|---|---|---|---|
|transactionDisplayId|path|string|true|트랜잭션 ID|b0797a66-37d3-4d88-8351-7810c6561858|
|body|body|[자산 출금 수수료 재설정 요청](#schema자산 출금 수수료 재설정 요청)|true|none|none|

> Example responses

> 400 Response

```json
{
  "error": "string",
  "message": "string",
  "data": "string"
}
```

<h3 id="7.6-네트워크-수수료-재설정-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[ErrorResDTO](#schemaerrorresdto)|

<h3 id="7.6-네트워크-수수료-재설정-responseschema">Response Schema</h3>

## 7.7 NFT 전체 입출금 현황 조회

<a id="opIdgetTransactions"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://waas.inbl-dev.site/api/waas/v1/nft-transactions \
  -H 'Accept: application/json' \
  -H 'x-api-key: API_KEY'

```

```java
URL obj = new URL("https://waas.inbl-dev.site/api/waas/v1/nft-transactions");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-api-key':'API_KEY'
};

fetch('https://waas.inbl-dev.site/api/waas/v1/nft-transactions',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-api-key' => 'API_KEY'
}

result = RestClient.get 'https://waas.inbl-dev.site/api/waas/v1/nft-transactions',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-api-key' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://waas.inbl-dev.site/api/waas/v1/nft-transactions', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-api-key': 'API_KEY'
}

r = requests.get('https://waas.inbl-dev.site/api/waas/v1/nft-transactions', headers = headers)

print(r.json())

```

`GET /api/waas/v1/nft-transactions`

NFT 입출금 전체 목록을 조회합니다.

<h3 id="7.7-nft-전체-입출금-현황-조회-parameters">Parameters</h3>

|Name|In|Type|Required|Description|Examples|
|---|---|---|---|---|---|
|walletType|query|string|false|지갑 종류|HOT|
|walletName|query|string|false|지갑 이름|사내용|
|address|query|string|false|주소|0xD3|
|transactionHash|query|string|false|트랜잭션 해시값|0xb43d6ec31|
|contractAddress|query|string|false|컨트랙트 주소|ad3Q|
|contractName|query|string|false|컨트랙트 이름|JINUNF7|
|startDt|query|string(yyyy-MM-dd HH:mm:ss)|false|트랜잭션 발생 시작일|2024-04-10 12:35:10|
|endDt|query|string(yyyy-MM-dd HH:mm:ss)|false|트랜잭션 발생 종료일|2024-04-25 07:31:45|
|statuses|query|array[string]|false|트랜잭션 상태|none|
|page|query|int|false|페이지 번호|2|
|size|query|int|false|페이지 크기|15|
|sort|query|string|false|정렬 기준|TRANSACTION_UPDATED_DT,DESC|

#### Enumerated Values

|Parameter|Value|
|---|---|
|walletType|HOT|
|walletType|COLD|
|statuses|WITHDRAW_WAIT|
|statuses|WITHDRAW_IN_PROGRESS|
|statuses|WITHDRAW_CANCEL|
|statuses|WITHDRAW_FAIL|
|statuses|WITHDRAW_COMPLETE|
|statuses|DEPOSIT_COMPLETE|

> Example responses

> 200 Response

```json
{
  "count": 4,
  "nftTransactions": [
    {
      "transactionDisplayId": "958b197a-c774-48c1-a391-8836db8813ba",
      "walletName": "사내용 지갑",
      "nftName": "29",
      "symbol": "JINU",
      "network": "holesky",
      "type": "WITHDRAW",
      "stat": "COMPLETE_WITHDRAW",
      "transactionHash": "0xadcbfac94920d2552ffc521711b634b473cf23551423344ff7f163c723580dbd",
      "amount": 1,
      "fee": 0.000096178991457065,
      "usdToKrw": 1380.6,
      "amountKrw": 0,
      "feeKrw": 434,
      "completedAt": "2019-08-24T14:15:22Z",
      "counterparties": [
        {
          "address": "0x9F1229D97F17BB45f4598195B36b667b01Bc6495",
          "dstTag": "string",
          "amount": 0.001
        }
      ]
    }
  ]
}
```

<h3 id="7.7-nft-전체-입출금-현황-조회-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[NFT 트랜잭션 리스트 조회 응답](#schemanft 트랜잭션 리스트 조회 응답)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[ErrorResDTO](#schemaerrorresdto)|

<h3 id="7.7-nft-전체-입출금-현황-조회-responseschema">Response Schema</h3>

## 7.8 NFT 입출금 상세 정보 조회

<a id="opIdgetTransaction"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://waas.inbl-dev.site/api/waas/v1/nft-transactions/{transactionDisplayId} \
  -H 'Accept: application/json' \
  -H 'x-api-key: API_KEY'

```

```java
URL obj = new URL("https://waas.inbl-dev.site/api/waas/v1/nft-transactions/{transactionDisplayId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```javascript

const headers = {
  'Accept':'application/json',
  'x-api-key':'API_KEY'
};

fetch('https://waas.inbl-dev.site/api/waas/v1/nft-transactions/{transactionDisplayId}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'x-api-key' => 'API_KEY'
}

result = RestClient.get 'https://waas.inbl-dev.site/api/waas/v1/nft-transactions/{transactionDisplayId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'x-api-key' => 'API_KEY',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://waas.inbl-dev.site/api/waas/v1/nft-transactions/{transactionDisplayId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'x-api-key': 'API_KEY'
}

r = requests.get('https://waas.inbl-dev.site/api/waas/v1/nft-transactions/{transactionDisplayId}', headers = headers)

print(r.json())

```

`GET /api/waas/v1/nft-transactions/{transactionDisplayId}`

특정 NFT 입출금건을 상세 정보를 조회합니다.

<h3 id="7.8-nft-입출금-상세-정보-조회-parameters">Parameters</h3>

|Name|In|Type|Required|Description|Examples|
|---|---|---|---|---|---|
|transactionDisplayId|path|string|true|트랜잭션 ID|b9fa192c-56c5-4cf2-a8ac-d65fd94bbc73|

> Example responses

> 200 Response

```json
{
  "transactionDisplayId": "958b197a-c774-48c1-a391-8836db8813ba",
  "walletName": "사내용 지갑",
  "nftName": "29",
  "symbol": "JINU",
  "network": "holesky",
  "type": "WITHDRAW",
  "stat": "COMPLETE_WITHDRAW",
  "transactionHash": "0xadcbfac94920d2552ffc521711b634b473cf23551423344ff7f163c723580dbd",
  "amount": 1,
  "fee": 0.000096178991457065,
  "usdToKrw": 1380.6,
  "amountKrw": 0,
  "feeKrw": 434,
  "completedAt": "2019-08-24T14:15:22Z",
  "counterparties": [
    {
      "address": "0x9F1229D97F17BB45f4598195B36b667b01Bc6495",
      "dstTag": "string",
      "amount": 0.001
    }
  ]
}
```

<h3 id="7.8-nft-입출금-상세-정보-조회-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[NFT 트랜잭션 조회 응답](#schemanft 트랜잭션 조회 응답)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[ErrorResDTO](#schemaerrorresdto)|

<h3 id="7.8-nft-입출금-상세-정보-조회-responseschema">Response Schema</h3>

# Schemas

<h2 id="tocS_ErrorResDTO">ErrorResDTO</h2>

<a id="schemaerrorresdto"></a>
<a id="schema_ErrorResDTO"></a>
<a id="tocSerrorresdto"></a>
<a id="tocserrorresdto"></a>

```json
{
  "error": "string",
  "message": "string",
  "data": "string"
}

```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|error|string|false|none|
|message|string|false|none|
|data|string|false|none|

<h2 id="tocS_지갑 생성 요청">지갑 생성 요청</h2>

<a id="schema지갑 생성 요청"></a>
<a id="schema_지갑 생성 요청"></a>
<a id="tocS지갑 생성 요청"></a>
<a id="tocs지갑 생성 요청"></a>

```json
{
  "walletName": "이더리움 지갑2",
  "coinDisplayId": [
    "8130e0f5-64b6-48c0-a10c-1d1d668810e5"
  ],
  "isMainnet": true
}

```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|walletName|string(숫자/영문/한글 가능, 최대 20자)|true|지갑 명|
|coinDisplayId|[string]|true|none|
|isMainnet|boolean|true|메인넷 여부|

<h2 id="tocS_지갑 변경 요청">지갑 변경 요청</h2>

<a id="schema지갑 변경 요청"></a>
<a id="schema_지갑 변경 요청"></a>
<a id="tocS지갑 변경 요청"></a>
<a id="tocs지갑 변경 요청"></a>

```json
{
  "walletName": "이더리움 지갑2",
  "status": "STOP",
  "description": "이더리움 지갑 ( 사내용 )"
}

```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|walletName|string(숫자/영문/한글 가능, 최대 20자)|false|지갑 명|
|status|string|false|변경할 지갑 상태|
|description|string|false|지갑 설명|

#### Enumerated Values

|Property|Value|
|---|---|
|status|ACTIVATED|
|status|STOP|
|status|DELETED|
|status|COLD_WAIT|
|status|LOCKUP|

<h2 id="tocS_자산 추가 요청">자산 추가 요청</h2>

<a id="schema자산 추가 요청"></a>
<a id="schema_자산 추가 요청"></a>
<a id="tocS자산 추가 요청"></a>
<a id="tocs자산 추가 요청"></a>

```json
{
  "coinDisplayIds": [
    "9dae86ce-958e-47bb-9681-ae5e8e91c48d"
  ]
}

```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|coinDisplayIds|[string]|true|none|

<h2 id="tocS_주소 생성 요청">주소 생성 요청</h2>

<a id="schema주소 생성 요청"></a>
<a id="schema_주소 생성 요청"></a>
<a id="tocS주소 생성 요청"></a>
<a id="tocs주소 생성 요청"></a>

```json
{
  "chainDisplayIds": [
    "a3836ad6-d507-4960-a1c8-78c4909db3f4"
  ]
}

```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|chainDisplayIds|[string]|true|none|

<h2 id="tocS_NFT 입금 받을 주소 요청">NFT 입금 받을 주소 요청</h2>

<a id="schemanft 입금 받을 주소 요청"></a>
<a id="schema_NFT 입금 받을 주소 요청"></a>
<a id="tocSnft 입금 받을 주소 요청"></a>
<a id="tocsnft 입금 받을 주소 요청"></a>

```json
{
  "address": "0x705C4c94B0440a19Fd0C4805ED3b5631E923384d",
  "dstTag": "string",
  "amount": 0.0045
}

```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|address|string|true|입금 받을 주소|
|dstTag|string|false|입금 받을 주소 태그|
|amount|number|true|입금 양|

<h2 id="tocS_NFT 출금 신청 요청">NFT 출금 신청 요청</h2>

<a id="schemanft 출금 신청 요청"></a>
<a id="schema_NFT 출금 신청 요청"></a>
<a id="tocSnft 출금 신청 요청"></a>
<a id="tocsnft 출금 신청 요청"></a>

```json
{
  "depositAddresses": [
    {
      "address": "0x705C4c94B0440a19Fd0C4805ED3b5631E923384d",
      "dstTag": "string",
      "amount": 0.0045
    }
  ],
  "memo": "피자 값",
  "feePriority": "FAST"
}

```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|depositAddresses|[[NFT 입금 받을 주소 요청](#schemanft 입금 받을 주소 요청)]|true|none|
|memo|string|false|출금 신청 메모|
|feePriority|string|true|수수료|

#### Enumerated Values

|Property|Value|
|---|---|
|feePriority|FAST|
|feePriority|SLOW|
|feePriority|STANDARD|

<h2 id="tocS_NFT 출금 수수료 조회 요청">NFT 출금 수수료 조회 요청</h2>

<a id="schemanft 출금 수수료 조회 요청"></a>
<a id="schema_NFT 출금 수수료 조회 요청"></a>
<a id="tocSnft 출금 수수료 조회 요청"></a>
<a id="tocsnft 출금 수수료 조회 요청"></a>

```json
{
  "counterparties": [
    {
      "address": "0x705C4c94B0440a19Fd0C4805ED3b5631E923384d",
      "dstTag": "string",
      "amount": 0.0045
    }
  ]
}

```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|counterparties|[[NFT 출금 수수료 조회할 입금 정보](#schemanft 출금 수수료 조회할 입금 정보)]|true|none|

<h2 id="tocS_NFT 출금 수수료 조회할 입금 정보">NFT 출금 수수료 조회할 입금 정보</h2>

<a id="schemanft 출금 수수료 조회할 입금 정보"></a>
<a id="schema_NFT 출금 수수료 조회할 입금 정보"></a>
<a id="tocSnft 출금 수수료 조회할 입금 정보"></a>
<a id="tocsnft 출금 수수료 조회할 입금 정보"></a>

```json
{
  "address": "0x705C4c94B0440a19Fd0C4805ED3b5631E923384d",
  "dstTag": "string",
  "amount": 0.0045
}

```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|address|string|true|입금 받을 주소|
|dstTag|string|false|입금 받을 주소 태그|
|amount|number|true|입금 양|

<h2 id="tocS_자산 출금 수수료 조회 응답">자산 출금 수수료 조회 응답</h2>

<a id="schema자산 출금 수수료 조회 응답"></a>
<a id="schema_자산 출금 수수료 조회 응답"></a>
<a id="tocS자산 출금 수수료 조회 응답"></a>
<a id="tocs자산 출금 수수료 조회 응답"></a>

```json
{
  "fast": 0.000085978712308125,
  "standard": 0.000085978712308125,
  "slow": 0.000085978712308125
}

```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|fast|number|false|FAST 수수료(개)|
|standard|number|false|STANDARD 수수료(개)|
|slow|number|false|SLOW 수수료(개)|

<h2 id="tocS_자산 출금 수수료 재설정 요청">자산 출금 수수료 재설정 요청</h2>

<a id="schema자산 출금 수수료 재설정 요청"></a>
<a id="schema_자산 출금 수수료 재설정 요청"></a>
<a id="tocS자산 출금 수수료 재설정 요청"></a>
<a id="tocs자산 출금 수수료 재설정 요청"></a>

```json
{
  "accelerateFee": 0.0001
}

```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|accelerateFee|number|true|자산 출금 수수료 재설정 요청|

<h2 id="tocS_자산 입금 받을 주소 요청">자산 입금 받을 주소 요청</h2>

<a id="schema자산 입금 받을 주소 요청"></a>
<a id="schema_자산 입금 받을 주소 요청"></a>
<a id="tocS자산 입금 받을 주소 요청"></a>
<a id="tocs자산 입금 받을 주소 요청"></a>

```json
{
  "address": "0x705C4c94B0440a19Fd0C4805ED3b5631E923384d",
  "dstTag": "string",
  "amount": 0.0045
}

```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|address|string|true|입금 받을 주소|
|dstTag|string|false|입금 받을 주소 태그|
|amount|number|true|입금 양|

<h2 id="tocS_자산 출금 신청 요청">자산 출금 신청 요청</h2>

<a id="schema자산 출금 신청 요청"></a>
<a id="schema_자산 출금 신청 요청"></a>
<a id="tocS자산 출금 신청 요청"></a>
<a id="tocs자산 출금 신청 요청"></a>

```json
{
  "depositAddresses": [
    {
      "address": "0x705C4c94B0440a19Fd0C4805ED3b5631E923384d",
      "dstTag": "string",
      "amount": 0.0045
    }
  ],
  "memo": "피자 값",
  "feePriority": "FAST"
}

```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|depositAddresses|[[자산 입금 받을 주소 요청](#schema자산 입금 받을 주소 요청)]|true|none|
|memo|string|false|출금 신청 메모|
|feePriority|string|true|수수료|

#### Enumerated Values

|Property|Value|
|---|---|
|feePriority|FAST|
|feePriority|SLOW|
|feePriority|STANDARD|

<h2 id="tocS_자산 출금 수수료 조회 요청">자산 출금 수수료 조회 요청</h2>

<a id="schema자산 출금 수수료 조회 요청"></a>
<a id="schema_자산 출금 수수료 조회 요청"></a>
<a id="tocS자산 출금 수수료 조회 요청"></a>
<a id="tocs자산 출금 수수료 조회 요청"></a>

```json
{
  "counterparties": [
    {
      "address": "0x705C4c94B0440a19Fd0C4805ED3b5631E923384d",
      "dstTag": "string",
      "amount": 0.0045
    }
  ]
}

```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|counterparties|[[자산 출금 수수료 조회할 입금 정보](#schema자산 출금 수수료 조회할 입금 정보)]|true|none|

<h2 id="tocS_자산 출금 수수료 조회할 입금 정보">자산 출금 수수료 조회할 입금 정보</h2>

<a id="schema자산 출금 수수료 조회할 입금 정보"></a>
<a id="schema_자산 출금 수수료 조회할 입금 정보"></a>
<a id="tocS자산 출금 수수료 조회할 입금 정보"></a>
<a id="tocs자산 출금 수수료 조회할 입금 정보"></a>

```json
{
  "address": "0x705C4c94B0440a19Fd0C4805ED3b5631E923384d",
  "dstTag": "string",
  "amount": 0.0045
}

```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|address|string|true|입금 받을 주소|
|dstTag|string|false|입금 받을 주소 태그|
|amount|number|true|입금 양|

<h2 id="tocS_자산 조회 응답">자산 조회 응답</h2>

<a id="schema자산 조회 응답"></a>
<a id="schema_자산 조회 응답"></a>
<a id="tocS자산 조회 응답"></a>
<a id="tocs자산 조회 응답"></a>

```json
{
  "assetDisplayId": "9c6dc0cc-c4a5-4a12-9c1f-1330621f8abb",
  "koreanName": "이더리움",
  "englishName": "Ethereum",
  "symbol": "ETH",
  "networkName": "이더리움 holesky 테스트넷",
  "totalVolume": 0.33,
  "withdrawableVolume": 0.134,
  "krwPrice": 4157141.637500035
}

```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|assetDisplayId|string|false|자산 ID|
|koreanName|string|false|자산 한글명|
|englishName|string|false|자산 영문명|
|symbol|string|false|자산 심볼|
|networkName|string|false|자산 네트워크 명|
|totalVolume|number|false|자산 총 양|
|withdrawableVolume|number|false|자산 출금 가능 양|
|krwPrice|number(double)|false|자산 원화 가격|

<h2 id="tocS_주소 조회 응답">주소 조회 응답</h2>

<a id="schema주소 조회 응답"></a>
<a id="schema_주소 조회 응답"></a>
<a id="tocS주소 조회 응답"></a>
<a id="tocs주소 조회 응답"></a>

```json
{
  "addressDisplayId": "4b5fd0fd-34ab-4039-8fec-922560c5d130",
  "address": "0x4C9F7a11D789A0ed2623d4D83614dDe80bdCF16B",
  "totalKrwBalance": 384710,
  "withdrawableKrwBalance": 78390,
  "assets": [
    {
      "assetDisplayId": "9c6dc0cc-c4a5-4a12-9c1f-1330621f8abb",
      "koreanName": "이더리움",
      "englishName": "Ethereum",
      "symbol": "ETH",
      "networkName": "이더리움 holesky 테스트넷",
      "totalVolume": 0.33,
      "withdrawableVolume": 0.134,
      "krwPrice": 4157141.637500035
    }
  ]
}

```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|addressDisplayId|string|false|주소 ID|
|address|string|false|주소|
|totalKrwBalance|integer|false|주소 원화 가치|
|withdrawableKrwBalance|integer|false|주소 출금 가능 원화 가치|
|assets|[[자산 조회 응답](#schema자산 조회 응답)]|false|none|

<h2 id="tocS_지갑 조회 리스트 응답">지갑 조회 리스트 응답</h2>

<a id="schema지갑 조회 리스트 응답"></a>
<a id="schema_지갑 조회 리스트 응답"></a>
<a id="tocS지갑 조회 리스트 응답"></a>
<a id="tocs지갑 조회 리스트 응답"></a>

```json
{
  "count": 1,
  "wallets": [
    {
      "walletDisplayId": "00478460-b277-455f-94d9-c370d2b9c929",
      "walletName": "이더리움홀스키지갑",
      "krwAmount": 3861940,
      "status": "ACTIVATED",
      "addresses": [
        {
          "addressDisplayId": "4b5fd0fd-34ab-4039-8fec-922560c5d130",
          "address": "0x4C9F7a11D789A0ed2623d4D83614dDe80bdCF16B",
          "totalKrwBalance": 384710,
          "withdrawableKrwBalance": 78390,
          "assets": [
            {}
          ]
        }
      ],
      "createdAt": "2019-08-24T14:15:22Z",
      "updatedAt": "2019-08-24T14:15:22Z",
      "deletedAt": "2019-08-24T14:15:22Z"
    }
  ]
}

```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|count|integer(int64)|false|지갑 개수|
|wallets|[[지갑 조회 응답](#schema지갑 조회 응답)]|false|none|

<h2 id="tocS_지갑 조회 응답">지갑 조회 응답</h2>

<a id="schema지갑 조회 응답"></a>
<a id="schema_지갑 조회 응답"></a>
<a id="tocS지갑 조회 응답"></a>
<a id="tocs지갑 조회 응답"></a>

```json
{
  "walletDisplayId": "00478460-b277-455f-94d9-c370d2b9c929",
  "walletName": "이더리움홀스키지갑",
  "krwAmount": 3861940,
  "status": "ACTIVATED",
  "addresses": [
    {
      "addressDisplayId": "4b5fd0fd-34ab-4039-8fec-922560c5d130",
      "address": "0x4C9F7a11D789A0ed2623d4D83614dDe80bdCF16B",
      "totalKrwBalance": 384710,
      "withdrawableKrwBalance": 78390,
      "assets": [
        {
          "assetDisplayId": "9c6dc0cc-c4a5-4a12-9c1f-1330621f8abb",
          "koreanName": "이더리움",
          "englishName": "Ethereum",
          "symbol": "ETH",
          "networkName": "이더리움 holesky 테스트넷",
          "totalVolume": 0.33,
          "withdrawableVolume": 0.134,
          "krwPrice": 4157141.637500035
        }
      ]
    }
  ],
  "createdAt": "2019-08-24T14:15:22Z",
  "updatedAt": "2019-08-24T14:15:22Z",
  "deletedAt": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|walletDisplayId|string|false|지갑 ID|
|walletName|string|false|지갑 명|
|krwAmount|integer|false|지갑 원화 가치|
|status|string|false|지갑 상태|
|addresses|[[주소 조회 응답](#schema주소 조회 응답)]|false|none|
|createdAt|string(date-time)|false|지갑 생성 일시|
|updatedAt|string(date-time)|false|지갑 변경 일시|
|deletedAt|string(date-time)|false|지갑 삭제 일시|

#### Enumerated Values

|Property|Value|
|---|---|
|status|ACTIVATED|
|status|STOP|
|status|DELETED|
|status|COLD_WAIT|
|status|LOCKUP|

<h2 id="tocS_코인 별 원화 기준 자산 비중 응답">코인 별 원화 기준 자산 비중 응답</h2>

<a id="schema코인 별 원화 기준 자산 비중 응답"></a>
<a id="schema_코인 별 원화 기준 자산 비중 응답"></a>
<a id="tocS코인 별 원화 기준 자산 비중 응답"></a>
<a id="tocs코인 별 원화 기준 자산 비중 응답"></a>

```json
{
  "coinDisplayId": "3b907b85-9ab9-4a88-85c3-d052b5386c39",
  "coinKoreanName": "이더리움",
  "coinEnglishName": "Ethereum",
  "symbol": "ETH",
  "networkName": "holesky",
  "balance": 0.3343,
  "krwAmount": 18473.54,
  "percentage": 38.31
}

```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|coinDisplayId|string|false|코인 ID|
|coinKoreanName|string|false|코인 한글명|
|coinEnglishName|string|false|코인 영문명|
|symbol|string|false|코인 심볼|
|networkName|string|false|네트워크명|
|balance|number|false|코인 양|
|krwAmount|number|false|자산 코인 원화 가치|
|percentage|number|false|자산 코인 비중|

<h2 id="tocS_주소 리스트 조회 응답">주소 리스트 조회 응답</h2>

<a id="schema주소 리스트 조회 응답"></a>
<a id="schema_주소 리스트 조회 응답"></a>
<a id="tocS주소 리스트 조회 응답"></a>
<a id="tocs주소 리스트 조회 응답"></a>

```json
{
  "count": 0,
  "addresses": [
    {
      "addressDisplayId": "4b5fd0fd-34ab-4039-8fec-922560c5d130",
      "address": "0x4C9F7a11D789A0ed2623d4D83614dDe80bdCF16B",
      "totalKrwBalance": 384710,
      "withdrawableKrwBalance": 78390,
      "assets": [
        {
          "assetDisplayId": "9c6dc0cc-c4a5-4a12-9c1f-1330621f8abb",
          "koreanName": "이더리움",
          "englishName": "Ethereum",
          "symbol": "ETH",
          "networkName": "이더리움 holesky 테스트넷",
          "totalVolume": 0.33,
          "withdrawableVolume": 0.134,
          "krwPrice": 4157141.637500035
        }
      ]
    }
  ]
}

```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|count|integer(int64)|false|주소 개수|
|addresses|[[주소 조회 응답](#schema주소 조회 응답)]|false|none|

<h2 id="tocS_NFT 리스트 조회 응답">NFT 리스트 조회 응답</h2>

<a id="schemanft 리스트 조회 응답"></a>
<a id="schema_NFT 리스트 조회 응답"></a>
<a id="tocSnft 리스트 조회 응답"></a>
<a id="tocsnft 리스트 조회 응답"></a>

```json
{
  "count": 3,
  "nfts": [
    {
      "nftDisplayId": "8472572f-8c99-4e5e-8c0c-8066ba8f7bb8",
      "koreanName": "29",
      "addressDisplayId": "b5d3cbdf-42d8-4b5f-96b4-9ffcd7850f6a",
      "walletName": "첫번째 지갑",
      "standard": "ERC-721",
      "contractAddress": "0xad34a40cee2df54e7669f2c3848237496717c099",
      "contractName": "JINUNFT",
      "symbol": "JINU",
      "tokenId": 29,
      "tokenName": "29",
      "totalVolume": 2,
      "withdrawableVolume": 1,
      "depositDt": "2019-08-24T14:15:22Z"
    }
  ]
}

```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|count|integer(int64)|false|NFT 개수|
|nfts|[[NFT 조회 응답](#schemanft 조회 응답)]|false|none|

<h2 id="tocS_NFT 조회 응답">NFT 조회 응답</h2>

<a id="schemanft 조회 응답"></a>
<a id="schema_NFT 조회 응답"></a>
<a id="tocSnft 조회 응답"></a>
<a id="tocsnft 조회 응답"></a>

```json
{
  "nftDisplayId": "8472572f-8c99-4e5e-8c0c-8066ba8f7bb8",
  "koreanName": "29",
  "addressDisplayId": "b5d3cbdf-42d8-4b5f-96b4-9ffcd7850f6a",
  "walletName": "첫번째 지갑",
  "standard": "ERC-721",
  "contractAddress": "0xad34a40cee2df54e7669f2c3848237496717c099",
  "contractName": "JINUNFT",
  "symbol": "JINU",
  "tokenId": 29,
  "tokenName": "29",
  "totalVolume": 2,
  "withdrawableVolume": 1,
  "depositDt": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|nftDisplayId|string|false|NFT ID|
|koreanName|string|false|NFT 명|
|addressDisplayId|string|false|주소 ID|
|walletName|string|false|지갑 명|
|standard|string|false|표준|
|contractAddress|string|false|컨트랙트 주소|
|contractName|string|false|컨트랙트 명|
|symbol|string|false|심볼|
|tokenId|integer(int64)|false|토큰 아이디|
|tokenName|string|false|토큰 명|
|totalVolume|number|false|총 개수|
|withdrawableVolume|number|false|출금 가능 개수|
|depositDt|string(date-time)|false|입금 날짜|

<h2 id="tocS_NFT 트랜잭션 리스트 조회 응답">NFT 트랜잭션 리스트 조회 응답</h2>

<a id="schemanft 트랜잭션 리스트 조회 응답"></a>
<a id="schema_NFT 트랜잭션 리스트 조회 응답"></a>
<a id="tocSnft 트랜잭션 리스트 조회 응답"></a>
<a id="tocsnft 트랜잭션 리스트 조회 응답"></a>

```json
{
  "count": 4,
  "nftTransactions": [
    {
      "transactionDisplayId": "958b197a-c774-48c1-a391-8836db8813ba",
      "walletName": "사내용 지갑",
      "nftName": "29",
      "symbol": "JINU",
      "network": "holesky",
      "type": "WITHDRAW",
      "stat": "COMPLETE_WITHDRAW",
      "transactionHash": "0xadcbfac94920d2552ffc521711b634b473cf23551423344ff7f163c723580dbd",
      "amount": 1,
      "fee": 0.000096178991457065,
      "usdToKrw": 1380.6,
      "amountKrw": 0,
      "feeKrw": 434,
      "completedAt": "2019-08-24T14:15:22Z",
      "counterparties": [
        {
          "address": "0x9F1229D97F17BB45f4598195B36b667b01Bc6495",
          "dstTag": "string",
          "amount": 0.001
        }
      ]
    }
  ]
}

```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|count|integer(int64)|false|트랜잭션 개수|
|nftTransactions|[[NFT 트랜잭션 조회 응답](#schemanft 트랜잭션 조회 응답)]|false|none|

<h2 id="tocS_NFT 트랜잭션 조회 응답">NFT 트랜잭션 조회 응답</h2>

<a id="schemanft 트랜잭션 조회 응답"></a>
<a id="schema_NFT 트랜잭션 조회 응답"></a>
<a id="tocSnft 트랜잭션 조회 응답"></a>
<a id="tocsnft 트랜잭션 조회 응답"></a>

```json
{
  "transactionDisplayId": "958b197a-c774-48c1-a391-8836db8813ba",
  "walletName": "사내용 지갑",
  "nftName": "29",
  "symbol": "JINU",
  "network": "holesky",
  "type": "WITHDRAW",
  "stat": "COMPLETE_WITHDRAW",
  "transactionHash": "0xadcbfac94920d2552ffc521711b634b473cf23551423344ff7f163c723580dbd",
  "amount": 1,
  "fee": 0.000096178991457065,
  "usdToKrw": 1380.6,
  "amountKrw": 0,
  "feeKrw": 434,
  "completedAt": "2019-08-24T14:15:22Z",
  "counterparties": [
    {
      "address": "0x9F1229D97F17BB45f4598195B36b667b01Bc6495",
      "dstTag": "string",
      "amount": 0.001
    }
  ]
}

```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|transactionDisplayId|string|false|트랜잭션 ID|
|walletName|string|false|지갑 명|
|nftName|string|false|NFT 명|
|symbol|string|false|NFT 심볼|
|network|string|false|네트워크|
|type|string|false|입/출금|
|stat|string|false|트랜잭션 상태|
|transactionHash|string|false|트랜잭션 해시값|
|amount|number|false|입/출금 양|
|fee|number|false|입/출금 수수료|
|usdToKrw|number(double)|false|입/출금 시 달러 환율 (원)|
|amountKrw|integer|false|입/출금 원화 가치|
|feeKrw|integer|false|입/출금 수수료 원화 가치|
|completedAt|string(date-time)|false|트랜잭션 생성시간|
|counterparties|[[자산 트랜잭션 상대방 정보](#schema자산 트랜잭션 상대방 정보)]|false|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|DEPOSIT|
|type|WITHDRAW|
|stat|WAIT_APPROVAL|
|stat|CANCEL_WITHDRAW|
|stat|APPROVAL_WITHDRAW|
|stat|REJECT_WITHDRAW|
|stat|DELAY_WITHDRAW|
|stat|EXECUTE_WITHDRAW|
|stat|COMPLETE_WITHDRAW|
|stat|FAIL_WITHDRAW|
|stat|CANCEL_FORCE_WITHDRAW|
|stat|COMPLETE_DEPOSIT|
|stat|PENDING_DEPOSIT|
|stat|FAILED_DEPOSIT|
|stat|REJECT_DEPOSIT|

<h2 id="tocS_자산 트랜잭션 상대방 정보">자산 트랜잭션 상대방 정보</h2>

<a id="schema자산 트랜잭션 상대방 정보"></a>
<a id="schema_자산 트랜잭션 상대방 정보"></a>
<a id="tocS자산 트랜잭션 상대방 정보"></a>
<a id="tocs자산 트랜잭션 상대방 정보"></a>

```json
{
  "address": "0x9F1229D97F17BB45f4598195B36b667b01Bc6495",
  "dstTag": "string",
  "amount": 0.001
}

```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|address|string|false|상대방 주소|
|dstTag|string|false|상대방 주소 태그|
|amount|number|false|입/출금 양|

<h2 id="tocS_지원네트워크 리스트 응답">지원네트워크 리스트 응답</h2>

<a id="schema지원네트워크 리스트 응답"></a>
<a id="schema_지원네트워크 리스트 응답"></a>
<a id="tocS지원네트워크 리스트 응답"></a>
<a id="tocs지원네트워크 리스트 응답"></a>

```json
{
  "count": 22,
  "networks": [
    {
      "networkName": "비트코인 메인넷",
      "chainDisplayId": "099590c1-dafb-4055-8f7d-d88995654bb2",
      "symbol": "BTC"
    }
  ]
}

```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|count|integer(int64)|false|전체 개수|
|networks|[[지원네트워크 응답](#schema지원네트워크 응답)]|false|none|

<h2 id="tocS_지원네트워크 응답">지원네트워크 응답</h2>

<a id="schema지원네트워크 응답"></a>
<a id="schema_지원네트워크 응답"></a>
<a id="tocS지원네트워크 응답"></a>
<a id="tocs지원네트워크 응답"></a>

```json
{
  "networkName": "비트코인 메인넷",
  "chainDisplayId": "099590c1-dafb-4055-8f7d-d88995654bb2",
  "symbol": "BTC"
}

```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|networkName|string|false|지원네트워크 이름|
|chainDisplayId|string|false|지원네트워크 ID|
|symbol|string|false|지원네트워크 심볼|

<h2 id="tocS_코인 목록 조회 요청">코인 목록 조회 요청</h2>

<a id="schema코인 목록 조회 요청"></a>
<a id="schema_코인 목록 조회 요청"></a>
<a id="tocS코인 목록 조회 요청"></a>
<a id="tocs코인 목록 조회 요청"></a>

```json
{
  "isMainnet": true
}

```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|isMainnet|boolean|false|none|

<h2 id="tocS_코인별 원화 가격 응답">코인별 원화 가격 응답</h2>

<a id="schema코인별 원화 가격 응답"></a>
<a id="schema_코인별 원화 가격 응답"></a>
<a id="tocS코인별 원화 가격 응답"></a>
<a id="tocs코인별 원화 가격 응답"></a>

```json
{
  "coinDisplayId": "8130e0f5-64b6-48c0-a10c-1d1d668810e5",
  "koreanName": "이더리움",
  "englishName": "Ethereum",
  "symbol": "ETH",
  "networkName": "비트코인 메인넷",
  "web3NetworkName": "mainnet",
  "price": 4153947.3674999517
}

```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|coinDisplayId|string|false|코인 ID|
|koreanName|string|false|코인 한글명|
|englishName|string|false|코인 영문명|
|symbol|string|false|코인 심볼|
|networkName|string|false|지원네트워크 이름|
|web3NetworkName|string|false|지원네트워크 Web3 이름|
|price|number(double)|false|코인 원화 가격|

<h2 id="tocS_자산 트랜잭션 리스트 조회 응답">자산 트랜잭션 리스트 조회 응답</h2>

<a id="schema자산 트랜잭션 리스트 조회 응답"></a>
<a id="schema_자산 트랜잭션 리스트 조회 응답"></a>
<a id="tocS자산 트랜잭션 리스트 조회 응답"></a>
<a id="tocs자산 트랜잭션 리스트 조회 응답"></a>

```json
{
  "count": 53,
  "transactions": [
    {
      "transactionDisplayId": "b9fa192c-56c5-4cf2-a8ac-d65fd94bbc73",
      "walletName": "사내용 지갑",
      "coinName": "이더리움",
      "symbol": "ETH",
      "network": "HOLESKY",
      "type": "WITHDRAW",
      "stat": "COMPLETE_WITHDRAW",
      "transactionHash": "0xff257541bb08497180c6087acf822ad7ac0cb9b473eb8c1d183d80d826ca6fdb",
      "amount": 0.001,
      "fee": 0.000082355175273,
      "coinToUsd": 3254.4606600225,
      "usdToKrw": 1375.9,
      "amountKrw": 4496,
      "feeKrw": 368,
      "completedAt": "2019-08-24T14:15:22Z",
      "counterparties": [
        {
          "address": "0x9F1229D97F17BB45f4598195B36b667b01Bc6495",
          "dstTag": "string",
          "amount": 0.001
        }
      ]
    }
  ]
}

```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|count|integer(int64)|false|트랜잭션 개수|
|transactions|[[자산 트랜잭션 조회 응답](#schema자산 트랜잭션 조회 응답)]|false|none|

<h2 id="tocS_자산 트랜잭션 조회 응답">자산 트랜잭션 조회 응답</h2>

<a id="schema자산 트랜잭션 조회 응답"></a>
<a id="schema_자산 트랜잭션 조회 응답"></a>
<a id="tocS자산 트랜잭션 조회 응답"></a>
<a id="tocs자산 트랜잭션 조회 응답"></a>

```json
{
  "transactionDisplayId": "b9fa192c-56c5-4cf2-a8ac-d65fd94bbc73",
  "walletName": "사내용 지갑",
  "coinName": "이더리움",
  "symbol": "ETH",
  "network": "HOLESKY",
  "type": "WITHDRAW",
  "stat": "COMPLETE_WITHDRAW",
  "transactionHash": "0xff257541bb08497180c6087acf822ad7ac0cb9b473eb8c1d183d80d826ca6fdb",
  "amount": 0.001,
  "fee": 0.000082355175273,
  "coinToUsd": 3254.4606600225,
  "usdToKrw": 1375.9,
  "amountKrw": 4496,
  "feeKrw": 368,
  "completedAt": "2019-08-24T14:15:22Z",
  "counterparties": [
    {
      "address": "0x9F1229D97F17BB45f4598195B36b667b01Bc6495",
      "dstTag": "string",
      "amount": 0.001
    }
  ]
}

```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|transactionDisplayId|string|false|트랜잭션 ID|
|walletName|string|false|지갑 명|
|coinName|string|false|코인 명|
|symbol|string|false|코인 심볼|
|network|string|false|네트워크|
|type|string|false|입/출금|
|stat|string|false|트랜잭션 상태|
|transactionHash|string|false|트랜잭션 해시값|
|amount|number|false|입/출금 양|
|fee|number|false|입/출금 수수료|
|coinToUsd|number(double)|false|입/출금 시 코인 환율 (달러)|
|usdToKrw|number(double)|false|입/출금 시 달러 환율 (원)|
|amountKrw|integer|false|입/출금 원화 가치|
|feeKrw|integer|false|입/출금 수수료 원화 가치|
|completedAt|string(date-time)|false|트랜잭션 생성시간|
|counterparties|[[자산 트랜잭션 상대방 정보](#schema자산 트랜잭션 상대방 정보)]|false|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|DEPOSIT|
|type|WITHDRAW|
|stat|WAIT_APPROVAL|
|stat|CANCEL_WITHDRAW|
|stat|APPROVAL_WITHDRAW|
|stat|REJECT_WITHDRAW|
|stat|DELAY_WITHDRAW|
|stat|EXECUTE_WITHDRAW|
|stat|COMPLETE_WITHDRAW|
|stat|FAIL_WITHDRAW|
|stat|CANCEL_FORCE_WITHDRAW|
|stat|COMPLETE_DEPOSIT|
|stat|PENDING_DEPOSIT|
|stat|FAILED_DEPOSIT|
|stat|REJECT_DEPOSIT|

