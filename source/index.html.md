---
title: Sample API v1
language_tabs:
  - ruby: Ruby
  - python: Python
  - java: Java
  - javascript: Javascript
language_clients:
  - ruby: ""
  - python: ""
  - java: ""
  - javascript: ""
toc_footers: []
includes: []
search: false
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: widdershins v4.0.1

---

<h1 id="sample-api">Sample API v1</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Base URLs:

* <a href="http://scoutquest-backend-service-staging.fundsmap.com">http://scoutquest-backend-service-staging.fundsmap.com</a>

# Authentication

- HTTP Authentication, scheme: basic

<h1 id="sample-api-admin-marketing-controller">admin-marketing-controller</h1>

---
title: API Reference

language_tabs: # must be one of https://github.com/rouge-ruby/rouge/wiki/List-of-supported-languages-and-lexers
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true

code_clipboard: true

meta:
  - name: description
    content: Documentation for the Kittn API
---

# Introduction

Welcome to the Kittn API! You can use our API to access Kittn API endpoints, which can get information on various cats, kittens, and breeds in our database.

We have language bindings in Shell, Ruby, Python, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/slatedocs/slate). Feel free to edit it and use it as a base for your own API's documentation.

# Authentication

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Instrument Update Messages

## Get Instrument Update Messages

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://scoutquest-backend-service-staging.fundsmap.com/api/v1/sqhive/instrumentUpdates" \
  -H "Authorization: meowmeowmeowte"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
{
    "content": [
        {
            "id": "589113564166804304",
            "title": "Amber Enterprises India Ltd",
            "description": "Restructuring",
            "content": "Intimation on pronouncement of the order dated 11 June 2024 (uploaded on website of Hon''ble NCLT on 13 June 2024) under first motion application bearing Company Application No. (CAA)67(MB)2024 ....",
            "scripDetails": {
                "bseScripCode": "540902",
                "scripName": "Amber Enterprises India Ltd",
                "bseTickr": "AMBER",
                "nseTickr": null,
                "isin": "INE371P01015"
            },
            "linkDetail": {
                "shortLink": "https://sqst.in/4PRQX"
            },
            "updateType": "CORPORATE_ANNOUNCEMENT",
            "creationTime": 1718292418,
            "lastUpdateTime": 1718292420,
            "filterCategory": "UNCLASSIFIED",
            "filterCategoryId": "-1"
        },
        {
            "id": "589113559821504865",
            "title": "Amber Enterprises India Ltd",
            "description": "Restructuring",
            "content": "Intimation on pronouncement of the order dated 11 June 2024 (uploaded on website of Hon''ble NCLT on 13 June 2024) under first motion application bearing Company Application No. (CAA)67(MB)2024 ....",
            "scripDetails": {
                "bseScripCode": "540902",
                "scripName": "Amber Enterprises India Ltd",
                "bseTickr": "AMBER",
                "nseTickr": null,
                "isin": "INE371P01015"
            },
            "linkDetail": {
                "shortLink": "https://sqst.in/SIKoq"
            },
            "updateType": "CORPORATE_ANNOUNCEMENT",
            "creationTime": 1718292417,
            "lastUpdateTime": 1718292419,
            "filterCategory": "UNCLASSIFIED",
            "filterCategoryId": "-1"
        },
        {
            "id": "589113551676169507",
            "title": "Paytm",
            "description": "Trending News - Business news: Paytm to focus on distribution of insurance products of other insurers | Biz highlights",
            "content": "Business Wrap: Here are the top developments of the day, Shares of Exide Industries Limited hit a record high on June 13 following company's Rs 75 crore investment in EESL. Soon after taking over as the aviation minister, Ram Mohan Naidu announced his commitment to ensuring more affordable airfares for domestic flights. Watch for more!",
            "scripDetails": {
                "bseScripCode": "543396",
                "scripName": "Paytm",
                "bseTickr": "PAYTM",
                "nseTickr": null,
                "isin": "INE982J01020"
            },
            "linkDetail": {
                "shortLink": "https://sqst.in/e31EG"
            },
            "updateType": "GENERAL_NEWS",
            "creationTime": 1718292415,
            "lastUpdateTime": 1718292417,
            "filterCategory": "MEDIA_COVERAGE",
            "filterCategoryId": "scrape_moneycontrol_news_business_companies"
        }
    ],
    "pageable": {
        "sort": {
            "empty": false,
            "sorted": true,
            "unsorted": false
        },
        "offset": 0,
        "pageNumber": 0,
        "pageSize": 3,
        "paged": true,
        "unpaged": false
    },
    "last": false,
    "totalElements": 347207,
    "totalPages": 115736,
    "size": 3,
    "number": 0,
    "sort": {
        "empty": false,
        "sorted": true,
        "unsorted": false
    },
    "first": true,
    "numberOfElements": 3,
    "empty": false
}
```

This endpoint retrieves all instrument updates fittng your query description. Results are returned in paginated formate.

### HTTP Request

`GET http://scoutquest-backend-service-staging.fundsmap.com/api/v1/sqhive/instrumentUpdates`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
pageNo | 0 | change pageNo for next set of results fitting your query description
pageSize | 200 | No of results to be returned in a single page. You can fetch more results by calling for the next `pageNo`. Maximum value of `pageSize` is 1000
sortDirection | DESC | Direction for the sorting of messages wth respect to the time when the message was created. `DESC` will return the results with the latest update messages at the top. Possible values (`ASC`, `DESC`)
fromTime | - | Used when you need updates within a time range. `toTime` query must also be present if `fromTime` is mentioned
toTime | - | Used when you need updates within a time range. `fromTime` query must also be present if `toTime` is mentioned
messageId | - | Used to fetch all messages created after a `messageId`. Useful when you have processed messages uptil a certain message and now need to process messages after it. `expression` query parameter is control this behaviour. If `expression` value is not passed, By default all messages after a message are returned i.e. `expression` will be considered to be GT.
expression | - | Used in conjuction with `messageId`. Controls the behviour of wether you want to get messages created after a given `messageId` or before. Possible values: (`GT`,`GOE`,`LT`,`LOE`,`EQ`); GT = Greater Than, GOE = Greater Than or Equal to, LT = Lesser Than, LOE = Lesser Than or Equal to, EQ = Equal To. If value of `expression` is passed without `messageId` , it will be ignored.


<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Delete a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2" \
  -X DELETE \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete
