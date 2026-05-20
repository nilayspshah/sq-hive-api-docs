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
SQ Hive allows developers to access ScoutQuest's AI-powered, high-quality, actionable and de-noised capital market insights at lightning-fast speeds.

## Characteristics
Updates provided by us have the following characteristics:

|   |   |
|---|---|
|__Simple__| The language of our updates is simple — we strip out most of the jargon. |
|__Relevant__| Through our proprietary algorithms, we filter out most non-relevant news. |
|__Actionable__| Updates provided by us are actionable. |
|__Structured__| Based on the type of update, you can choose to define your own handling logic. |
|__High Coverage__| Updates are sent for all mainboard BSE-listed entities. |
|__Comprehensive__| Our bots listen to thousands of sources including Exchange websites, Conference Calls, Twitter, News Channels, YouTube and many more, providing 360-degree update coverage. |
|__Realtime__| All of the above is done and disseminated to you at lightning speed. |

You can view [this short video](https://www.youtube.com/watch?v=s-pPlZ263Uc&ab_channel=ScoutQuestTV) to know more.

## How to receive updates?
We provide 2 methods to receive these updates.

1. Webhooks
2. API

You can register an endpoint where you will receive each update as and when it happens. Alternatively you can periodically poll for new updates via the API endpoint.

## How to use these updates?
Examples of general use cases include — sending these updates to your clients based on their holdings, having a general/personalised news feed on your website/app, etc.

The use case is up to you, however it is mandatory to attribute ScoutQuest.

## What should the attribution format be?
1. Each update should have a `Powered by ScoutQuest.in` text at the bottom of the message, where `ScoutQuest.in` should be a clickable hyperlink.
2. For each update the CTA / More Details link should be the *shortLink* provided in the update message.

# API

## Base URLs

Staging: <a href="http://scoutquest-backend-service-staging.fundsmap.com">http://scoutquest-backend-service-staging.fundsmap.com</a>

Live: <a href="http://scoutquest-backend-service-production.fundsmap.com">http://scoutquest-backend-service-production.fundsmap.com</a>


## Authentication

SQ Hive uses API keys to allow access to the API.
SQ Hive expects for the API key to be included in all API requests to the server in a header that looks like the following:

`x-api-key: yourapikeyhere`

<aside class="notice">
You must replace <code>yourapikeyhere</code> with your personal API key.
</aside>

<aside class="notice">
You can request an API Key by mailing us at <a href="mailto:sq@fundsmap.com">sq@fundsmap.com</a> or by sending <a href="https://api.whatsapp.com/send/?phone=918779170796&text=I%20would%20like%20to%20request%20for%20API%20keys%20for%20SQ%20Hive">us a WhatsApp at 918779170796</a> if it has not already been shared with you.
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

# Default paginated query
defaultQuery = "http://scoutquest-backend-service-staging.fundsmap.com/hive/api/v1/instrumentUpdates/query?pageNo=0&pageSize=200&sortDirection=DESC"

# Time range query
timeRangeQuery = "http://scoutquest-backend-service-staging.fundsmap.com/hive/api/v1/instrumentUpdates/query?fromTime=1718709015&toTime=1718790615"

# Poll for updates after a known message ID
messageIdQuery = "http://scoutquest-backend-service-staging.fundsmap.com/hive/api/v1/instrumentUpdates/query?messageId=590860706281420591&expression=GT"

payload = {}
headers = {
  'x-api-key': 'yourapikeyhere'
}

response = requests.request("GET", defaultQuery, headers=headers, data=payload)
print(response.text)
```

```shell
# Default paginated query
curl --location 'http://scoutquest-backend-service-staging.fundsmap.com/hive/api/v1/instrumentUpdates/query?pageNo=0&pageSize=200&sortDirection=DESC' \
--header 'x-api-key: yourapikeyhere'

# Time range query
curl --location 'http://scoutquest-backend-service-staging.fundsmap.com/hive/api/v1/instrumentUpdates/query?fromTime=1718709015&toTime=1718790615' \
--header 'x-api-key: yourapikeyhere'

# Poll for updates after a known message ID
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
      "id": "818768429104481561",
      "title": "Vedanta Ltd",
      "description": "💰 Large NCD Issuance Approved",
      "content": "📍Key Insight: Company approved issuing unsecured Non-Convertible Debentures (NCDs).• Up to 300,000 NCDs each valued at ₹1 crore.• Total amount up to ₹3,000 crores.• Private placement basis with listing on BSE.",
      "scripDetails": {
        "bseScripCode": "500295",
        "scripName": "Vedanta Ltd",
        "bseTickr": "VEDL",
        "nseTickr": null,
        "isin": "INE205A01025"
      },
      "linkDetail": {
        "shortLink": "https://sqst.in/XHB3R"
      },
      "creationTime": 1773046405,
      "filterCategory": "UNCLASSIFIED",
      "proFunnel": {
        "sentiment": "neutral",
        "bytes": [
          { "tag": "Maximum number of NCDs issued", "data": "300,000" },
          { "tag": "Face value per NCD", "data": "₹1 crore" },
          { "tag": "Total issuing amount", "data": "up to ₹3,000 crores" },
          { "tag": "Listing exchange", "data": "BSE" },
          { "tag": "Issue method", "data": "private placement" }
        ],
        "classificationJson": {
          "smartTag": "NCD Issuance",
          "importanceFlag": "Insightful",
          "category": "Financial Instruments",
          "subcategory": "Non-Convertible Debenture (NCD) Issuance",
          "emoji": "💰"
        }
      },
      "deepDiveData": {
        "title": "*💰 Large NCD Issuance Approved*",
        "insight": "• Company approved issuing unsecured Non-Convertible Debentures (NCDs).• Up to 300,000 NCDs each valued at ₹1 crore.• Total amount up to ₹3,000 crores.• Private placement basis with listing on BSE.",
        "fast_fact": "The company has approved issuing up to 300,000 unsecured, rated, listed, redeemable Non-Convertible Debentures with a face value of ₹1 crore each, aggregating up to ₹3,000 crores on a private placement basis, to be listed on BSE.",
        "source_link": "https://www.bseindia.com/xml-data/corpfiling/AttachLive/74a1e055-e4be-4fbc-abe0-2092e278bc0b.pdf",
        "deep_dive_html": "<h2>💡 Type of Securities:</h2><ul><li>Unsecured NCDs — loans without collateral security.</li><li>Redeemable — principal repaid after a set period.</li><li>Rated — assessed for credit quality.</li></ul>",
        "deep_dive_link": "https://scoutquest.blob.core.windows.net/sq-public-container/deepdive_2026-02-25T07:29:13.2192704Z.html",
        "deep_dive_text": "💡 Type of Securities:<br>- Unsecured NCDs without collateral security.<br>- Redeemable with principal repayment after a set period.<br>- Rated by credit quality agencies.",
        "flagNote": "Large debt fundraising approved, important for investors' financial understanding",
        "concernFlag": ""
      }
    },
    {
      "id": "589113551676169507",
      "title": "Paytm",
      "description": "Trending News - Business news: Paytm to focus on distribution of insurance products of other insurers | Biz highlights",
      "content": "Business Wrap: Here are the top developments of the day...",
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
      "creationTime": 1718292415,
      "filterCategory": "MEDIA_COVERAGE"
    }
  ],
  "total-items": 9984,
  "current-page": 0,
  "total-pages": 3328
}
```

This endpoint retrieves all instrument updates matching your query description. Results are returned in a paginated format.

### HTTP Request

`GET http://scoutquest-backend-service-staging.fundsmap.com/hive/api/v1/instrumentUpdates/query`

### Possible Queries

1. Get updates for a given time period (using `fromTime` and `toTime`)
2. Get data for a specific update (`messageId`)
3. Get updates before/after a specific update (`messageId` + `expression`)
4. Get updates for a specific scrip (`scripIdType` + `scripId`)

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
pageNo | 0 | Change `pageNo` for the next set of results matching your query. Zero-indexed.
pageSize | 200 | Number of results to be returned in a single page. You can fetch more results by incrementing `pageNo`. Maximum value is `1000`.
sortDirection | DESC | Sort order with respect to `creationTime`. `DESC` returns the latest updates at the top. Possible values: `ASC`, `DESC`.
fromTime | - | Used when you need updates within a time range. If `toTime` is absent, it is assumed to be the current server time. Value is a Unix epoch timestamp in UTC.
toTime | - | Used when you need updates within a time range. `fromTime` must also be present if `toTime` is specified. Value is a Unix epoch timestamp in UTC.
messageId | - | Used to fetch messages equal to, or chronologically before/after a given `messageId`. Useful when you have processed messages up to a certain point and need to process messages after it, or when you need to look up a specific update. The `expression` parameter controls this behaviour. If `expression` is not passed, only the exact matching message is returned (i.e. `expression` defaults to `EQ`).
expression | - | Used in conjunction with `messageId`. Controls whether you get messages created before or after the given `messageId`. Possible values: `GT` (Greater Than), `GOE` (Greater Than or Equal to), `LT` (Less Than), `LOE` (Less Than or Equal to), `EQ` (Equal To). Ignored if `messageId` is not present.
scripIdType | - | Used when querying updates for a particular scrip. Specifies the type of identifier passed in `scripId`. Possible values: `BSE_SCRIP_CODE`, `BSE_TICKR`.
scripId | - | The scrip identifier value. If `scripIdType` is `BSE_SCRIP_CODE`, pass the BSE scrip code (e.g. `500570` for Tata Motors). If `scripIdType` is `BSE_TICKR`, pass the ticker (e.g. `TATAMOTORS`). Refer to Instrument Masters such as Bhavcopy or Scrip Master (SCRIP.zip) from [this BSE site](https://www.bseindia.com/members/index.aspx).
curationType | CURATED | Controls suppression of lower-importance updates. `CURATED` returns only updates classified as high-signal by ScoutQuest's internal logic — recommended for most consumer-facing applications. `NON_CURATED` includes all `CURATED` updates plus additional lower-signal updates.

### Response Object

The update will have 4 main components — `title`, `description`, `content`, and `linkDetail.shortLink` — which can be used directly for display. `title` + `description` identify the company and update type; `content` provides the details.

**Instrument Update Message Fields**

Field | Description
--------- | -----------
id | Unique ID of the instrument update message.
title | The full company name. May contain emoji characters.
description | Describes the type of update. May contain emoji characters.
content | The detail body of the update. May contain emoji characters and inline image markdown syntax (e.g. `![Alt text](url)`).
scripDetails.bseScripCode | BSE scrip code of the company, or `null` if not available.
scripDetails.scripName | Full scrip name as listed on BSE.
scripDetails.bseTickr | BSE ticker symbol, or `null` if not available.
scripDetails.nseTickr | NSE ticker symbol. May be `null` **or** an empty string `""` — treat both as absent.
scripDetails.isin | ISIN of the company. May occasionally be stale; prefer `bseScripCode` for lookups.
linkDetail.shortLink | Short URL for the full update page. Must be present in any update you disseminate.
creationTime | Creation time of the update as a Unix epoch timestamp in UTC. Add 19800 seconds (+5:30) to convert to IST.
filterCategory | Classification of the update type. See [Examples section](#examples-for-instrument-update-messages-filter-categories). Possible values: `KEY_UPDATE`, `UNCLASSIFIED`, `ANALYTICAL_UPDATE`, `EVENT_SCHEDULE`, `TECHNICAL_IDEA`, `MEDIA_COVERAGE`, `SPVMA`.
smartTags <span style="background:#FFD700; color:#222; border-radius:4px; padding:2px 8px; font-weight:bold; font-size:90%; margin-left:6px;">Hive Pro</span> | A concise tag that classifies each update into a predefined, actionable category.
concernFlags <span style="background:#FFD700; color:#222; border-radius:4px; padding:2px 8px; font-weight:bold; font-size:90%; margin-left:6px;">Hive Pro</span> | Indicators such as Red Flag or Procedural Update to highlight updates requiring investor attention.
proFunnel <span style="background:#FFD700; color:#222; border-radius:4px; padding:2px 8px; font-weight:bold; font-size:90%; margin-left:6px;">Hive Pro</span> | Structured data regarding sentiment, key bytes, and classification of the update. May be absent for some update types (e.g. `MEDIA_COVERAGE`, `TECHNICAL_IDEA`).
deepDiveData <span style="background:#FFD700; color:#222; border-radius:4px; padding:2px 8px; font-weight:bold; font-size:90%; margin-left:6px;">Hive Pro</span> | Detailed structured data specific to the update type (e.g. revenue/PAT in results, transaction details in block deals). The schema is dynamic and varies by update type.

**Pagination Fields**

Field | Description
--------- | -----------
total-items | Total number of updates matching the query across all pages.
current-page | Current page number (zero-indexed).
total-pages | Total number of available pages for the current query.

<aside class="warning">
New <code>filterCategory</code> values can be added without prior notice. Existing values will not be altered without prior notice. Design your handler to process unknown values gracefully.
</aside>

<aside class="warning">
Use <code>bseScripCode</code> as the primary instrument identifier. ISIN values may sometimes be stale and out of sync.
</aside>

<aside class="warning">
<code>title</code>, <code>description</code>, and <code>content</code> can contain emoji characters (Unicode supplementary characters). In most languages the standard String type handles this correctly, but ensure your database columns use an encoding that supports 4-byte Unicode (e.g. <code>utf8mb4</code> in MySQL).
</aside>

<aside class="notice">
Only data for the last 7 days is available via the API.
</aside>

### `proFunnel` Object Structure

Field | Description
--------- | -----------
sentiment | The sentiment of the update. Possible values: `"positive"`, `"negative"`, `"neutral"`, `"not_known"`.
bytes | An array of key data points extracted from the update.
bytes[].tag | The label for the data point (e.g. `"Face value per NCD"`, `"Board Meeting Date"`).
bytes[].data | The value for the data point. Always a string. Date formats are not normalised — values may appear as ISO-8601 (`"2026-05-22"`), natural language (`"20th May 2026"`), or other formats. Render as a plain display string; do not attempt programmatic date parsing.
classificationJson | Structured classification metadata for the event.
classificationJson.smartTag | A concise 2–4 word tag summarising the update (e.g. `"NCD Issuance"`, `"Auditor Change"`).
classificationJson.importanceFlag | Qualitative importance level. Observed values: `"Insightful"`, `"Procedural"`. Additional values may be added.
classificationJson.category | Broad thematic category (e.g. `"Financial Instruments"`, `"Governance & Board Updates"`).
classificationJson.subcategory | Specific subcategory (e.g. `"Non-Convertible Debenture (NCD) Issuance"`, `"Board Meeting Scheduling"`).
classificationJson.emoji | A single emoji character representing the update type.

### `deepDiveData` Object Structure

The `deepDiveData` object provides detailed, specific insights into the update.

<aside class="notice">
The structure and fields within <code>deepDiveData</code> are dynamic. The schema will vary based on the specific type of update (e.g. financial results, NCD issuances, acquisitions).
</aside>

Field | Description
--------- | -----------
title | A formatted title for the deep-dive (may include markdown bold).
insight | A bullet-point summary of the key facts.
fast_fact | A single-sentence plain-language summary of the core fact. Always present when `deepDiveData` exists.
source_link | URL to the primary source document (e.g. BSE filing PDF). May be absent for some update types.
deep_dive_html | The full deep-dive as raw HTML. Structure varies by update type — some records use `<h2>` + `<ul><li>` hierarchy; others use `<p><strong>` + `<br>` inline structure.
deep_dive_link | URL to a hosted HTML page with the fully rendered deep-dive. Use as a "Read More" CTA link.
deep_dive_text | Plain-text rendering of the deep-dive with `<br>` line breaks. Suitable for WhatsApp, SMS, or plain-text email.
flagNote | A short contextual note about the update. May be present even when `concernFlag` is an empty string.
concernFlag | A string flag label. May be an empty string `""` when no flag was raised.


## Get Assessment for an Instrument Update

```ruby
require "uri"
require "net/http"

url = URI("http://scoutquest-backend-service-staging.fundsmap.com/hive/api/v1/instrumentUpdates/assessment?instrumentUpdateId=818768429104481561")

http = Net::HTTP.new(url.host, url.port);
request = Net::HTTP::Get.new(url)
request["x-api-key"] = "yourapikeyhere"

response = http.request(request)
puts response.read_body
```

```python
import requests

url = "http://scoutquest-backend-service-staging.fundsmap.com/hive/api/v1/instrumentUpdates/assessment?instrumentUpdateId=818768429104481561"

payload = {}
headers = {
  'x-api-key': 'yourapikeyhere'
}

response = requests.request("GET", url, headers=headers, data=payload)
print(response.text)
```

```shell
curl --location 'http://scoutquest-backend-service-staging.fundsmap.com/hive/api/v1/instrumentUpdates/assessment?instrumentUpdateId=818768429104481561' \
--header 'x-api-key: yourapikeyhere'
```

```javascript
const axios = require('axios');

let config = {
  method: 'get',
  maxBodyLength: Infinity,
  url: 'http://scoutquest-backend-service-staging.fundsmap.com/hive/api/v1/instrumentUpdates/assessment?instrumentUpdateId=818768429104481561',
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
  .url("http://scoutquest-backend-service-staging.fundsmap.com/hive/api/v1/instrumentUpdates/assessment?instrumentUpdateId=818768429104481561")
  .method("GET", body)
  .addHeader("x-api-key", "yourapikeyhere")
  .build();
Response response = client.newCall(request).execute();
```


> The above command returns JSON structured like this:

```json
{
  "stock": "Zydus Lifesciences Ltd",
  "event_type": "Share Buyback (board-approved)",
  "significance": "Medium",
  "what_happened": "Board approved a buyback of up to 95.65 lakh shares (≈0.95% of outstanding), at ₹1,150/share, with a maximum cash outlay of ₹1,100 crore. Record date for participation: May 29, 2026. Company cites utilisation of equity/reserves for the buyback.",
  "why_this_matters": [
    "Cash commitment is sizeable but affordable: ₹1,100 Cr represents ~1.06% of reported market cap (₹1,03,944 Cr) and ~39.6% of reported Cash & Bank (₹2,782 Cr).",
    "Buyback price (~₹1,150) is ≈11.3% premium to current price (₹1,033), creating a direct near-term upside incentive for holders to tender.",
    "Supply reduction is modest (0.95% of shares) — unlikely to materially change float or EPS by itself, though selective tendering (e.g. promoter participation) can alter effective benefit to public holders.",
    "Company appears to have strong cash-generation: latest operating cash flow ₹6,777 Cr (rising), supporting the payout without straining operations.",
    "Signal on capital allocation: buyback + proposed dividend indicates management prefers buybacks/dividends over other uses — positive for return-focused investors given healthy ROE/ROCE (21.2% / 24.3%)."
  ],
  "investor_impact": {
    "short_term": "Likely positive price support: buyback at an ~11% premium may lift market price ahead of/around the record date. Trading reaction could be muted after completion given small share reduction (0.95%).",
    "medium_term": "Limited EPS accretion given small reduction in shares; main benefit is return of capital to holders. If promoters participate, public minority may see less proportional benefit.",
    "long_term": "Neutral-to-modestly positive structural effect if buybacks become a recurring disciplined allocation method — preserves capital returns while company retains strong operating cash generation and healthy ROE/ROCE."
  },
  "risk_reward_outlook": "Moderate Positive",
  "risk_reward_score": 7,
  "ITI": "SSB3YW50IHRvIHVuZGVyc3RhbmQgZnVydGhlciBpHVybiBvZiBjYXBpdGFsIiwiY2FwaXRhbCByZWR1Y3Rpb24iXQo="
}
```

This endpoint retrieves the AI-generated assessment for a specific instrument update, providing structured analysis of the corporate event and its investor implications.

### HTTP Request

`GET http://scoutquest-backend-service-staging.fundsmap.com/hive/api/v1/instrumentUpdates/assessment`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
instrumentUpdateId | - | The `id` of the instrument update for which the assessment is to be retrieved. This is the same `id` field returned by the instrument update query endpoint.

### Response Object

Field | Description
--------- | -----------
stock | Name of the company / stock for which the assessment was generated.
event_type | The type of corporate event being assessed (e.g. `Share Buyback (board-approved)`, `Earnings`, `M&A`).
significance | Overall significance of the event. Possible values: `Low`, `Medium`, `High`.
what_happened | A concise factual summary of the event in plain language.
why_this_matters | An array of strings, each a bullet-point explaining the rationale behind the assessment — financial impact, comparisons with relevant metrics, and structural implications.
investor_impact | An object describing the expected impact across multiple time horizons.
investor_impact.short_term | Expected impact in the short term (typically days to weeks around the event).
investor_impact.medium_term | Expected impact in the medium term (typically months).
investor_impact.long_term | Expected structural / long-term impact.
risk_reward_outlook | A qualitative outlook label. Possible values: `Strong Negative`, `Moderate Negative`, `Neutral`, `Moderate Positive`, `Strong Positive`.
risk_reward_score | A numeric score from `1` (least favourable) to `10` (most favourable) representing the risk/reward profile of the event.
ITI | A base64-encoded string intended to be fed directly into an LLM of the client's choice for further analysis or chat-style interaction over the assessment.

<aside class="notice">
The set of fields in the assessment response may evolve over time as the underlying model improves. New fields can be added without prior notice. Existing fields will not be altered without prior notice.
</aside>

<aside class="notice">
Access to this endpoint requires a separate assessment entitlement. You can request access by mailing us at <a href="mailto:sq@fundsmap.com">sq@fundsmap.com</a> or by sending us a <a href="https://api.whatsapp.com/send/?phone=918779170796&text=I%20would%20like%20to%20request%20for%20access%20to%20the%20Assessment%20API%20for%20SQ%20Hive">WhatsApp at 918779170796</a>.
</aside>

### Postman

View these calls [in Postman](https://elements.getpostman.com/redirect?entityId=6164887-d8da8efe-16a4-4405-9abb-e685f9f0f85a&entityType=collection).


# Webhooks


## Introduction to SQ Hive Webhooks
Webhooks are how services notify each other of events. At their core they are just a `POST` request to a pre-determined endpoint. The endpoint can be whatever you want, and you can just [add them from the UI](#adding-an-endpoint). You normally use one endpoint per service, and that endpoint listens to all of the event types. For example, if you receive webhooks from Acme Inc., you can structure your URL like: `https://www.example.com/acme/webhooks/`.

The way to indicate that a webhook has been processed is by returning a `2xx` (status code `200-299`) response to the webhook message within a reasonable time-frame (15s). It's also important to disable `CSRF` protection for this endpoint if the framework you use enables it by default.

Another important aspect of handling webhooks is to verify the signature and timestamp when processing them. You can learn more about it in the [webhook signature verification](#webhook-signature-verification) section.

<aside class="notice">
You can request webhook access by mailing us at <a href="mailto:sq@fundsmap.com">sq@fundsmap.com</a> or by sending us a <a href="https://api.whatsapp.com/send/?phone=918779170796&text=I%20would%20like%20to%20request%20webhook%20access%20for%20SQ%20Hive">WhatsApp at 918779170796</a>, if you don't already have it.
</aside>


## Instrument Update Created — Webhook Event

We have a variety of event types you can subscribe to. One such event is `v1.instrument_update.created`, fired whenever a new instrument update is published.

> Here is a sample payload for `v1.instrument_update.created`:

```json
{
  "creationTimestamp": 1717247896,
  "eventId": "evt_cdab7cfe-043c-4d4a-99c1-258c0a60f4b8",
  "eventType": "V1_INSTRUMENT_UPDATE_CREATED",
  "payload": {
    "id": "584732514325722439",
    "title": "Macrotech Developers Limited",
    "description": "📊 Macrotech Developers Limited Earnings Conference Call Q4FY24",
    "content": "- Record pre-sales: Q4 FY24 at INR 42.3 billion (40% YoY growth) and FY24 at INR 145.2 billion (20% YoY growth). - Strong EBITDA margin: ~30% for FY24 and ~31% for Q4 FY24. - Robust operating cash flow: INR 57.2 billion for FY24 and INR 20.5 billion in Q4 FY24. ...",
    "scripDetails": {
      "bseScripCode": "543287",
      "scripName": "Macrotech Developers Limited",
      "bseTickr": "LODHA",
      "nseTickr": "LODHA",
      "isin": "INE670K01029"
    },
    "linkDetail": {
      "shortLink": "https://sqst.in/F08qo"
    },
    "creationTime": 1717247895,
    "filterCategory": "ANALYTICAL_UPDATE",
    "proFunnel": {
      "sentiment": "positive",
      "bytes": [
        { "tag": "Q4 FY24 Pre-sales", "data": "INR 42.3 billion" },
        { "tag": "FY24 Pre-sales", "data": "INR 145.2 billion" },
        { "tag": "FY24 EBITDA margin", "data": "~30%" },
        { "tag": "Net Debt", "data": "INR 30.1 billion" }
      ],
      "classificationJson": {
        "smartTag": "Quarterly Earnings Report",
        "importanceFlag": "Insightful",
        "category": "Financial Performance",
        "subcategory": "Earnings Reports",
        "emoji": "📊"
      },
      "deepdive": {
        "deep_dive_text": "🔍 Q4 FY24 highlights...",
        "deep_dive_link": "https://scoutquest.blob.core.windows.net/sq-public-container/deepdive_Macrotech_2024.html",
        "deep_dive_html": "<h2>🔍 Q4 FY24 highlights</h2><ul><li>Record pre-sales of INR 42.3 billion</li></ul>..."
      },
      "concernFlag": {
        "flag": "💡 Insightful Update",
        "flagNote": "Strong operating performance with margin expansion"
      },
      "deepdiveData": {
        "fast_fact": "Macrotech reported record FY24 pre-sales of INR 145.2 billion (20% YoY) with EBITDA margin of ~30%.",
        "source_link": "https://scoutquest.blob.core.windows.net/sq-public-container/concalltranscript_MacrotechDevelopersLimited2024-04-25T09:01:48.3862513Z.pdf"
      }
    }
  }
}
```

**Webhook Envelope Fields**

Field | Description
--------- | -----------
creationTimestamp | Unix epoch timestamp (UTC) of when the webhook event was created.
eventId | Unique identifier for this webhook event. Use for deduplication.
eventType | The event type string. Instrument update events use SCREAMING_SNAKE_CASE (e.g. `V1_INSTRUMENT_UPDATE_CREATED`). User events use dot notation (e.g. `v1.user.created`).
payload | The instrument update message object.


## Instrument Update Modified — Webhook Event

In case there is a revision to an already-sent instrument update, we send the updated message using the `v1.instrument_update.modified` event. The `payload` shape is identical to the `v1.instrument_update.created` event above.

> Here is a sample payload for `v1.instrument_update.modified`:

```json
{
  "creationTimestamp": 1717247896,
  "eventId": "evt_cdab7cfe-043c-4d4a-99c1-258c0a60f4b8",
  "eventType": "V1_INSTRUMENT_UPDATE_MODIFIED",
  "payload": {
    "id": "584732514325722439",
    "title": "Macrotech Developers Limited",
    "description": "📊 Macrotech Developers Limited Earnings Conference Call Q4FY24 (Revised)",
    "content": "- Record pre-sales: Q4 FY24 at INR 42.3 billion (40% YoY growth) and FY24 at INR 145.2 billion (20% YoY growth). - Strong EBITDA margin: ~30% for FY24 and ~31% for Q4 FY24. ...",
    "scripDetails": {
      "bseScripCode": "543287",
      "scripName": "Macrotech Developers Limited",
      "bseTickr": "LODHA",
      "nseTickr": "LODHA",
      "isin": "INE670K01029"
    },
    "linkDetail": {
      "shortLink": "https://sqst.in/F08qo"
    },
    "creationTime": 1717247895,
    "filterCategory": "ANALYTICAL_UPDATE",
    "proFunnel": {
      "sentiment": "positive",
      "bytes": [
        { "tag": "Q4 FY24 Pre-sales", "data": "INR 42.3 billion" },
        { "tag": "FY24 Pre-sales", "data": "INR 145.2 billion" }
      ],
      "classificationJson": {
        "smartTag": "Quarterly Earnings Report",
        "importanceFlag": "Insightful",
        "category": "Financial Performance",
        "subcategory": "Earnings Reports",
        "emoji": "📊"
      },
      "deepdive": {
        "deep_dive_text": "🔍 Q4 FY24 highlights (revised)...",
        "deep_dive_link": "https://scoutquest.blob.core.windows.net/sq-public-container/deepdive_Macrotech_2024.html",
        "deep_dive_html": "<h2>🔍 Q4 FY24 highlights (revised)</h2>..."
      },
      "concernFlag": {
        "flag": "💡 Insightful Update",
        "flagNote": "Strong operating performance with margin expansion"
      },
      "deepdiveData": {
        "fast_fact": "Macrotech reported record FY24 pre-sales of INR 145.2 billion (20% YoY) with EBITDA margin of ~30%.",
        "source_link": "https://scoutquest.blob.core.windows.net/sq-public-container/concalltranscript_MacrotechDevelopersLimited2024-04-25T09:01:48.3862513Z.pdf"
      }
    }
  }
}
```


## User Created — Webhook Event

If you as a business would like to keep track of users who have signed up using your business code, you can subscribe to this webhook.

> Here is a sample payload for `v1.user.created`:

```json
{
  "creationTimestamp": 1735731297,
  "eventId": "evt_16ecf03b-333d-4aab-aeff-6b1036e458af",
  "eventType": "v1.user.created",
  "payload": {
    "countryCode": "+91",
    "creationTime": 1735731295,
    "messageContent": "Hello I'm a client of Broker A. I would like to subscribe to WhatsApp updates for Stocks that I track",
    "messageId": "67752577f91729f7d301a793",
    "mobileNo": "888888888",
    "referralOrigin": "whatsapp-tellephant-bot",
    "referralSource": "Broker-A",
    "userId": "usr_6622575129096656",
    "userSignupChannel": "WHATSAPP"
  }
}
```

**Payload Fields**

Field | Description
--------- | -----------
countryCode | International dialling code of the user (e.g. `"+91"`).
creationTime | Unix epoch timestamp (UTC) of when the user was created.
messageContent | The first message the user sent when signing up (e.g. via WhatsApp bot).
messageId | Internal message ID of the sign-up trigger message.
mobileNo | User's mobile number (without country code).
referralOrigin | The channel through which the user signed up (e.g. `"whatsapp-tellephant-bot"`).
referralSource | Your business code / referral identifier as configured during onboarding.
userId | Unique user identifier assigned by SQ Hive (prefixed `usr_`).
userSignupChannel | The channel used for sign-up. Possible values: `WHATSAPP`.


## User Modified — Webhook Event

You can also subscribe to user modified webhook events, which are sent when user-related attributes change. Currently triggered when a user updates their WhatsApp consent.

> Here is a sample payload for `v1.user.modified`:

```json
{
  "creationTimestamp": 1740599471,
  "eventId": "evt_5d303a23-ada3-4b38-b3ea-e23dc29ece3a",
  "eventType": "v1.user.modified",
  "payload": {
    "consentStatus": "OPT_IN",
    "countryCode": "+91",
    "creationTime": 1735731295,
    "lastModificationTime": 1740599471,
    "mobileNo": "9999999999",
    "userId": "usr_662257512909639656"
  }
}
```

**Payload Fields**

Field | Description
--------- | -----------
consentStatus | The user's updated consent status. Possible values: `OPT_IN`, `OPT_OUT`.
countryCode | International dialling code of the user.
creationTime | Unix epoch timestamp (UTC) of when the user was originally created.
lastModificationTime | Unix epoch timestamp (UTC) of this modification event.
mobileNo | User's mobile number (without country code).
userId | Unique user identifier assigned by SQ Hive (prefixed `usr_`).


## Adding an Endpoint

In order to start listening to webhook messages sent by SQ Hive, you will need to configure your **endpoints**.

Adding an endpoint is as simple as providing a URL that you control and a list of **event types** that you want to listen to.

You can add your endpoint from your [webhooks dashboard](#dashboard).

![add endpoint](https://docs.svix.com/assets/images/add-endpoint-6cbcc00b62087f2774cd90b965a3d197.png)

<aside class="notice">
Helpful Tip!
<br>
If you don't have a URL or your service isn't quite ready to start receiving events, press the <code>Svix Play</code> button to have a unique URL generated for you.
<br>
You'll be able to view and inspect all webhook messages sent to your Svix Play URL, making it effortless to get started.
<br>
You can also use a service like <code>ngrok</code> to start receiving webhooks locally.
</aside>

If you don't specify any event types, by default your endpoint will receive all events, regardless of type. This can be helpful for getting started and testing, but we recommend narrowing to a subset later on to avoid receiving unexpected messages.

### Testing your Endpoint

The easiest way to gain confidence in your endpoint configuration is to start receiving events as quickly as possible.

That's why we have a "Testing" tab for you to send example events to your endpoint.

![testing endpoint](https://docs.svix.com/assets/images/testing-endpoint-3f325ed4f08a4b9c57c49a3dd8ef2e9f.png)

After sending an example event, you can click into the message to view the message payload, all of the message attempts, and whether each attempt succeeded or failed.


## Webhook Signature Verification

Webhook signatures are your way to verify that webhook messages are genuinely sent by us. For a more detailed explanation, check out this article on [why you should verify webhooks](https://docs.svix.com/receiving/verifying-payloads/why).

### How to verify webhooks with Svix Libraries

You can use useful libraries developed by our webhook partner Svix that make verifying webhooks very simple. Here is an example using JavaScript:

```javascript
import { Webhook } from "svix";

const secret = "whsec_MfKQ9r8GKYqrTwjUPD8ILPZIo2LaLaSw";

// These were all sent from the server
const headers = {
  "svix-id": "msg_p5jXN8AQM9LWM0D4loKWxJek",
  "svix-timestamp": "1614265330",
  "svix-signature": "v1,g0hM9SsE+OTPJTGt/tmIKtSyZlE3uFJELVlNIOLJ1OE=",
};
const payload = '{"test": 2432232314}';

const wh = new Webhook(secret);
// Throws on error, returns the verified content on success
const verifiedPayload = wh.verify(payload, headers);
```

For more instructions and examples of how to verify signatures, check out their [webhook verification documentation](https://docs.svix.com/receiving/verifying-payloads/how).


## Dashboard

You can set up webhooks via the portal. Your username and password will be shared with you during onboarding.

You can access the portal at [dashboard.hive.scoutquest.in](https://dashboard.hive.scoutquest.in).

### Demo Dashboard Access

You can explore the dashboard using demo credentials: visit [dashboard.hive.scoutquest.in](https://dashboard.hive.scoutquest.in) with `username` — `sq-hive-demo` and `password` — `sq-hive-demo`.

<aside class="notice">
The demo dashboard is for viewing and introductory purposes only. Your actual credentials will be shared with you during onboarding.
</aside>


## Retries

SQ Hive attempts to deliver each webhook message based on a retry schedule with exponential backoff.

### The schedule

Each message is attempted based on the following schedule, where each period starts following the failure of the preceding attempt:

- Immediately
- 5 seconds
- 5 minutes
- 30 minutes
- 2 hours
- 5 hours
- 10 hours
- 10 hours (in addition to the previous)

If an endpoint is removed or disabled, delivery attempts to that endpoint will also stop.

For example, an attempt that fails three times before eventually succeeding will be delivered roughly 35 minutes and 5 seconds following the first attempt.

### Manual retries

You can also use the application portal to manually retry each message at any time, or automatically retry ("Recover") all failed messages starting from a given date.


## Troubleshooting Tips

There are some common reasons why your webhook endpoint may be failing:

### Not using the raw payload body

This is the most common issue. When generating the signed content, we use the raw string body of the message payload.

If you convert JSON payloads into strings using methods like `stringify`, different implementations may produce different string representations of the JSON object, which can lead to discrepancies when verifying the signature. It's crucial to verify the payload exactly as it was sent, byte-for-byte or string-for-string.

### Missing the secret key

From time to time we see people using the wrong secret key. Remember that keys are unique to endpoints.

### Sending the wrong response codes

When we receive a response with a `2xx` status code, we interpret that as a successful delivery even if you indicate a failure in the response payload. Make sure to use the correct response status codes so we know when messages are supposed to succeed vs. fail.

### Responses timing out

We will consider any message that fails to send a response within the timeout duration a failed message. If your endpoint is processing complicated workflows, it may time out and result in failed messages.

We recommend having your endpoint simply receive the message and add it to a queue for asynchronous processing, so you can respond promptly and avoid timeouts.


## Failure Recovery

### Re-enable a disabled endpoint

If all attempts to a specific endpoint fail for a period of 5 days, the endpoint will be disabled. To re-enable it, go to the webhook dashboard, find the endpoint from the list, and select "Enable Endpoint".

### Recovering/Resending failed messages

#### Why Replay

- If your service has downtime
- If your endpoint was misconfigured

If you want to replay a single event, find the message from the UI and click the options menu next to any of the attempts.

![resend message](https://docs.svix.com/assets/images/resend-single-a4fb6e65f27f27e5700becb523135c2f.png)

From there, click "resend" to have the same message sent to your endpoint again.

If you need to recover from a service outage and want to replay all the events since a given time, you can do so from the Endpoint page. On an endpoint's details page, click `Options > Recover Failed Messages`.

![recover modal](https://docs.svix.com/assets/images/replay-modal-fa510bd82e4eccbbb01df28581ad8901.png)

From there, you can choose a time window to recover from.

For more granular recovery — for example, if you know the exact timestamp you want to recover from — you can click the options menu on any message from the endpoint page, then click "Replay..." and choose "Replay all failed messages since this time."


# Examples for Instrument Update Messages Filter Categories

## KEY_UPDATE — filterCategory

Significant corporate events such as block deals, large institutional transactions, material regulatory disclosures, auditor appointments, and insider trading disclosures.

> Example for Filter Category — KEY_UPDATE

```json
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
  "creationTime": 1718714125,
  "filterCategory": "KEY_UPDATE"
}
```


## ANALYTICAL_UPDATE — filterCategory

Broker research reports, analyst ratings, buy/sell/hold recommendations with target prices. The `content` field typically contains an AI-generated interpretation of the broker note.

> Example for Filter Category — ANALYTICAL_UPDATE

```json
{
  "id": "589832824574705351",
  "title": "Zomato Ltd.",
  "description": "SBI Securities has published a Buy report on Zomato Ltd.. (CMP: 186.20 As on 14 Jun 24 | 16:00 )",
  "content": "🤖 AI interpretation: Zomato Ltd. is recommended as a `BUY` with a 12-month target price of 214.0/-. The basis for this recommendation includes its diversified business model, strong brand, expanding product offerings, presence in 800+ cities, strong financial performance, and plans to double the store count. The stock's current valuation is considered premium but well supported by earnings growth. Key risk factors include any consumption slowdown and high competition.",
  "scripDetails": {
    "bseScripCode": "543320",
    "scripName": "Zomato Ltd.",
    "bseTickr": "ZOMATO",
    "nseTickr": "",
    "isin": "INE758T01015"
  },
  "linkDetail": {
    "shortLink": "https://sqst.in/hyONA"
  },
  "creationTime": 1718463903,
  "filterCategory": "ANALYTICAL_UPDATE"
}
```

<aside class="notice">
Note that <code>nseTickr</code> is an empty string <code>""</code> in this example, not <code>null</code>. Both <code>null</code> and <code>""</code> indicate the ticker is unavailable. Always treat both as absent when building display logic.
</aside>


## MEDIA_COVERAGE — filterCategory

TV video feeds, news article mentions, and YouTube coverage of the company. `proFunnel` is typically absent for this category.

> Example for Filter Category — MEDIA_COVERAGE

```json
{
  "id": "590874291145537518",
  "title": "M&M",
  "description": "Video feed - CNBC TV18 Newsmakers | M&M: Best Performing Nifty Stock 2002-2024 | Mega Exclusive | N18V",
  "content": "CNBC TV18 Newsmakers | M&M: Best Performing Nifty Stock 2002-2024 | Mega Exclusive | N18V",
  "scripDetails": {
    "bseScripCode": "509196",
    "scripName": "M&M",
    "bseTickr": "MMRUBBR-B",
    "nseTickr": null,
    "isin": "INE159E01026"
  },
  "linkDetail": {
    "shortLink": "https://sqst.in/d1d04"
  },
  "creationTime": 1718712208,
  "filterCategory": "MEDIA_COVERAGE"
}
```


## SPVMA — filterCategory

Significant Price and Volume Movement Alert. Triggered when trading volume exceeds a multiple of the recent average (e.g. 9.99× the 2-week average daily volume).

> Example for Filter Category — SPVMA

```json
{
  "id": "590834457848837239",
  "title": "Kalpataru Projects International Limited",
  "description": "🔥 Unusually high trading activity - Trading volume as of 02:54PM is  9.99 times of the average daily volume (2 week avg.) \n34 Lakh shares (Value: Rs. 413 Crores)  traded on NSE as of 02:54PM.",
  "content": "🏷️ CMP @ 02:54PM: 1173.7 (Chg %: -3.81)",
  "scripDetails": {
    "bseScripCode": "522287",
    "scripName": "Kalpataru Projects International Limited",
    "bseTickr": "KPIL",
    "nseTickr": "KPIL",
    "isin": "INE220B01022"
  },
  "linkDetail": {
    "shortLink": "https://sqst.in/CaKY8"
  },
  "creationTime": 1718702711,
  "filterCategory": "SPVMA"
}
```


## EVENT_SCHEDULE — filterCategory

Scheduled corporate events such as board meetings, AGMs, analyst/institutional meets, earnings calls, and trading window closures.

> Example for Filter Category — EVENT_SCHEDULE

```json
{
  "id": "590874081665218776",
  "title": "KIRLOSKAR OIL ENGINES LTD.",
  "description": "💼 Analyst / Institutional Meet",
  "content": "Kirloskar Oil Engines Limited held a virtual meeting with Antique securities to discuss the operational overview of the company. No unpublished price sensitive information was disclosed. The meeting was in compliance with SEBI regulations.",
  "scripDetails": {
    "bseScripCode": "533293",
    "scripName": "KIRLOSKAR OIL ENGINES LTD.",
    "bseTickr": "KIRLOSENG",
    "nseTickr": null,
    "isin": "INE146L01010"
  },
  "linkDetail": {
    "shortLink": "https://sqst.in/GixAV"
  },
  "creationTime": 1718712158,
  "filterCategory": "EVENT_SCHEDULE"
}
```


## TECHNICAL_IDEA — filterCategory

Chart pattern signals and technical analysis ideas. `proFunnel` is typically absent for this category.

> Example for Filter Category — TECHNICAL_IDEA

```json
{
  "id": "583227559222362559",
  "title": "COROMANDEL",
  "description": "Long",
  "content": "#COROMANDEL #NSE - CUP PATTERN",
  "scripDetails": {
    "bseScripCode": "506395",
    "scripName": "COROMANDEL",
    "bseTickr": "COROMANDEL",
    "nseTickr": null,
    "isin": "INE169A01031"
  },
  "linkDetail": {
    "shortLink": "https://sqst.in/qZcls"
  },
  "creationTime": 1716889085,
  "filterCategory": "TECHNICAL_IDEA"
}
```


## UNCLASSIFIED — filterCategory

Updates that do not fit into any of the above categories — including NCLT orders, restructuring notices, and other miscellaneous exchange filings.

> Example for Filter Category — UNCLASSIFIED

```json
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
  "creationTime": 1718292417,
  "filterCategory": "UNCLASSIFIED"
}
```
