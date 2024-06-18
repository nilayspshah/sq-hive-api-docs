---
title: SQ Hive API Documentation
language_tabs:
  - shell: Shell 
  - ruby: Ruby
  - python: Python
  - java: Java
  - javascript: Javascript
language_clients:
  - shell: ""
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

# SQ Hive

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.


## Introduction
SQ Hive allows developers to access to capital market stock specific news at lightening speed via Webhooks and API. 

## Characteristics
Updates provided by us has the following characteristics:

|   |   |
|---|---|
|__Simple__| The language of our updates is simple as we strip out most of the jargon |
| __Relevant__ | Through our proprietry algorithms, We filter out most of the non-relevant news. |
| __Actionable__ | Updates provided by us are actionable |
|__Structured__| Based on the type of updates you can choose to define your handling. |
| __No Stock Left Behind__ | Updates are sent for all mainboard BSE listed entities. |
| __Comprehensive__ | Our bots listen to thousands of sources including Exchange websites, Conference Calls, Twitter, News Channels, Youtube and many more, providing a 360 degree update coverage.|
| __Realtime__ | All of the above is done and dissimenated to you at lighning speed. |

You can view [this short video](https://www.youtube.com/watch?v=s-pPlZ263Uc&ab_channel=ScoutQuestTV) to know more.

## How to recieve updates?
We provide 2 methods to recieve these updates. 
1. Webhooks
2. API

You can register an endpoint where you will recieve each update as and when it happens. Alternatively you can periodically poll for new updates via the API endpoint.

## How to use these updates?
How you use the updates is upto you. Examples of general use cases include - Sending these updates to your clients based on their holdings, Having a general/persionalised news feed on your website/app etc.
Use case is upto you, however it is mandatory to attribute ScoutQuest 

## What should be format for attribution?
1. Each Update should have a `Powered by ScoutQuest.in` text at the bottom of the message, where `ScoutQuest.in` should be clickable
2. For Each update the CTA / More Details Link should be the *shortLink* provided in the update message.

# API

## Base URLs:

Staging: <a href="http://scoutquest-backend-service-staging.fundsmap.com">http://scoutquest-backend-service-staging.fundsmap.com</a>

Live: <a href="http://scoutquest-backend-service-production.fundsmap.com">http://scoutquest-backend-service-production.fundsmap.com</a>


## Authentication

SQ Hive uses API keys to allow access to the API. You can request for an API Key by mailing to us at sq@fundsmap.com if its not already shared with you.

SQ Hive expects for the API key to be included in all API requests to the server in a header that looks like the following:

`x-api-key: yourapikeyhere`

<aside class="notice">
You must replace <code>yourapikeyhere</code> with your personal API key.
</aside>


## Get Instrument Update Messages

```ruby
require "uri"
require "net/http"

url = URI("http://scoutquest-backend-service-staging.fundsmap.com/hive/api/v1/instrumentUpdates/query?pageNo=0&pageSize=200&sortDirection=DESC")

http = Net::HTTP.new(url.host, url.port);
request = Net::HTTP::Get.new(url)
request["x-api-key"] = "yourapikeyhere"

response = http.request(request)
puts response.read_body

```

```python
import requests

defaultQuery = "http://scoutquest-backend-service-staging.fundsmap.com/hive/api/v1/instrumentUpdates/query?pageNo=0&pageSize=200&sortDirection=DESC"

timeRangeQuery = "http://scoutquest-backend-service-staging.fundsmap.com/hive/api/v1/instrumentUpdates/query?fromTime=1718709015&toTime=1718190615"

messageIdQuery = "http://scoutquest-backend-service-staging.fundsmap.com/hive/api/v1/instrumentUpdates/query?messageId=590860706281420591&expression=GT"

payload = {}
headers = {
  'x-api-key': 'yourapikeyhere'
}

response = requests.request("GET", url, headers=headers, data=payload)

print(response.text)

```

```shell
curl --location 'http://scoutquest-backend-service-staging.fundsmap.com/hive/api/v1/instrumentUpdates/query?pageNo=0&pageSize=200&sortDirection=DESC' \
--header 'x-api-key: yourapikeyhere'

curl --location 'http://scoutquest-backend-service-staging.fundsmap.com/hive/api/v1/instrumentUpdates/query?fromTime=1718709015&toTime=1718190615' \
--header 'x-api-key: yourapikeyhere'

curl --location 'http://scoutquest-backend-service-staging.fundsmap.com/hive/api/v1/instrumentUpdates/query?messageId=590860706281420591&expression=GT' \
--header 'x-api-key: yourapikeyhere'
```

```javascript
const axios = require('axios');

let config = {
  method: 'get',
  maxBodyLength: Infinity,
  url: 'http://scoutquest-backend-service-staging.fundsmap.com/hive/api/v1/instrumentUpdates/query?pageNo=0&pageSize=200&sortDirection=DESC',
  headers: { 
    'x-api-key': 'yourapikeyhere'
  }
};

axios.request(config)
.then((response) => {
  console.log(JSON.stringify(response.data));
})
.catch((error) => {
  console.log(error);
});

```

```java

OkHttpClient client = new OkHttpClient().newBuilder()
  .build();
MediaType mediaType = MediaType.parse("text/plain");
RequestBody body = RequestBody.create(mediaType, "");
Request request = new Request.Builder()
  .url("http://scoutquest-backend-service-staging.fundsmap.com/hive/api/v1/instrumentUpdates/query?pageNo=0&pageSize=200&sortDirection=DESC")
  .method("GET", body)
  .addHeader("x-api-key", "yourapikeyhere")
  .build();
Response response = client.newCall(request).execute();

```


> The above command returns JSON structured like this:

```json
{
    "instrumentUpdateMessages": [
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
            "filterCategory": "UNCLASSIFIED",
            "filterCategoryId": "-1"
        },
        {
            "id": "589113551676169507",
            "title": "Paytm",
            "description": "Trending News - Business news: Paytm to focus on distribution of insurance products of other insurers | Biz highlights",
            "content": "Business Wrap: Here are the top developments of the day, Shares of Exide Industries Limited hit a record high on June 13 following company's Rs 75 crore i![Alt text](sqtest.png)nvestment in EESL. Soon after taking over as the aviation minister, Ram Mohan Naidu announced his commitment to ensuring more affordable airfares for domestic flights. Watch for more!",
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
            "filterCategory": "MEDIA_COVERAGE"
        }
    ],
     "total-items": 9984,
     "current-page": 0,
    "total-pages": 3328
}
```

This endpoint retrieves all instrument updates fittng your query description. Results are returned in paginated formate.

### HTTP Request

`GET http://scoutquest-backend-service-staging.fundsmap.com/hive/api/v1/instrumentUpdates`

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

### Response Object
The update will have 4 main components - `title`, `description`, `content`, `linkDetail.shortLink` which can be used 

- Instrument Update Message Related Fields

Field | Description
--------- | -----------
id | ID of the instrument update message
title | Can be thought of as the heading, In most cases gives the Long Name of the company
description | Can be thought of as the sub-heading. In most cases it gives the type of the update
content | This field has the details about the update
scripDetails.bseScripCode | Gives BSE scrip code of the company if present, else null
scripDetails.scripName | Gives the long scrip name 
scripDetails.bseTickr | Gives BSE Tickr of the company if present, else null
scripDetails.nseTickr | Gives NSE Tickr of the company if present, else null
scripDetails.isin | Gives ISIN the company
linkDetail.shortLink | Gives the link where user can know more about the update. This link needs to be present for any update that you disseminate / publish
updateType | Type of the Update. Possible values: `ANALYST_VIEWS, BULK_BLOCK, CONCALL_HIGHLIGHTS, CONCALL_SUMMARY, CORPORATE_ANNOUNCEMENT, FUTURE_OUTLOOK, GENERAL_NEWS, SQ_SPVMA_INTRADAY_VOLUME_SPURT, TECHNICAL_ANALYSIS, TWEET`. Read More in the example section below. New Update types can be introduced without prior notice. Old Update Types will not be altered without prior notice.
creationTime | Creation time of the update in epoch format
filterCategory | This field can be used to filter out certain kinds of update. Possible Values: `KEY_UPDATE, UNCLASSIFIED, ANALYTICAL_UPDATE, EVENT_SCHEDULE, TECHNICAL_IDEA, MEDIA_COVERAGE, SPVMA`. New New FilterCategories can be introduced without prior notice. 

<aside class="warn">
New `updateType` and `filterCategory` *can be added without* prior notice. Old `updateType` and `filterCategory` will *not be altered without* prior notice.
</aside>


- Pagination Related fields

Field | Description
--------- | -----------
currentPage | Current Page No, starts with 0
totalItems | Total items(instrumentUpdateMessages) available for the given query 
totalPages | Total pages for the available result


### Postman

View these calls [in postman](https://elements.getpostman.com/redirect?entityId=6164887-d8da8efe-16a4-4405-9abb-e685f9f0f85a&entityType=collection)


# Webhooks

## Portal
You can setup webhook, via the portal. To access the webportal, user name and password will be shared with you during onboarding. You can access the portal using this link [hive-dev-portal.scoutquest.in](hive-dev-portal.scoutquest.in)

# Examples

## Instrument Update Messages Examples

### Update Type : BULK_BLOCK 

> Example for Update Type : BULK_BLOCK:
```
{
            "id": "590882329969555364",
            "title": "Shriram Finance Limited",
            "description": "💎Block Deal in Shriram Finance Limited on 2024-06-18",
            "content": "➖ Seller(s):\nBNP PARIBAS FINANCIAL MARKETS\nTotal Sold Qty:1,467,822\nTotal Sold Value:401.03 crores\n➕ Buyer(s):\nMARSHALL WACE INVESTMENT STRATEGIES - EUREKA FUND\nTotal Bought Qty:1,467,822\nTotal Bought Value:401.03 crores\n",
            "scripDetails": {
                "bseScripCode": "511218",
                "scripName": "Shriram Finance Limited",
                "bseTickr": "SHRIRAMFIN",
                "nseTickr": "SHRIRAMFIN",
                "isin": "INE721A01013"
            },
            "linkDetail": {
                "shortLink": "https://sqst.in/PCxmR"
            },
            "updateType": "BULK_BLOCK",
            "creationTime": 1718714125,
            "filterCategory": "KEY_UPDATE"
        }
```  

### Update Type : ANALYTICAL_UPDATE 

> Example for Update Type : ANALYTICAL_UPDATE:
```
{
            "id": "590882329969555364",
            "title": "Shriram Finance Limited",
            "description": "💎Block Deal in Shriram Finance Limited on 2024-06-18",
            "content": "➖ Seller(s):\nBNP PARIBAS FINANCIAL MARKETS\nTotal Sold Qty:1,467,822\nTotal Sold Value:401.03 crores\n➕ Buyer(s):\nMARSHALL WACE INVESTMENT STRATEGIES - EUREKA FUND\nTotal Bought Qty:1,467,822\nTotal Bought Value:401.03 crores\n",
            "scripDetails": {
                "bseScripCode": "511218",
                "scripName": "Shriram Finance Limited",
                "bseTickr": "SHRIRAMFIN",
                "nseTickr": "SHRIRAMFIN",
                "isin": "INE721A01013"
            },
            "linkDetail": {
                "shortLink": "https://sqst.in/PCxmR"
            },
            "updateType": "BULK_BLOCK",
            "creationTime": 1718714125,
            "filterCategory": "KEY_UPDATE"
        }
```  

