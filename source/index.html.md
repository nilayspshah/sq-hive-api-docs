---
title: Sample API v1
language_tabs:
  - ruby: Ruby
  - python: Python
language_clients:
  - ruby: ""
  - python: ""
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

## editSurveyDiscount

<a id="opIdeditSurveyDiscount"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.put 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/marketing/survey/discount/create',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.put('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/marketing/survey/discount/create', headers = headers)

print(r.json())

```

`PUT /api/v1/marketing/survey/discount/create`

> Body parameter

```json
{
  "surveyIds": [
    0
  ],
  "bodyValues": [
    "string"
  ]
}
```

<h3 id="editsurveydiscount-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[CumulativeDiscountReminderMessageEditRequest](#schemacumulativediscountremindermessageeditrequest)|true|none|

> Example responses

> 200 Response

<h3 id="editsurveydiscount-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="editsurveydiscount-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[DiscountReminderMessageResponseDto](#schemadiscountremindermessageresponsedto)]|false|none|none|
|» id|integer(int64)|false|none|none|
|» creationTime|integer(int64)|false|none|none|
|» userId|integer(int64)|false|none|none|
|» countryCode|string|false|none|none|
|» mobileNumber|integer(int64)|false|none|none|
|» createdByUserId|integer(int64)|false|none|none|
|» scheduledNextMessageTime|integer(int64)|false|none|none|
|» scheduledNextMessageType|string|false|none|none|
|» scheduledNextMessageReminderType|string|false|none|none|
|» noOfTimesReminderMessagesToBeSent|integer(int32)|false|none|none|
|» noOfTimesReminderMessagesAlreadySent|integer(int32)|false|none|none|
|» startTime|integer(int64)|false|none|none|
|» endTime|integer(int64)|false|none|none|
|» sentMessageLog|[[DiscountReminderSentMessage](#schemadiscountremindersentmessage)]|false|none|none|
|»» messageSentReceipt|string|false|none|none|
|»» id|string|false|none|none|
|»» creationTime|integer(int64)|false|none|none|
|»» messageType|string|false|none|none|
|»» reminderType|string|false|none|none|
|» templateId|string|false|none|none|
|» userPaidMarkTime|integer(int64)|false|none|none|
|» surveyStatus|string|false|none|none|
|» surveyType|string|false|none|none|
|» reminderTimes|[integer]|false|none|none|
|» bodyValues|[string]|false|none|none|
|» ctaValue|string|false|none|none|
|» headerValue|string|false|none|none|
|» headerType|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|scheduledNextMessageType|MARKETING_REMINDER|
|scheduledNextMessageReminderType|FIRST_MESSAGE|
|scheduledNextMessageReminderType|FOLLOW_UP|
|scheduledNextMessageReminderType|FINAL_MESSAGE|
|messageType|MARKETING_REMINDER|
|reminderType|FIRST_MESSAGE|
|reminderType|FOLLOW_UP|
|reminderType|FINAL_MESSAGE|
|surveyStatus|CREATED|
|surveyStatus|REMINDER_SENT|
|surveyStatus|USER_PAID|
|surveyStatus|REMINDER_COMPLETE|
|surveyStatus|USER_UNSUBSCRIBED|
|surveyType|TRIAL_USER_FEEDBACK|
|surveyType|CONVERT_TRIAL_TO_PAID_SURVEY_CASUAL|
|surveyType|CONVERT_TRIAL_TO_PAID_SURVEY_CORPORATE|
|surveyType|FLASH_SALE|
|surveyType|FESTIVE_DISCOUNT|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## createDiscountReminderSurvey

<a id="opIdcreateDiscountReminderSurvey"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/marketing/survey/discount/create',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/marketing/survey/discount/create', headers = headers)

print(r.json())

```

`POST /api/v1/marketing/survey/discount/create`

> Body parameter

```json
{
  "userId": [
    0
  ],
  "startTime": "2019-08-24T14:15:22Z",
  "endTime": "2019-08-24T14:15:22Z",
  "noOfTimesRemindersToBeSent": 0,
  "reminderTimes": [
    "2019-08-24T14:15:22Z"
  ],
  "templateId": "string",
  "bodyValues": [
    "string"
  ],
  "appendCtaValue": "string",
  "headerValue": "string",
  "headerType": "string",
  "initiationType": "IMMEDIATE",
  "surveyName": "TRIAL_USER_FEEDBACK"
}
```

<h3 id="creatediscountremindersurvey-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[CumulativeDiscountReminderMessageRequest](#schemacumulativediscountremindermessagerequest)|true|none|

> Example responses

> 200 Response

<h3 id="creatediscountremindersurvey-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[CumulativeReminderMessageResponse](#schemacumulativeremindermessageresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## triggerSurveyDiscount

<a id="opIdtriggerSurveyDiscount"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/marketing/survey/discount/trigger',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/marketing/survey/discount/trigger', headers = headers)

print(r.json())

```

`POST /api/v1/marketing/survey/discount/trigger`

> Body parameter

```json
[
  {
    "userId": "string"
  }
]
```

<h3 id="triggersurveydiscount-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[DiscountMessageSurveySurveyTriggerRequestDto](#schemadiscountmessagesurveysurveytriggerrequestdto)|true|none|

<h3 id="triggersurveydiscount-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## createPaymentMandateForUser_6

<a id="opIdcreatePaymentMandateForUser_6"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/marketing/discount/trigger',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/marketing/discount/trigger', headers = headers)

print(r.json())

```

`POST /api/v1/marketing/discount/trigger`

> Body parameter

```json
{
  "userIds": [
    0
  ],
  "heading": "string",
  "plan": "string",
  "validity": "string",
  "templateId": "string",
  "chatLink": "string",
  "redirectionLink": "string"
}
```

<h3 id="createpaymentmandateforuser_6-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[MarketingRequestUserIdListDto](#schemamarketingrequestuseridlistdto)|true|none|

> Example responses

> 200 Response

<h3 id="createpaymentmandateforuser_6-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[MarketingResponseDto](#schemamarketingresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

<h1 id="sample-api-corporate-domain-controller">corporate-domain-controller</h1>

## updateCorporateDomain

<a id="opIdupdateCorporateDomain"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.put 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/corporateDomains/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.put('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/corporateDomains/{id}', headers = headers)

print(r.json())

```

`PUT /api/v1/admin/corporateDomains/{id}`

> Body parameter

```json
{
  "id": "string",
  "website": "string",
  "companyName": "string",
  "industry": "string",
  "budgetForFreeUser": 400,
  "status": "PRIVILEGED"
}
```

<h3 id="updatecorporatedomain-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|
|body|body|[CorporateDomainUpdateRequestDto](#schemacorporatedomainupdaterequestdto)|true|none|

> Example responses

> 200 Response

<h3 id="updatecorporatedomain-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[CorporateDomainUpdateResponseDto](#schemacorporatedomainupdateresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## getCorporateDomains

<a id="opIdgetCorporateDomains"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.get 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/corporateDomains',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.get('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/corporateDomains', headers = headers)

print(r.json())

```

`GET /api/v1/admin/corporateDomains`

<h3 id="getcorporatedomains-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|pageNo|query|integer(int32)|false|none|
|pageSize|query|integer(int32)|false|none|
|sortBy|query|string|false|none|
|sortDirection|query|string|false|none|
|status|query|string|false|none|
|search|query|string|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|status|ALL|
|status|PRIVILEGED|
|status|NOT_PRIVILEGED|
|status|UNDETERMINED|

> Example responses

> 200 Response

<h3 id="getcorporatedomains-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[PageCorporateDomainResponseDto](#schemapagecorporatedomainresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

<h1 id="sample-api-user-verification-controller">user-verification-controller</h1>

## formPost

<a id="opIdformPost"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/users/verification/email-verification',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/users/verification/email-verification', headers = headers)

print(r.json())

```

`POST /api/v1/users/verification/email-verification`

> Example responses

> 200 Response

<h3 id="formpost-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|string|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

<h1 id="sample-api-user-corporate-information-controller">user-corporate-information-controller</h1>

## backPopulateUserCorporateInformation

<a id="opIdbackPopulateUserCorporateInformation"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/users/userCorporateInformation/backPopulate',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/users/userCorporateInformation/backPopulate', headers = headers)

print(r.json())

```

`POST /api/v1/users/userCorporateInformation/backPopulate`

> Body parameter

```json
{
  "userIds": [
    0
  ]
}
```

<h3 id="backpopulateusercorporateinformation-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[BackPopulateUserCorporateInformationRequestDto](#schemabackpopulateusercorporateinformationrequestdto)|true|none|

> Example responses

> 200 Response

<h3 id="backpopulateusercorporateinformation-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[BackPopulateUserCorporateInformationResponseDto](#schemabackpopulateusercorporateinformationresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

<h1 id="sample-api-user-authentication-controller">user-authentication-controller</h1>

## signup

<a id="opIdsignup"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/users/signup',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/users/signup', headers = headers)

print(r.json())

```

`POST /api/v1/users/signup`

> Body parameter

```json
{
  "countryCode": "string",
  "mobileNumber": 0,
  "userType": "RETAIL_USER",
  "referralCode": "string",
  "email": "string"
}
```

<h3 id="signup-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[UserCreationRequestDto](#schemausercreationrequestdto)|true|none|

> Example responses

> 200 Response

<h3 id="signup-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|string|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## generateOtpForLogin

<a id="opIdgenerateOtpForLogin"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/users/generate-login-otp',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/users/generate-login-otp', headers = headers)

print(r.json())

```

`POST /api/v1/users/generate-login-otp`

> Body parameter

```json
{
  "countryCode": "string",
  "mobileNumber": 0,
  "referralCode": "string",
  "referralSource": "string"
}
```

<h3 id="generateotpforlogin-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[GenerateOtpRequestDto](#schemagenerateotprequestdto)|true|none|

> Example responses

> 200 Response

<h3 id="generateotpforlogin-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[GenerateOtpResponseDto](#schemagenerateotpresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## updateUserEmailId

<a id="opIdupdateUserEmailId"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/users/email/update',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/users/email/update', headers = headers)

print(r.json())

```

`POST /api/v1/users/email/update`

> Body parameter

```json
{
  "email": "string",
  "name": "string"
}
```

<h3 id="updateuseremailid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[UserEmailUpdateRequestDto](#schemauseremailupdaterequestdto)|true|none|

> Example responses

> 200 Response

<h3 id="updateuseremailid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[UserEmailUpdateEmailResponseDto](#schemauseremailupdateemailresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## updateCorporateEmailDetails

<a id="opIdupdateCorporateEmailDetails"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/users/email/corporate/update',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/users/email/corporate/update', headers = headers)

print(r.json())

```

`POST /api/v1/users/email/corporate/update`

> Body parameter

```json
{
  "website": "string",
  "designation": "string",
  "companyProfile": "string",
  "companyName": "string",
  "companyId": 0
}
```

<h3 id="updatecorporateemaildetails-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[CorporateEmailUpdateRequestDto](#schemacorporateemailupdaterequestdto)|true|none|

> Example responses

> 200 Response

<h3 id="updatecorporateemaildetails-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[UserCorporateInformationResponseDto](#schemausercorporateinformationresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## continueWithMobile

<a id="opIdcontinueWithMobile"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/users/continue-with-mobile',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/users/continue-with-mobile', headers = headers)

print(r.json())

```

`POST /api/v1/users/continue-with-mobile`

> Body parameter

```json
{
  "key": "string",
  "otp": 0,
  "userType": "NEW"
}
```

<h3 id="continuewithmobile-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[ContinueWithMobileRequestDto](#schemacontinuewithmobilerequestdto)|true|none|

> Example responses

> 200 Response

<h3 id="continuewithmobile-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[ContinueWithMobileResponseDto](#schemacontinuewithmobileresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## resendOtp

<a id="opIdresendOtp"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/users/auth/resend',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/users/auth/resend', headers = headers)

print(r.json())

```

`POST /api/v1/users/auth/resend`

> Body parameter

```json
{
  "signupStatus": "NEW",
  "txnId": "string"
}
```

<h3 id="resendotp-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[GenerateOtpResponseDto](#schemagenerateotpresponsedto)|true|none|

> Example responses

> 200 Response

<h3 id="resendotp-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="resendotp-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## continueWithMobileForAdmin

<a id="opIdcontinueWithMobileForAdmin"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/users/admin/continue-with-mobile',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/users/admin/continue-with-mobile', headers = headers)

print(r.json())

```

`POST /api/v1/users/admin/continue-with-mobile`

> Body parameter

```json
{
  "key": "string",
  "otp": 0,
  "userType": "NEW"
}
```

<h3 id="continuewithmobileforadmin-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[ContinueWithMobileRequestDto](#schemacontinuewithmobilerequestdto)|true|none|

> Example responses

> 200 Response

<h3 id="continuewithmobileforadmin-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[ContinueWithMobileResponseDto](#schemacontinuewithmobileresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## getUserProfileDetails

<a id="opIdgetUserProfileDetails"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.get 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/users/profile',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.get('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/users/profile', headers = headers)

print(r.json())

```

`GET /api/v1/users/profile`

> Example responses

> 200 Response

<h3 id="getuserprofiledetails-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[UserProfileResponseDto](#schemauserprofileresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## getMe

<a id="opIdgetMe"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.get 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/users/me',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Authorization': 'Basic {access-token}'
}

r = requests.get('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/users/me', headers = headers)

print(r.json())

```

`GET /api/v1/users/me`

<h3 id="getme-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

<h1 id="sample-api-user-notification-preference-controller">user-notification-preference-controller</h1>

## updateUserProfilingQuestion

<a id="opIdupdateUserProfilingQuestion"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/users/preferences/profiling',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/users/preferences/profiling', headers = headers)

print(r.json())

```

`POST /api/v1/users/preferences/profiling`

> Body parameter

```json
{
  "investmentPreference": "FUNDAMENTAL_BASED",
  "tradingFrequency": "EVERY_DAY",
  "profession": "FULL_TIME_TRADER"
}
```

<h3 id="updateuserprofilingquestion-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[UserProfilingQuestionRequestDto](#schemauserprofilingquestionrequestdto)|true|none|

> Example responses

> 200 Response

<h3 id="updateuserprofilingquestion-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[UserProfilingQuestionResponseDto](#schemauserprofilingquestionresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## getUserNotificationPreference

<a id="opIdgetUserNotificationPreference"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.get 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/users/preferences/notifications',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.get('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/users/preferences/notifications', headers = headers)

print(r.json())

```

`GET /api/v1/users/preferences/notifications`

> Example responses

> 200 Response

<h3 id="getusernotificationpreference-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[UserNotificationPreferenceResponseDto](#schemausernotificationpreferenceresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## updateUserInstrumentTracking

<a id="opIdupdateUserInstrumentTracking"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/users/preferences/notifications',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/users/preferences/notifications', headers = headers)

print(r.json())

```

`POST /api/v1/users/preferences/notifications`

> Body parameter

```json
{
  "generalNewsPreference": "NONE",
  "technicalAnalysisPreference": "NONE",
  "stopUserNotification": true
}
```

<h3 id="updateuserinstrumenttracking-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[UserNotificationPreferenceUpdateRequestDto](#schemausernotificationpreferenceupdaterequestdto)|true|none|

> Example responses

> 200 Response

<h3 id="updateuserinstrumenttracking-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[UserNotificationPreferenceResponseDto](#schemausernotificationpreferenceresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## updateUserInstrumentTracking_1

<a id="opIdupdateUserInstrumentTracking_1"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/users/preferences/categoryFilter',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/users/preferences/categoryFilter', headers = headers)

print(r.json())

```

`POST /api/v1/users/preferences/categoryFilter`

> Body parameter

```json
{
  "userId": 0,
  "category": "KEY_UPDATE",
  "filterScope": "NONE"
}
```

<h3 id="updateuserinstrumenttracking_1-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[UserInstrumentUpdateCategoryFilterMappingRequestDto](#schemauserinstrumentupdatecategoryfiltermappingrequestdto)|true|none|

> Example responses

> 200 Response

<h3 id="updateuserinstrumenttracking_1-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[UserInstrumentUpdateCategoryFilterMappingResponseDto](#schemauserinstrumentupdatecategoryfiltermappingresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## updateUserInstrumentTracking_5

<a id="opIdupdateUserInstrumentTracking_5"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.get 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/users/preferences/categoryFilters',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.get('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/users/preferences/categoryFilters', headers = headers)

print(r.json())

```

`GET /api/v1/users/preferences/categoryFilters`

> Example responses

> 200 Response

<h3 id="updateuserinstrumenttracking_5-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[CumulativeUserInstrumentUpdateCategoryFilterMappingResponseDto](#schemacumulativeuserinstrumentupdatecategoryfiltermappingresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

<h1 id="sample-api-user-discount-controller">user-discount-controller</h1>

## createPricingInformation

<a id="opIdcreatePricingInformation"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/userDiscounts/plans',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/userDiscounts/plans', headers = headers)

print(r.json())

```

`POST /api/v1/userDiscounts/plans`

> Body parameter

```json
{
  "userIds": [
    0
  ],
  "couponCode": "string",
  "startTime": "2019-08-24T14:15:22Z",
  "endTime": "2019-08-24T14:15:22Z"
}
```

<h3 id="createpricinginformation-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[UserDiscountPlanCreationRequestDto](#schemauserdiscountplancreationrequestdto)|true|none|

> Example responses

> 200 Response

```json
{
  "totalCount": 0,
  "successCount": 0,
  "failureCount": 0,
  "failedDiscounts": [
    {
      "user": 0,
      "isSuccess": true,
      "reason": "string",
      "success": true
    }
  ]
}
```

<h3 id="createpricinginformation-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[CumulativeUserDiscountPlanResponseDto](#schemacumulativeuserdiscountplanresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## getCurrentUserDiscounts

<a id="opIdgetCurrentUserDiscounts"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.get 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/userDiscounts/currentDiscounts',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Basic {access-token}'
}

r = requests.get('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/userDiscounts/currentDiscounts', headers = headers)

print(r.json())

```

`GET /api/v1/userDiscounts/currentDiscounts`

> Example responses

> 200 Response

```json
{
  "isDiscountOnBasicMonthly": true,
  "isDiscountOnProfessionalMonthly": true,
  "isDiscountOnPowerUserMonthly": true,
  "isDiscountOnBasicYearly": true,
  "isDiscountOnProfessionalYearly": true,
  "isDiscountOnPowerUserYearly": true,
  "basicDiscountTextMonthly": "string",
  "professionalDiscountTextMonthly": "string",
  "powerUserDiscountTextMonthly": "string",
  "basicDiscountTextYearly": "string",
  "professionalDiscountTextYearly": "string",
  "powerUserDiscountTextYearly": "string"
}
```

<h3 id="getcurrentuserdiscounts-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[CurrentUserDiscountResponseDto](#schemacurrentuserdiscountresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

<h1 id="sample-api-smallcase-controller">smallcase-controller</h1>

## acceptIncomingWebhookFromSmallcase

<a id="opIdacceptIncomingWebhookFromSmallcase"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/smallcase/webhooks/accept',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/smallcase/webhooks/accept', headers = headers)

print(r.json())

```

`POST /api/v1/smallcase/webhooks/accept`

> Body parameter

```json
{}
```

<h3 id="acceptincomingwebhookfromsmallcase-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[JsonNode](#schemajsonnode)|true|none|

> Example responses

> 200 Response

<h3 id="acceptincomingwebhookfromsmallcase-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="acceptincomingwebhookfromsmallcase-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## createTransactionForUser

<a id="opIdcreateTransactionForUser"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/smallcase/transactions',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/smallcase/transactions', headers = headers)

print(r.json())

```

`POST /api/v1/smallcase/transactions`

> Body parameter

```json
{
  "brokerName": "string",
  "brokerSymbol": "string"
}
```

<h3 id="createtransactionforuser-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[SmallcaseTransactionCreationRequestDto](#schemasmallcasetransactioncreationrequestdto)|true|none|

> Example responses

> 200 Response

<h3 id="createtransactionforuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[SmallcaseTransactionCreationResponseDto](#schemasmallcasetransactioncreationresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## postSmallcaseTransactionResponse

<a id="opIdpostSmallcaseTransactionResponse"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/smallcase/transactions/postback/success',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/smallcase/transactions/postback/success', headers = headers)

print(r.json())

```

`POST /api/v1/smallcase/transactions/postback/success`

> Body parameter

```json
{
  "smallcaseAuthToken": "string",
  "transactionId": "string",
  "broker": "string",
  "success": "string"
}
```

<h3 id="postsmallcasetransactionresponse-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[SmallcaseHoldingSuccessPostbackRequestDto](#schemasmallcaseholdingsuccesspostbackrequestdto)|true|none|

> Example responses

> 200 Response

<h3 id="postsmallcasetransactionresponse-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[SmallcaseHoldingSuccessPostbackResponseDto](#schemasmallcaseholdingsuccesspostbackresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## fetchHoldings

<a id="opIdfetchHoldings"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/smallcase/transactions/holdings/fetch',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/smallcase/transactions/holdings/fetch', headers = headers)

print(r.json())

```

`POST /api/v1/smallcase/transactions/holdings/fetch`

<h3 id="fetchholdings-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

<h1 id="sample-api-pricing-controller">pricing-controller</h1>

## getPricingPlans

<a id="opIdgetPricingPlans"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.get 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/pricing/plans',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Basic {access-token}'
}

r = requests.get('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/pricing/plans', headers = headers)

print(r.json())

```

`GET /api/v1/pricing/plans`

> Example responses

> 200 Response

```json
{
  "pricingInformationList": [
    {
      "name": "string",
      "planType": "BASIC",
      "planFrequency": "MONTHLY",
      "maximumAmount": 0,
      "minimumPaymentCount": 0,
      "mandateStrategy": "FIRST_CYCLE_DISCOUNT",
      "firstPaymentAmount": 0,
      "mandateFrequency": "ONETIME",
      "initialWindowSizeInDays": 0,
      "schemeReferenceId": "string",
      "firstPaymentBaseAmount": 0,
      "firstPaymentTaxAmount": 0,
      "firstPaymentNonRoundedTotalAmount": 0,
      "firstPaymentRoundedTotalAmount": 0,
      "maximumBaseAmount": 0,
      "maximumTaxAmount": 0,
      "maximumNonRoundedTotalAmount": 0,
      "maximumRoundedTotalAmount": 0,
      "stockTrackingLimit": 0,
      "couponCode": "string",
      "isDiscounted": true,
      "discountPercent": 0,
      "cancelledPerMonthPrice": 0,
      "subscriptionAmountType": "FIX"
    }
  ]
}
```

<h3 id="getpricingplans-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[MultiplePricingDetailResponse](#schemamultiplepricingdetailresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## createPricingInformation_1

<a id="opIdcreatePricingInformation_1"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/pricing/plans',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/pricing/plans', headers = headers)

print(r.json())

```

`POST /api/v1/pricing/plans`

> Body parameter

```json
{
  "pricingDetail": [
    {
      "name": "string",
      "planType": "BASIC",
      "frequency": "MONTHLY",
      "maximumAmount": 0,
      "firstPaymentAmount": 0,
      "minimumPaymentCount": 0,
      "mandateStrategy": "FIRST_CYCLE_DISCOUNT",
      "mandateFrequency": "ONETIME",
      "initialWindowSizeInDays": 0,
      "firstPaymentBaseAmount": 0,
      "firstPaymentTaxAmount": 0,
      "firstPaymentNonRoundedTotalAmount": 0,
      "firstPaymentRoundedTotalAmount": 0,
      "maximumBaseAmount": 0,
      "maximumTaxAmount": 0,
      "maximumNonRoundedTotalAmount": 0,
      "maximumRoundedTotalAmount": 0,
      "stockTrackingLimit": 0,
      "couponCode": "string",
      "isDiscounted": true,
      "discountPercent": 0,
      "cancelledPerMonthPrice": 0,
      "subscriptionAmountType": "FIX"
    }
  ]
}
```

<h3 id="createpricinginformation_1-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[MultiplePricingDetailRequestDto](#schemamultiplepricingdetailrequestdto)|true|none|

> Example responses

> 200 Response

```json
{
  "pricingInformationList": [
    {
      "name": "string",
      "planType": "BASIC",
      "planFrequency": "MONTHLY",
      "maximumAmount": 0,
      "minimumPaymentCount": 0,
      "mandateStrategy": "FIRST_CYCLE_DISCOUNT",
      "firstPaymentAmount": 0,
      "mandateFrequency": "ONETIME",
      "initialWindowSizeInDays": 0,
      "schemeReferenceId": "string",
      "firstPaymentBaseAmount": 0,
      "firstPaymentTaxAmount": 0,
      "firstPaymentNonRoundedTotalAmount": 0,
      "firstPaymentRoundedTotalAmount": 0,
      "maximumBaseAmount": 0,
      "maximumTaxAmount": 0,
      "maximumNonRoundedTotalAmount": 0,
      "maximumRoundedTotalAmount": 0,
      "stockTrackingLimit": 0,
      "couponCode": "string",
      "isDiscounted": true,
      "discountPercent": 0,
      "cancelledPerMonthPrice": 0,
      "subscriptionAmountType": "FIX"
    }
  ]
}
```

<h3 id="createpricinginformation_1-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[MultiplePricingDetailResponse](#schemamultiplepricingdetailresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

<h1 id="sample-api-paytm-subscription-controller">paytm-subscription-controller</h1>

## processSubscriptionWebhook

<a id="opIdprocessSubscriptionWebhook"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/paytm/subscriptions/webhook',
  params: {
  'paramMap' => '[MultiValueMapStringString](#schemamultivaluemapstringstring)'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/paytm/subscriptions/webhook', params={
  'paramMap': {
  "all": {
    "property1": "string",
    "property2": "string"
  },
  "empty": true,
  "property1": [
    "string"
  ],
  "property2": [
    "string"
  ]
}
}, headers = headers)

print(r.json())

```

`POST /api/v1/payments/paytm/subscriptions/webhook`

<h3 id="processsubscriptionwebhook-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|paramMap|query|[MultiValueMapStringString](#schemamultivaluemapstringstring)|true|none|

<h3 id="processsubscriptionwebhook-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## getTransactionStatus

<a id="opIdgetTransactionStatus"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/paytm/subscriptions/transactions/status',
  params: {
  'orderIds' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/paytm/subscriptions/transactions/status', params={
  'orderIds': 'string'
}, headers = headers)

print(r.json())

```

`POST /api/v1/payments/paytm/subscriptions/transactions/status`

<h3 id="gettransactionstatus-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|orderIds|query|string|true|none|

> Example responses

> 200 Response

<h3 id="gettransactionstatus-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="gettransactionstatus-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[TransactionStatusResponseDto](#schematransactionstatusresponsedto)]|false|none|none|
|» body|[TransactionStatusResponseBodyDto](#schematransactionstatusresponsebodydto)|false|none|none|
|»» userId|string|false|none|none|
|»» schemeRefId|string|false|none|none|
|»» resultInfo|[TransactionStatusResponseResultInfo](#schematransactionstatusresponseresultinfo)|false|none|none|
|»»» resultCode|string|false|none|none|
|»»» resultStatus|string|false|none|none|
|»»» resultMsg|string|false|none|none|
|»» txnId|string|false|none|none|
|»» bankTxnId|string|false|none|none|
|»» orderId|string|false|none|none|
|»» txnAmount|number|false|none|none|
|»» txnType|string|false|none|none|
|»» gatewayName|string|false|none|none|
|»» gatewayInfo|string|false|none|none|
|»» bankName|string|false|none|none|
|»» mid|string|false|none|none|
|»» paymentMode|string|false|none|none|
|»» txnDate|string|false|none|none|
|»» subsId|string|false|none|none|
|»» merchantUniqueReference|string|false|none|none|
|»» udf1|string|false|none|none|
|»» udf2|string|false|none|none|
|» head|[TransactionStatusResponseHeadDto](#schematransactionstatusresponseheaddto)|false|none|none|
|»» responseTimestamp|string|false|none|none|
|»» signature|string|false|none|none|
|»» version|string|false|none|none|
|»» channelId|string|false|none|none|
|»» clientId|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|resultStatus|TXN_SUCCESS|
|resultStatus|TXN_FAILURE|
|resultStatus|PENDING|
|resultStatus|NO_RECORD_FOUND|
|paymentMode|CC|
|paymentMode|DC|
|paymentMode|PPI|
|paymentMode|BANK_MANDATE|
|paymentMode|UPI|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## processSubscriptionStatusWebhook

<a id="opIdprocessSubscriptionStatusWebhook"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/paytm/subscriptions/status/webhook',
  params: {
  'paramMap' => '[MultiValueMapStringString](#schemamultivaluemapstringstring)'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/paytm/subscriptions/status/webhook', params={
  'paramMap': {
  "all": {
    "property1": "string",
    "property2": "string"
  },
  "empty": true,
  "property1": [
    "string"
  ],
  "property2": [
    "string"
  ]
}
}, headers = headers)

print(r.json())

```

`POST /api/v1/payments/paytm/subscriptions/status/webhook`

<h3 id="processsubscriptionstatuswebhook-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|paramMap|query|[MultiValueMapStringString](#schemamultivaluemapstringstring)|true|none|

<h3 id="processsubscriptionstatuswebhook-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## revokeSubscriptionMandate

<a id="opIdrevokeSubscriptionMandate"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/paytm/subscriptions/revoke',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/paytm/subscriptions/revoke', headers = headers)

print(r.json())

```

`POST /api/v1/payments/paytm/subscriptions/revoke`

> Body parameter

```json
{
  "subscriptionId": "string",
  "internalOrderId": "string"
}
```

<h3 id="revokesubscriptionmandate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[PaytmSubscriptionRevocationRequest](#schemapaytmsubscriptionrevocationrequest)|true|none|

<h3 id="revokesubscriptionmandate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## renewSubscription

<a id="opIdrenewSubscription"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/paytm/subscriptions/renew',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/paytm/subscriptions/renew', headers = headers)

print(r.json())

```

`POST /api/v1/payments/paytm/subscriptions/renew`

> Body parameter

```json
{
  "subscriptionIds": [
    "string"
  ],
  "noOfDays": 0
}
```

<h3 id="renewsubscription-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[RenewSubscriptionsList](#schemarenewsubscriptionslist)|true|none|

> Example responses

> 200 Response

<h3 id="renewsubscription-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="renewsubscription-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[IndividualRenewSubscriptionResponseDto](#schemaindividualrenewsubscriptionresponsedto)]|false|none|none|
|» subscriptionId|string|false|none|none|
|» paytmTxnId|string|false|none|none|
|» orderId|string|false|none|none|
|» transactionDate|string|false|none|none|
|» amount|string|false|none|none|
|» responseResultInfoDto|[InitiateSubscriptionResponseResultInfoDto](#schemainitiatesubscriptionresponseresultinfodto)|false|none|none|
|»» resultStatus|string|false|none|none|
|»» resultCode|string|false|none|none|
|»» resultMsg|string|false|none|none|
|» preNotificationPaytmReference|string|false|none|none|
|» preNotificationInternalReference|string|false|none|none|
|» exceptionMessage|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|resultStatus|S|
|resultStatus|F|
|resultStatus|U|
|resultStatus|TXN_FAILURE|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## renewSubscriptionDirect

<a id="opIdrenewSubscriptionDirect"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/paytm/subscriptions/renew/direct',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/paytm/subscriptions/renew/direct', headers = headers)

print(r.json())

```

`POST /api/v1/payments/paytm/subscriptions/renew/direct`

> Body parameter

```json
{
  "subscriptionId": "string",
  "debitDate": "2019-08-24",
  "schemeRefId": "string",
  "custId": "string",
  "amount": 0
}
```

<h3 id="renewsubscriptiondirect-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[RenewSubscriptionDirectly](#schemarenewsubscriptiondirectly)|true|none|

> Example responses

> 200 Response

<h3 id="renewsubscriptiondirect-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[RenewSubscriptionResponseDto](#schemarenewsubscriptionresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## paytmPreNotifySubscriptions_1

<a id="opIdpaytmPreNotifySubscriptions_1"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.get 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/paytm/subscriptions/preNotify',
  params: {
  'requestDto' => '[PaytmPreNotificationStatusRequestDto](#schemapaytmprenotificationstatusrequestdto)'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.get('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/paytm/subscriptions/preNotify', params={
  'requestDto': {
  "subscriptionId": "string",
  "preNotificationPaytmReferenceId": "string"
}
}, headers = headers)

print(r.json())

```

`GET /api/v1/payments/paytm/subscriptions/preNotify`

<h3 id="paytmprenotifysubscriptions_1-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|requestDto|query|[PaytmPreNotificationStatusRequestDto](#schemapaytmprenotificationstatusrequestdto)|true|none|

> Example responses

> 200 Response

<h3 id="paytmprenotifysubscriptions_1-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[PreNotifyCheckStatusResponseDto](#schemaprenotifycheckstatusresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## paytmPreNotifySubscriptions

<a id="opIdpaytmPreNotifySubscriptions"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/paytm/subscriptions/preNotify',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/paytm/subscriptions/preNotify', headers = headers)

print(r.json())

```

`POST /api/v1/payments/paytm/subscriptions/preNotify`

> Body parameter

```json
{
  "subscriptionIds": [
    "string"
  ],
  "noOfDays": 0
}
```

<h3 id="paytmprenotifysubscriptions-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[RenewSubscriptionsList](#schemarenewsubscriptionslist)|true|none|

> Example responses

> 200 Response

<h3 id="paytmprenotifysubscriptions-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[PaytmPreNotificationResponseListDto](#schemapaytmprenotificationresponselistdto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## createPaymentMandateForUser

<a id="opIdcreatePaymentMandateForUser"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/paytm/subscriptions/postback/success',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/paytm/subscriptions/postback/success', headers = headers)

print(r.json())

```

`POST /api/v1/payments/paytm/subscriptions/postback/success`

> Body parameter

```json
{
  "BANKTXNID": "string",
  "CHECKSUMHASH": "string",
  "CURRENCY": "string",
  "GATEWAYNAME": "string",
  "MERC_UNQ_REF": "string",
  "MID": "string",
  "ORDERID": "string",
  "PAYMENTMODE": "string",
  "RESPCODE": "string",
  "RESPMSG": "string",
  "STATUS": "TXN_SUCCESS",
  "SUBS_ID": "string",
  "TXNAMOUNT": 0,
  "TXNDATE": "string",
  "TXNID": "string",
  "UDF_1": "string",
  "UDF_2": "string"
}
```

<h3 id="createpaymentmandateforuser-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[PaytmSubscriptionPostbackSuccessDto](#schemapaytmsubscriptionpostbacksuccessdto)|true|none|

> Example responses

> 200 Response

<h3 id="createpaymentmandateforuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DigioManadateCreationSuccessPostbackResponseDto](#schemadigiomanadatecreationsuccesspostbackresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## getTransactionStatus_1

<a id="opIdgetTransactionStatus_1"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/paytm/subscriptions/override/payments/status/webhook',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/paytm/subscriptions/override/payments/status/webhook', headers = headers)

print(r.json())

```

`POST /api/v1/payments/paytm/subscriptions/override/payments/status/webhook`

> Body parameter

```json
{
  "ORDERID": "string",
  "MID": "string",
  "TXNID": "string",
  "TXNAMOUNT": 0,
  "PAYMENTMODE": "CC",
  "CURRENCY": "INR",
  "TXNDATETIME": "2019-08-24T14:15:22Z",
  "TXNDATE": "2019-08-24",
  "STATUS": "TXN_SUCCESS",
  "RESPCODE": "string",
  "RESPMSG": "string",
  "GATEWAYNAME": "string",
  "BANKTXNID": "string",
  "CHECKSUMHASH": "string",
  "MERC_UNQ_REF": "string",
  "udf_1": "string",
  "udf_2": "string"
}
```

<h3 id="gettransactionstatus_1-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[PaytmPaymentStatusWebhook](#schemapaytmpaymentstatuswebhook)|true|none|

<h3 id="gettransactionstatus_1-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## getTransactionStatus_2

<a id="opIdgetTransactionStatus_2"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/paytm/subscriptions/override/payments/prenotification/webhook',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/paytm/subscriptions/override/payments/prenotification/webhook', headers = headers)

print(r.json())

```

`POST /api/v1/payments/paytm/subscriptions/override/payments/prenotification/webhook`

> Body parameter

```json
{
  "TXNDATE": "2019-08-24T14:15:22Z",
  "TXNMESSAGE": "string",
  "REFERENCEID": "string",
  "CHECKSUMHASH": "string",
  "NOTIFICATIONDATE": "2019-08-24T14:15:22Z",
  "NOTIFICATIONSTATUS": "SUCCESS",
  "NOTIFICATIONSTATUSCODE": "string",
  "NOTIFICATIONSTATUSMESSAGE": "string"
}
```

<h3 id="gettransactionstatus_2-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[PaytmPreNotificationUpdateWebhook](#schemapaytmprenotificationupdatewebhook)|true|none|

<h3 id="gettransactionstatus_2-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## createPaymentMandateForUser_1

<a id="opIdcreatePaymentMandateForUser_1"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/paytm/subscriptions/create',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/paytm/subscriptions/create', headers = headers)

print(r.json())

```

`POST /api/v1/payments/paytm/subscriptions/create`

> Body parameter

```json
{
  "plan": "BASIC",
  "frequency": "MONTHLY",
  "discountCode": "string"
}
```

<h3 id="createpaymentmandateforuser_1-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[PaytmSubscriptionCreationRequestDto](#schemapaytmsubscriptioncreationrequestdto)|true|none|

> Example responses

> 200 Response

<h3 id="createpaymentmandateforuser_1-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[PaytmSubscriptionCreationResponseDto](#schemapaytmsubscriptioncreationresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## cancelSubscriptionResponseDtos

<a id="opIdcancelSubscriptionResponseDtos"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/paytm/subscriptions/cancel',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/paytm/subscriptions/cancel', headers = headers)

print(r.json())

```

`POST /api/v1/payments/paytm/subscriptions/cancel`

> Body parameter

```json
{
  "subscriptionIds": [
    "string"
  ],
  "noOfDays": 0
}
```

<h3 id="cancelsubscriptionresponsedtos-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[RenewSubscriptionsList](#schemarenewsubscriptionslist)|true|none|

> Example responses

> 200 Response

<h3 id="cancelsubscriptionresponsedtos-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="cancelsubscriptionresponsedtos-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[CancelSubscriptionResponseDto](#schemacancelsubscriptionresponsedto)]|false|none|none|
|» head|[CancelSubscriptionResponseHeadDto](#schemacancelsubscriptionresponseheaddto)|false|none|none|
|»» responseTimestamp|string|false|none|none|
|»» signature|string|false|none|none|
|» body|[CancelSubscriptionResponseBodyDto](#schemacancelsubscriptionresponsebodydto)|false|none|none|
|»» resultInfo|[CancelSubscriptionResultInfoResponseDto](#schemacancelsubscriptionresultinforesponsedto)|false|none|none|
|»»» status|string|false|none|none|
|»»» code|string|false|none|none|
|»»» message|string|false|none|none|
|»» mid|string|false|none|none|
|»» subsId|string|false|none|none|
|»» custId|string|false|none|none|
|»» createdDate|string|false|none|none|
|»» expiryDate|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|SUCCESS|
|status|FAILURE|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## getSubscriptionStatus

<a id="opIdgetSubscriptionStatus"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.get 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/paytm/subscriptions/status',
  params: {
  'subIds' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.get('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/paytm/subscriptions/status', params={
  'subIds': 'string'
}, headers = headers)

print(r.json())

```

`GET /api/v1/payments/paytm/subscriptions/status`

<h3 id="getsubscriptionstatus-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|subIds|query|string|true|none|

> Example responses

> 200 Response

<h3 id="getsubscriptionstatus-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="getsubscriptionstatus-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[SubscriptionDetailsResponseDto](#schemasubscriptiondetailsresponsedto)]|false|none|none|
|» subscriptionComplete|boolean|false|none|none|
|» head|[SubscriptionDetailsResponseHeadDto](#schemasubscriptiondetailsresponseheaddto)|false|none|none|
|»» responseTimestamp|string|false|none|none|
|»» signature|string|false|none|none|
|»» tokenType|string|false|none|none|
|» body|[SubscriptionDetailsResponseBodyDto](#schemasubscriptiondetailsresponsebodydto)|false|none|none|
|»» resultInfo|[SubscriptionDetailsResponseResultInfoDto](#schemasubscriptiondetailsresponseresultinfodto)|false|none|none|
|»»» code|string|false|none|none|
|»»» message|string|false|none|none|
|»»» status|string|false|none|none|
|»» subsId|string|false|none|none|
|»» status|string|false|none|none|
|»» subStatus|string|false|none|none|
|»» activationDate|string|false|none|none|
|»» vpa|string|false|none|none|
|»» orderId|string|false|none|none|
|»» subsPaymentInstDetails|[SubscriptionDetailsResponseSubPaymentInstDetailsDto](#schemasubscriptiondetailsresponsesubpaymentinstdetailsdto)|false|none|none|
|»»» maskedAccountNumber|string|false|none|none|
|»»» ifsc|string|false|none|none|
|»»» maskedVpa|string|false|none|none|
|»»» bankName|string|false|none|none|
|»»» paymentMode|string|false|none|none|
|»»» instrumentStatus|string|false|none|none|
|»» subsLastRetryDone|[SubscriptionDetailsResponseLastRetryStatusDto](#schemasubscriptiondetailsresponselastretrystatusdto)|false|none|none|
|»»» status|string|false|none|none|
|»»» attemptedTime|string|false|none|none|
|»» subsNextRetry|[SubscriptionDetailsResponseNextRetryDto](#schemasubscriptiondetailsresponsenextretrydto)|false|none|none|
|»»» attemptedTime|string|false|none|none|
|»» subsRetryDetails|[SubscriptionDetailsResponseRetryDetailsDto](#schemasubscriptiondetailsresponseretrydetailsdto)|false|none|none|
|»»» totalRetryCount|string|false|none|none|
|»»» retriesLeft|string|false|none|none|
|»» lastOrderId|string|false|none|none|
|»» lastOrderStatus|string|false|none|none|
|»» lastOrderCreationDate|string|false|none|none|
|»» lastOrderAmount|string|false|none|none|
|»» amountType|string|false|none|none|
|»» maxAmount|string|false|none|none|
|»» mid|string|false|none|none|
|»» frequencyUnit|string|false|none|none|
|»» frequency|string|false|none|none|
|»» merchantName|string|false|none|none|
|»» expiryDate|string|false|none|none|
|»» createdDate|string|false|none|none|
|»» updatedDate|string|false|none|none|
|»» custId|string|false|none|none|
|»» custEmailId|string|false|none|none|
|»» custMobileNo|string|false|none|none|
|»» respCode|string|false|none|none|
|»» respMsg|string|false|none|none|
|»» upfrontTxnAmount|string|false|none|none|
|»» upfrontTxnId|string|false|none|none|
|»» linkDetails|[SubscriptionDetailsResponseLinkDetailsDto](#schemasubscriptiondetailsresponselinkdetailsdto)|false|none|none|
|»»» linkId|string|false|none|none|
|»»» linkNotes|string|false|none|none|
|»»» expiryDate|string|false|none|none|
|»»» shortUrl|string|false|none|none|
|»» pauseStartDate|string|false|none|none|
|»» pauseEndDate|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|INIT|
|status|ACTIVE|
|status|REJECT|
|status|IN_AUTHORIZATION|
|status|AUTHORIZED|
|status|AUTHORIZATION_FAILED|
|status|EXPIRED|
|status|CLOSED|
|status|SUSPENDED|
|subStatus|INIT|
|subStatus|PPBL_PENDING|
|subStatus|PPBL_REJECT|
|subStatus|NPCI_PENDING|
|subStatus|NPCI_REJECT|
|subStatus|ACTIVE|
|subStatus|MERCHANT_CANCELLED|
|subStatus|USER_CANCELLED|
|subStatus|TIMED_OUT|
|subStatus|ORDER_CLOSED|
|subStatus|CONFIRMED|
|subStatus|ISSUING_BANK_CANCELLED|
|subStatus|USER_SUSPENDED|
|subStatus|MERCHANT_SUSPENDED|
|subStatus|PPBL_SUSPENDED|
|subStatus|RESUMED|
|paymentMode|NORMAL|
|paymentMode|PPI|
|paymentMode|CC|
|paymentMode|DC|
|paymentMode|PPBL|
|paymentMode|BANK_MANDATE|
|paymentMode|UPI|
|paymentMode|UNKNOWN|
|instrumentStatus|EXPIRED|
|instrumentStatus|ACTIVE|
|instrumentStatus|INACTIVE|
|amountType|FIX|
|amountType|VARIABLE|
|frequencyUnit|DAY|
|frequencyUnit|WEEK|
|frequencyUnit|MONTH|
|frequencyUnit|BI_MONTHLY|
|frequencyUnit|QUARTER|
|frequencyUnit|SEMI_ANNUALLY|
|frequencyUnit|YEAR|
|frequencyUnit|ONDEMAND|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

<h1 id="sample-api-paytm-one-time-transaction-controller">paytm-one-time-transaction-controller</h1>

## handlePostbackSuccessCallForOneTimePayment

<a id="opIdhandlePostbackSuccessCallForOneTimePayment"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/paytm/oneTimePayments/postback/success',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/paytm/oneTimePayments/postback/success', headers = headers)

print(r.json())

```

`POST /api/v1/payments/paytm/oneTimePayments/postback/success`

> Body parameter

```json
{
  "BANKTXNID": "string",
  "CHECKSUMHASH": "string",
  "CURRENCY": "string",
  "GATEWAYNAME": "string",
  "MERC_UNQ_REF": "string",
  "MID": "string",
  "ORDERID": "string",
  "PAYMENTMODE": "string",
  "RESPCODE": "string",
  "RESPMSG": "string",
  "STATUS": "TXN_SUCCESS",
  "SUBS_ID": "string",
  "TXNAMOUNT": 0,
  "TXNDATE": "string",
  "TXNID": "string",
  "UDF_1": "string",
  "UDF_2": "string"
}
```

<h3 id="handlepostbacksuccesscallforonetimepayment-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[PaytmSubscriptionPostbackSuccessDto](#schemapaytmsubscriptionpostbacksuccessdto)|true|none|

> Example responses

> 200 Response

<h3 id="handlepostbacksuccesscallforonetimepayment-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[OneTimePaymentResponseDto](#schemaonetimepaymentresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## createPaymentMandateForUser_2

<a id="opIdcreatePaymentMandateForUser_2"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/paytm/oneTimePayments/create',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/paytm/oneTimePayments/create', headers = headers)

print(r.json())

```

`POST /api/v1/payments/paytm/oneTimePayments/create`

> Body parameter

```json
{
  "plan": "BASIC",
  "frequency": "MONTHLY",
  "discountCode": "string"
}
```

<h3 id="createpaymentmandateforuser_2-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[PaytmSubscriptionCreationRequestDto](#schemapaytmsubscriptioncreationrequestdto)|true|none|

> Example responses

> 200 Response

<h3 id="createpaymentmandateforuser_2-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[OneTimePaymentCreationResponseDto](#schemaonetimepaymentcreationresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

<h1 id="sample-api-payment-controller">payment-controller</h1>

## createPaymentMandateForUser_3

<a id="opIdcreatePaymentMandateForUser_3"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/mandate',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/mandate', headers = headers)

print(r.json())

```

`POST /api/v1/payments/mandate`

> Body parameter

```json
{
  "vpa": "string",
  "plan": "BASIC",
  "frequency": "MONTHLY",
  "discountCode": "string"
}
```

<h3 id="createpaymentmandateforuser_3-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[MandateCreationRequestDto](#schemamandatecreationrequestdto)|true|none|

> Example responses

> 200 Response

<h3 id="createpaymentmandateforuser_3-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[MandateCreationResponseDto](#schemamandatecreationresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## createPaymentMandateForUser_4

<a id="opIdcreatePaymentMandateForUser_4"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/mandate/postback/success',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/mandate/postback/success', headers = headers)

print(r.json())

```

`POST /api/v1/payments/mandate/postback/success`

> Body parameter

```json
{
  "txn_id": "string",
  "digio_doc_id": "string",
  "message": "string"
}
```

<h3 id="createpaymentmandateforuser_4-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[DigioMandateCreationSuccessPostbackRequestDto](#schemadigiomandatecreationsuccesspostbackrequestdto)|true|none|

> Example responses

> 200 Response

<h3 id="createpaymentmandateforuser_4-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DigioManadateCreationSuccessPostbackResponseDto](#schemadigiomanadatecreationsuccesspostbackresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## processDigioWebhook

<a id="opIdprocessDigioWebhook"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/digio/webhook',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/digio/webhook', headers = headers)

print(r.json())

```

`POST /api/v1/payments/digio/webhook`

> Body parameter

```json
"string"
```

<h3 id="processdigiowebhook-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|string|true|none|

> Example responses

> 200 Response

<h3 id="processdigiowebhook-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="processdigiowebhook-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

<h1 id="sample-api-external-payments-controller">external-payments-controller</h1>

## createPaymentMandateForUser_5

<a id="opIdcreatePaymentMandateForUser_5"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/external/create',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/payments/external/create', headers = headers)

print(r.json())

```

`POST /api/v1/payments/external/create`

> Body parameter

```json
{
  "userId": "string",
  "amountPaid": 0,
  "destinationPlanType": "TRIAL",
  "paymentTime": "2019-08-24T14:15:22Z",
  "paymentId": "string",
  "planId": "string",
  "transactionId": "string",
  "expiryDate": "2019-08-24",
  "channel": "PAYTM",
  "duration": "Adhoc"
}
```

<h3 id="createpaymentmandateforuser_5-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[ExternalPaymentCreationRequestDto](#schemaexternalpaymentcreationrequestdto)|true|none|

> Example responses

> 200 Response

<h3 id="createpaymentmandateforuser_5-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[ExternalPaymentResponseDto](#schemaexternalpaymentresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

<h1 id="sample-api-scout-quest-task-controller">scout-quest-task-controller</h1>

## submitAudioTranslationTasks

<a id="opIdsubmitAudioTranslationTasks"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/pa/tasks/submit/audioTranslation',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/pa/tasks/submit/audioTranslation', headers = headers)

print(r.json())

```

`POST /api/v1/pa/tasks/submit/audioTranslation`

> Body parameter

```json
{
  "id": "string",
  "base64File": "string",
  "fileName": "string",
  "prompt": "string",
  "model": "string",
  "fileUrl": "string"
}
```

<h3 id="submitaudiotranslationtasks-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[AudioTranslationRequestDto](#schemaaudiotranslationrequestdto)|true|none|

> Example responses

> 200 Response

<h3 id="submitaudiotranslationtasks-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="submitaudiotranslationtasks-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## getStatusForTask

<a id="opIdgetStatusForTask"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.get 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/pa/tasks/status/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.get('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/pa/tasks/status/{id}', headers = headers)

print(r.json())

```

`GET /api/v1/pa/tasks/status/{id}`

<h3 id="getstatusfortask-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer(int64)|true|none|

> Example responses

> 200 Response

<h3 id="getstatusfortask-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="getstatusfortask-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## getResultForTask

<a id="opIdgetResultForTask"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.get 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/pa/tasks/results/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.get('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/pa/tasks/results/{id}', headers = headers)

print(r.json())

```

`GET /api/v1/pa/tasks/results/{id}`

<h3 id="getresultfortask-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer(int64)|true|none|

> Example responses

> 200 Response

<h3 id="getresultfortask-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[JsonNode](#schemajsonnode)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

<h1 id="sample-api-otp-controller">otp-controller</h1>

## validateOTP

<a id="opIdvalidateOTP"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/otp/validate',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/otp/validate', headers = headers)

print(r.json())

```

`POST /api/v1/otp/validate`

> Body parameter

```json
{
  "otp": 0
}
```

<h3 id="validateotp-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|txnId|query|string|false|none|
|body|body|[OtpDTO](#schemaotpdto)|true|none|

> Example responses

> 200 Response

```json
{}
```

<h3 id="validateotp-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="validateotp-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## resendOtp_1

<a id="opIdresendOtp_1"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/otp/resend',
  params: {
  'type' => 'string',
'transactionId' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/otp/resend', params={
  'type': 'CALL',  'transactionId': 'string'
}, headers = headers)

print(r.json())

```

`POST /api/v1/otp/resend`

<h3 id="resendotp_1-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|type|query|string|true|none|
|transactionId|query|string|true|none|
|notificationType|query|string|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|type|CALL|
|type|SMS|
|type|WHATSAPP|
|notificationType|EMAIL_VERIFICATION|
|notificationType|EMAIL_VERIFICATION_OTP|
|notificationType|OTP|
|notificationType|MOBILE_VERIFICATION_OTP|
|notificationType|LOGIN_OTP|
|notificationType|SIGNUP_OTP|
|notificationType|WELCOME_USER|
|notificationType|WELCOME_USER_MOBILE_VERIFIED|
|notificationType|WELCOME_USER_MANUAL_STOCK_ADDED|
|notificationType|WELCOME_USER_ONBOARDING_COMPLETE|
|notificationType|PAYMENT_SUCCESS|
|notificationType|PAYMENT_FAILURE|
|notificationType|BROKER_REFERRAL_STOCKS_UPLOADED|
|notificationType|USER_TRACKED_INSTRUMENT_UPDATE|
|notificationType|EXPLAINER_VIDEO|

> Example responses

> 200 Response

```json
{}
```

<h3 id="resendotp_1-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="resendotp_1-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## generateOTP

<a id="opIdgenerateOTP"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/otp/generate',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/otp/generate', headers = headers)

print(r.json())

```

`POST /api/v1/otp/generate`

<h3 id="generateotp-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|txnId|query|string|false|none|

> Example responses

> 200 Response

```json
{}
```

<h3 id="generateotp-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="generateotp-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

<h1 id="sample-api-instrument-controller">instrument-controller</h1>

## getInstrumentsCurrentlyTrackedByUser

<a id="opIdgetInstrumentsCurrentlyTrackedByUser"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.get 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/instruments/users/tracking',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.get('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/instruments/users/tracking', headers = headers)

print(r.json())

```

`GET /api/v1/instruments/users/tracking`

> Example responses

> 200 Response

<h3 id="getinstrumentscurrentlytrackedbyuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="getinstrumentscurrentlytrackedbyuser-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[TrackedInstrumentsResponseDto](#schematrackedinstrumentsresponsedto)]|false|none|none|
|» subscriptionId|integer(int64)|true|none|none|
|» isin|string|true|none|none|
|» tickr|string|true|none|none|
|» name|string|true|none|none|
|» source|string|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|source|MANUAL|
|source|GATEWAY|
|source|CAS|
|source|HOLDINGPARSER|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## updateUserInstrumentTracking_2

<a id="opIdupdateUserInstrumentTracking_2"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/instruments/users/tracking',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/instruments/users/tracking', headers = headers)

print(r.json())

```

`POST /api/v1/instruments/users/tracking`

> Body parameter

```json
{
  "instruments": [
    {
      "isin": "string",
      "tickr": "string"
    }
  ]
}
```

<h3 id="updateuserinstrumenttracking_2-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[UpdateUserStockSubscriptionRequestDto](#schemaupdateuserstocksubscriptionrequestdto)|true|none|

> Example responses

> 200 Response

<h3 id="updateuserinstrumenttracking_2-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[TrackInstrumentsUpdateResponseDto](#schematrackinstrumentsupdateresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## loadCompanyNames

<a id="opIdloadCompanyNames"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/instruments/load/companyNames',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/instruments/load/companyNames', headers = headers)

print(r.json())

```

`POST /api/v1/instruments/load/companyNames`

> Example responses

> 200 Response

<h3 id="loadcompanynames-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[CompanyNameLookupBuildStatistic](#schemacompanynamelookupbuildstatistic)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## importFromListedEquity

<a id="opIdimportFromListedEquity"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/instruments/import',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/instruments/import', headers = headers)

print(r.json())

```

`POST /api/v1/instruments/import`

> Body parameter

```json
{
  "file": "string"
}
```

<h3 id="importfromlistedequity-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|none|
|» file|body|string(binary)|true|none|

> Example responses

> 200 Response

<h3 id="importfromlistedequity-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[FileImportReportDto](#schemafileimportreportdto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## getCompanyNames

<a id="opIdgetCompanyNames"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.get 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/instruments/lookup',
  params: {
  'name' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.get('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/instruments/lookup', params={
  'name': 'string'
}, headers = headers)

print(r.json())

```

`GET /api/v1/instruments/lookup`

<h3 id="getcompanynames-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|name|query|string|true|none|

> Example responses

> 200 Response

<h3 id="getcompanynames-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="getcompanynames-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[CompanyNameLookupResponseDto](#schemacompanynamelookupresponsedto)]|false|none|none|
|» isin|string|false|none|none|
|» tickr|string|false|none|none|
|» bseScripCode|integer(int32)|false|none|none|
|» longName|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

<h1 id="sample-api-file-upload-instrument-user-controller">file-upload-instrument-user-controller</h1>

## updateUserInstrumentTracking_3

<a id="opIdupdateUserInstrumentTracking_3"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/instruments/file/users/tracking',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/instruments/file/users/tracking', headers = headers)

print(r.json())

```

`POST /api/v1/instruments/file/users/tracking`

> Body parameter

```json
{
  "file": "string",
  "mode": "string"
}
```

<h3 id="updateuserinstrumenttracking_3-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|none|
|» file|body|string(binary)|true|none|
|» mode|body|string|true|none|

> Example responses

> 200 Response

<h3 id="updateuserinstrumenttracking_3-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[UserInstrumentFileUploadResponseDto](#schemauserinstrumentfileuploadresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## create

<a id="opIdcreate"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.get 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/instruments/file/user/permissions',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.get('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/instruments/file/user/permissions', headers = headers)

print(r.json())

```

`GET /api/v1/instruments/file/user/permissions`

> Example responses

> 200 Response

<h3 id="create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[UserFileUploadPermissionsResponseDto](#schemauserfileuploadpermissionsresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

<h1 id="sample-api-holding-parser-controller">holding-parser-controller</h1>

## upload

<a id="opIdupload"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/holdingParser/upload',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/holdingParser/upload', headers = headers)

print(r.json())

```

`POST /api/v1/holdingParser/upload`

> Body parameter

```json
{
  "file": "string",
  "password": "string"
}
```

<h3 id="upload-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|none|
|» file|body|string(binary)|true|none|
|» password|body|string|false|none|

> Example responses

> 200 Response

<h3 id="upload-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[ConsolidatedImportedHoldingsFromHoldingAIParseImportResponseDto](#schemaconsolidatedimportedholdingsfromholdingaiparseimportresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

<h1 id="sample-api-mail-database-controller">mail-database-controller</h1>

## importFromListedEquity_1

<a id="opIdimportFromListedEquity_1"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/corporate/import',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/corporate/import', headers = headers)

print(r.json())

```

`POST /api/v1/corporate/import`

> Body parameter

```json
{
  "file": "string"
}
```

<h3 id="importfromlistedequity_1-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|none|
|» file|body|string(binary)|true|none|

> Example responses

> 200 Response

<h3 id="importfromlistedequity_1-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[ImportReport](#schemaimportreport)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

<h1 id="sample-api-cas-parser-controller">cas-parser-controller</h1>

## upload_1

<a id="opIdupload_1"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/casparser/upload',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/casparser/upload', headers = headers)

print(r.json())

```

`POST /api/v1/casparser/upload`

> Body parameter

```json
{
  "file": "string",
  "password": "string",
  "type": "string"
}
```

<h3 id="upload_1-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|none|
|» file|body|string(binary)|true|none|
|» password|body|string|false|none|
|» type|body|string|true|none|

> Example responses

> 200 Response

<h3 id="upload_1-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[CasUploadResponseDto](#schemacasuploadresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

<h1 id="sample-api-whatsapp-bot-controller">whatsapp-bot-controller</h1>

## changeUserPreferences

<a id="opIdchangeUserPreferences"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/bot/users/preferences',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/bot/users/preferences', headers = headers)

print(r.json())

```

`POST /api/v1/bot/users/preferences`

> Body parameter

```json
{
  "stopUserNotification": true,
  "sessionId": "string",
  "mobileNo": 0,
  "countryCode": 0
}
```

<h3 id="changeuserpreferences-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[UpdateUserPreferenceRequestDto](#schemaupdateuserpreferencerequestdto)|true|none|

> Example responses

> 200 Response

<h3 id="changeuserpreferences-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[UserLookupResponseDto](#schemauserlookupresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## lookupUser

<a id="opIdlookupUser"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/bot/users/lookup',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/bot/users/lookup', headers = headers)

print(r.json())

```

`POST /api/v1/bot/users/lookup`

> Body parameter

```json
{
  "countryCode": 0,
  "mobileNo": 0,
  "source": "string",
  "name": "string"
}
```

<h3 id="lookupuser-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[UserLookupRequestDto](#schemauserlookuprequestdto)|true|none|

> Example responses

> 200 Response

<h3 id="lookupuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[UserLookupResponseDto](#schemauserlookupresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## signupUserViaBroker

<a id="opIdsignupUserViaBroker"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/bot/users/brokerSignup',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/bot/users/brokerSignup', headers = headers)

print(r.json())

```

`POST /api/v1/bot/users/brokerSignup`

> Body parameter

```json
{
  "countryCode": 0,
  "mobileNo": 0,
  "source": "string",
  "name": "string",
  "brokerName": "string",
  "holdingFetchConsent": true
}
```

<h3 id="signupuserviabroker-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[BrokeUserSignupRequestDto](#schemabrokeusersignuprequestdto)|true|none|

> Example responses

> 200 Response

<h3 id="signupuserviabroker-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[UserLookupResponseDto](#schemauserlookupresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

<h1 id="sample-api-whatsapp-bot-survey-controller">whatsapp-bot-survey-controller</h1>

## registerShareChannelResponse

<a id="opIdregisterShareChannelResponse"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/bot/surveys/userPaidPlanShiftSurvey/responses',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/bot/surveys/userPaidPlanShiftSurvey/responses', headers = headers)

print(r.json())

```

`POST /api/v1/bot/surveys/userPaidPlanShiftSurvey/responses`

> Body parameter

```json
{
  "sessionId": "string",
  "userId": 0,
  "mobileNo": 0,
  "countryCode": 0,
  "responseTime": 0,
  "vendorResponseTime": "string",
  "response": "UPGRADE_NOW"
}
```

<h3 id="registersharechannelresponse-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[UserPaidShiftSurveyResponseDto](#schemauserpaidshiftsurveyresponsedto)|true|none|

<h3 id="registersharechannelresponse-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## registerShareChannelResponse_1

<a id="opIdregisterShareChannelResponse_1"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/bot/surveys/trialUserFeedback/shareChannelResponse',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/bot/surveys/trialUserFeedback/shareChannelResponse', headers = headers)

print(r.json())

```

`POST /api/v1/bot/surveys/trialUserFeedback/shareChannelResponse`

> Body parameter

```json
{
  "sessionId": "string",
  "userId": 0,
  "mobileNo": 0,
  "countryCode": 0,
  "responseTime": 0,
  "vendorResponseTime": "string",
  "channel": "TWITTER"
}
```

<h3 id="registersharechannelresponse_1-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[TrialUserFeedBackSurveyChannelRequestDto](#schematrialuserfeedbacksurveychannelrequestdto)|true|none|

<h3 id="registersharechannelresponse_1-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## registerInitialResponse

<a id="opIdregisterInitialResponse"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/bot/surveys/trialUserFeedback/initialResponse',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/bot/surveys/trialUserFeedback/initialResponse', headers = headers)

print(r.json())

```

`POST /api/v1/bot/surveys/trialUserFeedback/initialResponse`

> Body parameter

```json
{
  "sessionId": "string",
  "userId": 0,
  "mobileNo": 0,
  "countryCode": 0,
  "responseTime": 0,
  "vendorResponseTime": "string",
  "isSqHelpful": true
}
```

<h3 id="registerinitialresponse-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[TrialUserFeedBackSurveyInitialResponseRequestDto](#schematrialuserfeedbacksurveyinitialresponserequestdto)|true|none|

<h3 id="registerinitialresponse-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

<h1 id="sample-api-admin-user-instrument-controller">admin-user-instrument-controller</h1>

## updateUserPrivilegeStatus

<a id="opIdupdateUserPrivilegeStatus"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/users/privilege',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/users/privilege', headers = headers)

print(r.json())

```

`POST /api/v1/admin/users/privilege`

> Body parameter

```json
{
  "userId": "string",
  "userPrivileged": true
}
```

<h3 id="updateuserprivilegestatus-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[UserPrivilegeUpdateRequestDto](#schemauserprivilegeupdaterequestdto)|true|none|

> Example responses

> 200 Response

<h3 id="updateuserprivilegestatus-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[UserResponseDto](#schemauserresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## addInstrumentsForUser

<a id="opIdaddInstrumentsForUser"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/users/instruments/tracking/update',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/users/instruments/tracking/update', headers = headers)

print(r.json())

```

`POST /api/v1/admin/users/instruments/tracking/update`

> Body parameter

```json
{
  "instruments": [
    {
      "isin": "string",
      "tickr": "string"
    }
  ],
  "userId": "string",
  "mode": "APPEND"
}
```

<h3 id="addinstrumentsforuser-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[AdminUpdateUserStockSubscriptionRequestDto](#schemaadminupdateuserstocksubscriptionrequestdto)|true|none|

> Example responses

> 200 Response

<h3 id="addinstrumentsforuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[TrackInstrumentsUpdateResponseDto](#schematrackinstrumentsupdateresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## getAllInstrumentsForUser

<a id="opIdgetAllInstrumentsForUser"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.get 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/users/{userId}/instruments/tracking',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.get('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/users/{userId}/instruments/tracking', headers = headers)

print(r.json())

```

`GET /api/v1/admin/users/{userId}/instruments/tracking`

<h3 id="getallinstrumentsforuser-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|userId|path|string|true|none|

> Example responses

> 200 Response

<h3 id="getallinstrumentsforuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[CumulativeTrackedInstrumentResponseDto](#schemacumulativetrackedinstrumentresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## getAllUsersWhoTracksAnInstrument

<a id="opIdgetAllUsersWhoTracksAnInstrument"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.get 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/users/instrument/tracking',
  params: {
  'channel' => 'string',
'instrumentId' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.get('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/users/instrument/tracking', params={
  'channel': 'CORPORATE_ANNOUNCEMENT',  'instrumentId': 'string'
}, headers = headers)

print(r.json())

```

`GET /api/v1/admin/users/instrument/tracking`

<h3 id="getalluserswhotracksaninstrument-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|channel|query|string|true|none|
|instrumentId|query|string|true|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|channel|CORPORATE_ANNOUNCEMENT|
|channel|TECHNICAL_ANALYSIS|
|channel|GENERAL_NEWS|
|channel|TELEGRAM|
|channel|TWEET|
|channel|BULLETIN|
|channel|RSS|
|channel|CONCALL_HIGHLIGHTS|
|channel|CONCALL_SUMMARY|
|channel|FUTURE_OUTLOOK|
|channel|BULK_BLOCK|
|channel|SQ_SPVMA_INTRADAY_VOLUME_SPURT|
|channel|ANALYST_VIEWS|

> Example responses

> 200 Response

<h3 id="getalluserswhotracksaninstrument-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="getalluserswhotracksaninstrument-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

<h1 id="sample-api-admin-user-action-controller">admin-user-action-controller</h1>

## updateUserPrivilegeStatus_1

<a id="opIdupdateUserPrivilegeStatus_1"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/users/notes',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/users/notes', headers = headers)

print(r.json())

```

`POST /api/v1/admin/users/notes`

> Body parameter

```json
{
  "userId": "string",
  "userType": "string",
  "companyName": "string",
  "userDesignation": "string",
  "payPotential": "string",
  "source": "string",
  "additionalNotes": "string"
}
```

<h3 id="updateuserprivilegestatus_1-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[UserNotesUpdateRequestDto](#schemausernotesupdaterequestdto)|true|none|

> Example responses

> 200 Response

<h3 id="updateuserprivilegestatus_1-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[UserNotesResponseDto](#schemausernotesresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## getUserNotes

<a id="opIdgetUserNotes"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.get 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/users/notes/{userId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.get('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/users/notes/{userId}', headers = headers)

print(r.json())

```

`GET /api/v1/admin/users/notes/{userId}`

<h3 id="getusernotes-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|userId|path|string|true|none|

> Example responses

> 200 Response

<h3 id="getusernotes-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[UserNotesResponseDto](#schemausernotesresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

<h1 id="sample-api-admin-user-controller">admin-user-controller</h1>

## addInstrumentsForUser_1

<a id="opIdaddInstrumentsForUser_1"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/users/create',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/users/create', headers = headers)

print(r.json())

```

`POST /api/v1/admin/users/create`

> Body parameter

```json
{
  "mobileNo": 0,
  "countryCode": 0,
  "name": "string",
  "source": "string",
  "referralCode": "string",
  "userPlanType": "TRIAL",
  "noOfDaysTillPlanExpiry": 0,
  "stockTrackingLimit": 0,
  "planSchemeRefId": "string"
}
```

<h3 id="addinstrumentsforuser_1-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[AdminUserCreationRequestDto](#schemaadminusercreationrequestdto)|true|none|

> Example responses

> 200 Response

<h3 id="addinstrumentsforuser_1-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[UserResponseDto](#schemauserresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## getUserProfileDetails_1

<a id="opIdgetUserProfileDetails_1"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.get 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/users',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.get('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/users', headers = headers)

print(r.json())

```

`GET /api/v1/admin/users`

<h3 id="getuserprofiledetails_1-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|pageNo|query|integer(int32)|false|none|
|pageSize|query|integer(int32)|false|none|
|sortBy|query|string|false|none|
|sortDirection|query|string|false|none|
|type|query|string|false|none|
|search|query|string|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|type|ALL|
|type|TRIAL|
|type|FREE|
|type|PAID|

> Example responses

> 200 Response

<h3 id="getuserprofiledetails_1-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[PageUserAdminLookupResponseDto](#schemapageuseradminlookupresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## getProfilingQuestionsResponseForUser

<a id="opIdgetProfilingQuestionsResponseForUser"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.get 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/users/{userId}/profilingQuestions/',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.get('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/users/{userId}/profilingQuestions/', headers = headers)

print(r.json())

```

`GET /api/v1/admin/users/{userId}/profilingQuestions/`

<h3 id="getprofilingquestionsresponseforuser-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|userId|path|string|true|none|

> Example responses

> 200 Response

<h3 id="getprofilingquestionsresponseforuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[UserProfilingQuestionResponseDto](#schemauserprofilingquestionresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

<h1 id="sample-api-admin-broker-signup-controller">admin-broker-signup-controller</h1>

## addInstrumentsForUser_2

<a id="opIdaddInstrumentsForUser_2"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/users/brokers/instruments/tracking/upload',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/users/brokers/instruments/tracking/upload', headers = headers)

print(r.json())

```

`POST /api/v1/admin/users/brokers/instruments/tracking/upload`

> Body parameter

```json
{
  "file": "string",
  "brokerName": "string"
}
```

<h3 id="addinstrumentsforuser_2-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|none|
|» file|body|string(binary)|true|none|
|» brokerName|body|string|false|none|

> Example responses

> 200 Response

<h3 id="addinstrumentsforuser_2-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="addinstrumentsforuser_2-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[BrokerUserHoldingResponseDto](#schemabrokeruserholdingresponsedto)]|false|none|none|
|» accountInfo|[BrokerUserAccountInfoResponseDto](#schemabrokeruseraccountinforesponsedto)|false|none|none|
|»» id|integer(int64)|false|none|none|
|»» clientName|string|false|none|none|
|»» countryCode|string|false|none|none|
|»» uploadRequestId|integer(int64)|false|none|none|
|»» brokerName|string|false|none|none|
|»» creationTime|integer(int64)|false|none|none|
|»» brokerId|string|false|none|none|
|»» brokerSignupRequestId|string|false|none|none|
|»» userId|integer(int64)|false|none|none|
|»» validityStatus|string|false|none|none|
|»» noOfStocks|integer(int64)|false|none|none|
|»» value|number|false|none|none|
|»» importedByAdminUserId|integer(int64)|false|none|none|
|» individualHoldings|[[BrokerUserIndividualHoldingsResponseDto](#schemabrokeruserindividualholdingsresponsedto)]|false|none|none|
|»» id|integer(int64)|false|none|none|
|»» brokerUserAccountInfoId|integer(int64)|false|none|none|
|»» qty|integer(int32)|false|none|none|
|»» isin|string|false|none|none|
|»» creationTime|integer(int64)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|brokerId|PMSECURITIES|
|brokerId|ABANS_SECURITIES|
|brokerId|AJAY_JAIN|
|brokerId|ALACRITY_SECURITIES|
|brokerId|ALDAN_INVESTMENTS|
|brokerId|ALLWIN_SECURITIES|
|brokerId|AMIT_SAHITA_SEC|
|brokerId|ANANT_INVESTMENTS|
|brokerId|ASHISH_VAID|
|brokerId|ASIAN_BROKING|
|brokerId|AXIOM_BROKING|
|brokerId|BD_SHAH_SECURITIES|
|brokerId|BD_SHROFF_SECURITIES|
|brokerId|BAJAJ_SHARES|
|brokerId|BIGCAPITA_SECURITIES|
|brokerId|CHIMANLAL_MANEKLAL_SECURITIES|
|brokerId|CHURIWALA_SECURITIES|
|brokerId|CROSSEAS_CAPITAL_SERVICES|
|brokerId|DALAL_BROACHA_STOCK_BROKING|
|brokerId|DARASHAW_COMPANY|
|brokerId|DEEP_FINANCIAL_CONSULTANTS|
|brokerId|DHANKI_SECURITIES|
|brokerId|DHARAMSHI_SECURITIES|
|brokerId|DHWAJA_SHARES|
|brokerId|DHYAN_STOCKS|
|brokerId|ELIXIR_EQUITIES|
|brokerId|FIRST_INDIA_SECURITIES|
|brokerId|GNG_INVESTMENTS|
|brokerId|GHANSHYAM_SHARES_STOCK_BROKERS|
|brokerId|HARENDRA_D_MEHTA_SHARE_AND_STOCK_BROKER|
|brokerId|HARJIVANDAS_NEMIDAS_SECURITIES|
|brokerId|HORNIC_INVESTMENT|
|brokerId|INA_STOCK_BROKING|
|brokerId|JAS_ONE_SECURITIES|
|brokerId|JMP_SECURITIES|
|brokerId|RRS_SHARES_STOCK_BROKERS|
|brokerId|KAI_SECURITIES|
|brokerId|KALASH_SHARES|
|brokerId|KANTILAL_CHHAGANLAL_SEC|
|brokerId|KAUSHIK_SHAH_SHARES_SECURITIES|
|brokerId|KAVIRAJ_SECURITIES|
|brokerId|KIMAYA_SECURITIES|
|brokerId|LOTUS_GLOBAL_EQUITIES|
|brokerId|LPC_SECURITIES|
|brokerId|MD_SHUKLA_SHARE_AND_SECURITIES|
|brokerId|MJ_PATEL_SHARE|
|brokerId|VC_MEHTA|
|brokerId|MACY_SECURITIES|
|brokerId|MACY_SHARES_AND_STOCK_BROKERS|
|brokerId|MANUBHAI_MANGALDAS_SEC|
|brokerId|MANYOG_SECURITIES|
|brokerId|MARKETWOLF_SECURITIES|
|brokerId|MAXIMUS_SECURITIES|
|brokerId|MDN_SHARES_AND_STOCK_BROKERS|
|brokerId|MEHTA_VAKIL|
|brokerId|MESH_STOCK_BROKERS|
|brokerId|MUKUL_AMRUTLAL_SONAWALA|
|brokerId|NANGALIA_STOCK_BROKING|
|brokerId|PSURYAKANT_SHARE_STOCK_BROKERS|
|brokerId|PAVAK_SECURITIES|
|brokerId|PRAKASH_K_SHAH_SHARES_SECURITIES|
|brokerId|PRAKASH_SECURITIES|
|brokerId|PRARAMBH_SECURITIES|
|brokerId|PRL_STOCK_AND_SHARE_BROKERS|
|brokerId|RN_PATWA_SHARES_STOCK_BROKERS|
|brokerId|RAMESH_DAMANI|
|brokerId|RASHI_EQUISEARCH|
|brokerId|SHARAD_AGARWAL_BROKING_SERVICES|
|brokerId|SHREE_NAMAN_SECURITIES|
|brokerId|SHREEHARI_SHARES_AND_STOCK_BROKERS|
|brokerId|SURESH_KHANDELWAL|
|brokerId|TRUSTED_SHARES_INVESTMENTS|
|brokerId|UNIQUE_STOCKBRO|
|brokerId|UPMOVE_FINANCIAL_TECHNOLOGIES|
|brokerId|WELATHMILLS_SECURITIES|
|brokerId|YOGEN_BABU_SECURITIES|
|brokerId|CHOICE_BROKING|
|validityStatus|VALID|
|validityStatus|INVALID|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## getProfilingQuestionsResponseForUser_1

<a id="opIdgetProfilingQuestionsResponseForUser_1"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.get 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/users/brokers/signups',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.get('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/users/brokers/signups', headers = headers)

print(r.json())

```

`GET /api/v1/admin/users/brokers/signups`

<h3 id="getprofilingquestionsresponseforuser_1-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|brokerName|query|string|false|none|
|uploadStatus|query|string|false|none|
|pageNo|query|integer(int32)|false|none|
|pageSize|query|integer(int32)|false|none|
|sortBy|query|string|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|brokerName|PMSECURITIES|
|brokerName|ABANS_SECURITIES|
|brokerName|AJAY_JAIN|
|brokerName|ALACRITY_SECURITIES|
|brokerName|ALDAN_INVESTMENTS|
|brokerName|ALLWIN_SECURITIES|
|brokerName|AMIT_SAHITA_SEC|
|brokerName|ANANT_INVESTMENTS|
|brokerName|ASHISH_VAID|
|brokerName|ASIAN_BROKING|
|brokerName|AXIOM_BROKING|
|brokerName|BD_SHAH_SECURITIES|
|brokerName|BD_SHROFF_SECURITIES|
|brokerName|BAJAJ_SHARES|
|brokerName|BIGCAPITA_SECURITIES|
|brokerName|CHIMANLAL_MANEKLAL_SECURITIES|
|brokerName|CHURIWALA_SECURITIES|
|brokerName|CROSSEAS_CAPITAL_SERVICES|
|brokerName|DALAL_BROACHA_STOCK_BROKING|
|brokerName|DARASHAW_COMPANY|
|brokerName|DEEP_FINANCIAL_CONSULTANTS|
|brokerName|DHANKI_SECURITIES|
|brokerName|DHARAMSHI_SECURITIES|
|brokerName|DHWAJA_SHARES|
|brokerName|DHYAN_STOCKS|
|brokerName|ELIXIR_EQUITIES|
|brokerName|FIRST_INDIA_SECURITIES|
|brokerName|GNG_INVESTMENTS|
|brokerName|GHANSHYAM_SHARES_STOCK_BROKERS|
|brokerName|HARENDRA_D_MEHTA_SHARE_AND_STOCK_BROKER|
|brokerName|HARJIVANDAS_NEMIDAS_SECURITIES|
|brokerName|HORNIC_INVESTMENT|
|brokerName|INA_STOCK_BROKING|
|brokerName|JAS_ONE_SECURITIES|
|brokerName|JMP_SECURITIES|
|brokerName|RRS_SHARES_STOCK_BROKERS|
|brokerName|KAI_SECURITIES|
|brokerName|KALASH_SHARES|
|brokerName|KANTILAL_CHHAGANLAL_SEC|
|brokerName|KAUSHIK_SHAH_SHARES_SECURITIES|
|brokerName|KAVIRAJ_SECURITIES|
|brokerName|KIMAYA_SECURITIES|
|brokerName|LOTUS_GLOBAL_EQUITIES|
|brokerName|LPC_SECURITIES|
|brokerName|MD_SHUKLA_SHARE_AND_SECURITIES|
|brokerName|MJ_PATEL_SHARE|
|brokerName|VC_MEHTA|
|brokerName|MACY_SECURITIES|
|brokerName|MACY_SHARES_AND_STOCK_BROKERS|
|brokerName|MANUBHAI_MANGALDAS_SEC|
|brokerName|MANYOG_SECURITIES|
|brokerName|MARKETWOLF_SECURITIES|
|brokerName|MAXIMUS_SECURITIES|
|brokerName|MDN_SHARES_AND_STOCK_BROKERS|
|brokerName|MEHTA_VAKIL|
|brokerName|MESH_STOCK_BROKERS|
|brokerName|MUKUL_AMRUTLAL_SONAWALA|
|brokerName|NANGALIA_STOCK_BROKING|
|brokerName|PSURYAKANT_SHARE_STOCK_BROKERS|
|brokerName|PAVAK_SECURITIES|
|brokerName|PRAKASH_K_SHAH_SHARES_SECURITIES|
|brokerName|PRAKASH_SECURITIES|
|brokerName|PRARAMBH_SECURITIES|
|brokerName|PRL_STOCK_AND_SHARE_BROKERS|
|brokerName|RN_PATWA_SHARES_STOCK_BROKERS|
|brokerName|RAMESH_DAMANI|
|brokerName|RASHI_EQUISEARCH|
|brokerName|SHARAD_AGARWAL_BROKING_SERVICES|
|brokerName|SHREE_NAMAN_SECURITIES|
|brokerName|SHREEHARI_SHARES_AND_STOCK_BROKERS|
|brokerName|SURESH_KHANDELWAL|
|brokerName|TRUSTED_SHARES_INVESTMENTS|
|brokerName|UNIQUE_STOCKBRO|
|brokerName|UPMOVE_FINANCIAL_TECHNOLOGIES|
|brokerName|WELATHMILLS_SECURITIES|
|brokerName|YOGEN_BABU_SECURITIES|
|brokerName|CHOICE_BROKING|
|uploadStatus|NA|
|uploadStatus|PENDING|
|uploadStatus|UPLOADED|

> Example responses

> 200 Response

<h3 id="getprofilingquestionsresponseforuser_1-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[PageBrokerSignupRequestDto](#schemapagebrokersignuprequestdto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

<h1 id="sample-api-user-paid-survey-admin-controller">user-paid-survey-admin-controller</h1>

## createUserPaidPlanShiftSurvey

<a id="opIdcreateUserPaidPlanShiftSurvey"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/survey/userPaidShift/trigger',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/survey/userPaidShift/trigger', headers = headers)

print(r.json())

```

`POST /api/v1/admin/survey/userPaidShift/trigger`

> Body parameter

```json
[
  {
    "userId": "string"
  }
]
```

<h3 id="createuserpaidplanshiftsurvey-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[UserPaidPlanShiftSurveyTriggerRequestDto](#schemauserpaidplanshiftsurveytriggerrequestdto)|true|none|

<h3 id="createuserpaidplanshiftsurvey-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## getAllSurveysWhichRequireActions

<a id="opIdgetAllSurveysWhichRequireActions"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.get 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/survey/userPaidShift/active',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.get('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/survey/userPaidShift/active', headers = headers)

print(r.json())

```

`GET /api/v1/admin/survey/userPaidShift/active`

<h3 id="getallsurveyswhichrequireactions-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|date|query|string(date)|false|none|

> Example responses

> 200 Response

<h3 id="getallsurveyswhichrequireactions-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="getallsurveyswhichrequireactions-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[UserPaidPlanShiftSurvey](#schemauserpaidplanshiftsurvey)]|false|none|none|
|» uniqueSurveyRequestId|integer(int64)|false|none|none|
|» surveyId|string|false|none|none|
|» userId|integer(int64)|false|none|none|
|» userType|string|false|none|none|
|» surveyName|string|false|none|none|
|» countryCode|string|false|none|none|
|» mobileNumber|integer(int64)|false|none|none|
|» expiryDate|string(date)|false|none|none|
|» surveyStatus|string|false|none|none|
|» noOfTimesTrialExpiryPendingRemindersToBeSent|integer(int32)|false|none|none|
|» noOfTimesTrialExpiryPendingRemindersAlreadySent|integer(int32)|false|none|none|
|» lastTrialExpiryPendingReminderSentTime|integer(int64)|false|none|none|
|» scheduledNextMessageTime|integer(int64)|false|none|none|
|» scheduledNextMessageType|string|false|none|none|
|» sentMessageLog|[[SentMessage](#schemasentmessage)]|false|none|none|
|»» messageSentReceipt|string|false|none|none|
|»» id|string|false|none|none|
|»» creationTime|integer(int64)|false|none|none|
|»» messageType|string|false|none|none|
|» noOfTimesTrialExpiryNotificationToBeSent|integer(int32)|false|none|none|
|» noOfTimesTrialExpiryNotificationAlreadySent|integer(int32)|false|none|none|
|» lastTrialExpiryNotificationSentTime|integer(int64)|false|none|none|
|» trialExpiryFirstResponse|string|false|none|none|
|» trialExpiryFirstResponseTime|integer(int64)|false|none|none|
|» trialExpirySecondResponse|string|false|none|none|
|» trialExpirySecondResponseTime|integer(int64)|false|none|none|
|» noOfTimesFreeTrialIntroToBeSent|integer(int32)|false|none|none|
|» noOfTimesFreeTrialIntroAlreadySent|integer(int32)|false|none|none|
|» freeTrialIntroLastSentTime|integer(int64)|false|none|none|
|» freeTrialSurveyResponse|string|false|none|none|
|» freeTrialAckResponseTime|integer(int64)|false|none|none|
|» freeTierTransitionCompleteTime|integer(int64)|false|none|none|
|» noOfTimesFreeTrialExtensionDoneBeSent|integer(int32)|false|none|none|
|» noOfTimesFreeTrialExtensionAlreadySent|integer(int32)|false|none|none|
|» freeTrialExtensionLastSentTime|integer(int64)|false|none|none|
|» creationTime|integer(int64)|false|none|none|
|» userPaidMarkTime|integer(int64)|false|none|none|
|» createdByUserId|integer(int64)|false|none|none|
|» isFinalReminder|boolean|false|none|none|
|» scheduledMessageToBeSent|string|false|none|none|
|» surveyTerminated|boolean|false|none|none|
|» trialExpiredNotificationFirstResponseAlreadyRegistered|boolean|false|none|none|
|» trialExpiredNotificationSecondResponseAlreadyRegistered|boolean|false|none|none|
|» freeTrialExtensionResponseFirstResponseAlreadyRegistered|boolean|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|userType|RETAIL_USER|
|userType|PMS|
|surveyName|TRIAL_USER_FEEDBACK|
|surveyName|CONVERT_TRIAL_TO_PAID_SURVEY_CASUAL|
|surveyName|CONVERT_TRIAL_TO_PAID_SURVEY_CORPORATE|
|surveyName|FLASH_SALE|
|surveyName|FESTIVE_DISCOUNT|
|surveyStatus|CREATED|
|surveyStatus|PENDING_TRIAL_EXPIRY_NOTIFIED|
|surveyStatus|USER_PAID|
|surveyStatus|TRIAL_EXPIRED_NOTIFIED|
|surveyStatus|TRIAL_EXPIRED_ACK|
|surveyStatus|FREE_TRIAL_NOTIFIED|
|surveyStatus|FREE_TRIAL_EXTENSION_ACK|
|surveyStatus|FREE_TIER_TRANSITIONED|
|surveyStatus|USER_UNSUBSCRIBED|
|scheduledNextMessageType|TRIAL_EXPIRY_REMINDER|
|scheduledNextMessageType|TRIAL_EXPIRED|
|scheduledNextMessageType|FREE_TRIAL_EXTENSION|
|scheduledNextMessageType|FREE_TIER_TRANSITION_COMPLETE|
|messageType|TRIAL_EXPIRY_REMINDER|
|messageType|TRIAL_EXPIRED|
|messageType|FREE_TRIAL_EXTENSION|
|messageType|FREE_TIER_TRANSITION_COMPLETE|
|trialExpiryFirstResponse|UPGRADE_NOW|
|trialExpiryFirstResponse|DONT_WANT_TO_UPGRADE|
|trialExpiryFirstResponse|PAYMENT_ISSUE|
|trialExpiryFirstResponse|PRICING_FEEDBACK|
|trialExpiryFirstResponse|NOT_USEFUL_FEEDBACK|
|trialExpiryFirstResponse|OTHER_FEEDBACK|
|trialExpirySecondResponse|UPGRADE_NOW|
|trialExpirySecondResponse|DONT_WANT_TO_UPGRADE|
|trialExpirySecondResponse|PAYMENT_ISSUE|
|trialExpirySecondResponse|PRICING_FEEDBACK|
|trialExpirySecondResponse|NOT_USEFUL_FEEDBACK|
|trialExpirySecondResponse|OTHER_FEEDBACK|
|freeTrialSurveyResponse|AGREE_TO_FREE_TRIAL|
|freeTrialSurveyResponse|UPGRADE_TO_PAID|
|freeTrialSurveyResponse|STOP_NOTIFICATION|
|scheduledMessageToBeSent|TRIAL_EXPIRY_REMINDER|
|scheduledMessageToBeSent|TRIAL_EXPIRED|
|scheduledMessageToBeSent|FREE_TRIAL_EXTENSION|
|scheduledMessageToBeSent|FREE_TIER_TRANSITION_COMPLETE|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

<h1 id="sample-api-survey-creation-controller">survey-creation-controller</h1>

## createUserPaidPlanShiftSurvey_1

<a id="opIdcreateUserPaidPlanShiftSurvey_1"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/survey/userPaidShift/create',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/survey/userPaidShift/create', headers = headers)

print(r.json())

```

`POST /api/v1/admin/survey/userPaidShift/create`

> Body parameter

```json
{
  "file": "string"
}
```

<h3 id="createuserpaidplanshiftsurvey_1-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|none|
|» file|body|string(binary)|true|none|

> Example responses

> 200 Response

<h3 id="createuserpaidplanshiftsurvey_1-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[UserPaidPlanShiftSurveyUploadCumulativeResponseDto](#schemauserpaidplanshiftsurveyuploadcumulativeresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## sendSurveyRequests

<a id="opIdsendSurveyRequests"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/survey/create',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/survey/create', headers = headers)

print(r.json())

```

`POST /api/v1/admin/survey/create`

> Body parameter

```json
{
  "file": "string"
}
```

<h3 id="sendsurveyrequests-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|none|
|» file|body|string(binary)|true|none|

> Example responses

> 200 Response

<h3 id="sendsurveyrequests-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[SurveyFileResponse](#schemasurveyfileresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

<h1 id="sample-api-corporate-user-paid-nudge-survey-controller">corporate-user-paid-nudge-survey-controller</h1>

## createUserPaidPlanShiftSurvey_2

<a id="opIdcreateUserPaidPlanShiftSurvey_2"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/survey/corporate/trigger',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/survey/corporate/trigger', headers = headers)

print(r.json())

```

`POST /api/v1/admin/survey/corporate/trigger`

> Body parameter

```json
[
  {
    "userId": "string"
  }
]
```

<h3 id="createuserpaidplanshiftsurvey_2-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[UserPaidPlanShiftSurveyTriggerRequestDto](#schemauserpaidplanshiftsurveytriggerrequestdto)|true|none|

<h3 id="createuserpaidplanshiftsurvey_2-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## createUserPaidPlanShiftSurvey_3

<a id="opIdcreateUserPaidPlanShiftSurvey_3"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/survey/corporate/payNudge/create',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/survey/corporate/payNudge/create', headers = headers)

print(r.json())

```

`POST /api/v1/admin/survey/corporate/payNudge/create`

> Body parameter

```json
{
  "file": "string"
}
```

<h3 id="createuserpaidplanshiftsurvey_3-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|none|
|» file|body|string(binary)|true|none|

<h3 id="createuserpaidplanshiftsurvey_3-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

<h1 id="sample-api-admin-report-controller">admin-report-controller</h1>

## createPaymentsRelatedReport

<a id="opIdcreatePaymentsRelatedReport"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/reports/payments/generate',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/reports/payments/generate', headers = headers)

print(r.json())

```

`POST /api/v1/admin/reports/payments/generate`

> Body parameter

```json
{
  "startTime": "2019-08-24T14:15:22Z",
  "endTime": "2019-08-24T14:15:22Z",
  "emailIds": "string"
}
```

<h3 id="createpaymentsrelatedreport-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[AdminUserDataReportGenerationRequestDto](#schemaadminuserdatareportgenerationrequestdto)|true|none|

> Example responses

> 200 Response

```json
{
  "reportType": "CONSOLIDATED_USER_DATA",
  "message": "string"
}
```

<h3 id="createpaymentsrelatedreport-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[AdminReportGenerationResponseDto](#schemaadminreportgenerationresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## createPricingInformation_2

<a id="opIdcreatePricingInformation_2"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/reports/consolidatedUsers/generate',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/reports/consolidatedUsers/generate', headers = headers)

print(r.json())

```

`POST /api/v1/admin/reports/consolidatedUsers/generate`

> Body parameter

```json
{
  "startTime": "2019-08-24T14:15:22Z",
  "endTime": "2019-08-24T14:15:22Z",
  "emailIds": "string"
}
```

<h3 id="createpricinginformation_2-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[AdminUserDataReportGenerationRequestDto](#schemaadminuserdatareportgenerationrequestdto)|true|none|

> Example responses

> 200 Response

```json
{
  "reportType": "CONSOLIDATED_USER_DATA",
  "message": "string"
}
```

<h3 id="createpricinginformation_2-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[AdminReportGenerationResponseDto](#schemaadminreportgenerationresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

<h1 id="sample-api-admin-instrument-update-message-controller">admin-instrument-update-message-controller</h1>

## replayInstrumentUpdate

<a id="opIdreplayInstrumentUpdate"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/instrumentUpdates/replay',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/instrumentUpdates/replay', headers = headers)

print(r.json())

```

`POST /api/v1/admin/instrumentUpdates/replay`

> Body parameter

```json
{
  "instrumentUpdateId": 0
}
```

<h3 id="replayinstrumentupdate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[InstrumentUpdateReplayRequestDto](#schemainstrumentupdatereplayrequestdto)|true|none|

<h3 id="replayinstrumentupdate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## getAllInstrumentUpdateMessages_1

<a id="opIdgetAllInstrumentUpdateMessages_1"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.get 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/instrumentUpdates',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.get('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/instrumentUpdates', headers = headers)

print(r.json())

```

`GET /api/v1/admin/instrumentUpdates`

<h3 id="getallinstrumentupdatemessages_1-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|pageNo|query|integer(int32)|false|none|
|pageSize|query|integer(int32)|false|none|
|sortBy|query|string|false|none|
|status|query|string|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|status|ALL|
|status|FAILED|

> Example responses

> 200 Response

<h3 id="getallinstrumentupdatemessages_1-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[PageInstrumentUpdateResponseDto](#schemapageinstrumentupdateresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

<h1 id="sample-api-admin-instrument-details-controller">admin-instrument-details-controller</h1>

## importFromNse

<a id="opIdimportFromNse"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/instrumentDetails/nse/import',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/instrumentDetails/nse/import', headers = headers)

print(r.json())

```

`POST /api/v1/admin/instrumentDetails/nse/import`

> Body parameter

```json
{
  "file": "string"
}
```

<h3 id="importfromnse-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|none|
|» file|body|string(binary)|true|none|

> Example responses

> 200 Response

<h3 id="importfromnse-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[AdminFileNseImportResponseDto](#schemaadminfilenseimportresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## importFromListedEquity_2

<a id="opIdimportFromListedEquity_2"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/instrumentDetails/bse/import',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/instrumentDetails/bse/import', headers = headers)

print(r.json())

```

`POST /api/v1/admin/instrumentDetails/bse/import`

> Body parameter

```json
{
  "file": "string"
}
```

<h3 id="importfromlistedequity_2-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|none|
|» file|body|string(binary)|true|none|

> Example responses

> 200 Response

<h3 id="importfromlistedequity_2-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[AdminFileImportReportResponseDto](#schemaadminfileimportreportresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## getInstrumentDetailSnapshot

<a id="opIdgetInstrumentDetailSnapshot"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.get 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/instrumentDetails/snapshot',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.get('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/instrumentDetails/snapshot', headers = headers)

print(r.json())

```

`GET /api/v1/admin/instrumentDetails/snapshot`

> Example responses

> 200 Response

<h3 id="getinstrumentdetailsnapshot-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[InstrumentDetailSnapshotResponseDto](#schemainstrumentdetailsnapshotresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## getLastInstrumentFileUploadLog

<a id="opIdgetLastInstrumentFileUploadLog"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.get 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/instrumentDetails/lastImport',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.get('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/instrumentDetails/lastImport', headers = headers)

print(r.json())

```

`GET /api/v1/admin/instrumentDetails/lastImport`

> Example responses

> 200 Response

<h3 id="getlastinstrumentfileuploadlog-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[InstrumentFileUploadLogResponseDto](#schemainstrumentfileuploadlogresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

<h1 id="sample-api-bse-data-fetch-controller">bse-data-fetch-controller</h1>

## replayFailedCorpAnnouncements

<a id="opIdreplayFailedCorpAnnouncements"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.post 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/bseDataFetcher/corpAnnouncements/retry',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.post('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/bseDataFetcher/corpAnnouncements/retry', headers = headers)

print(r.json())

```

`POST /api/v1/admin/bseDataFetcher/corpAnnouncements/retry`

> Body parameter

```json
{
  "newsIds": [
    "string"
  ]
}
```

<h3 id="replayfailedcorpannouncements-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[RetryNewsIdRequestDto](#schemaretrynewsidrequestdto)|true|none|

> Example responses

> 200 Response

<h3 id="replayfailedcorpannouncements-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="replayfailedcorpannouncements-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[RetryNewsIdResponseDto](#schemaretrynewsidresponsedto)]|false|none|none|
|» newsId|string|false|none|none|
|» retryNewsId|string|false|none|none|
|» status|string|false|none|none|
|» failureReason|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## getCorporateAnnouncementsForDateRange

<a id="opIdgetCorporateAnnouncementsForDateRange"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.get 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/bseDataFetcher/corpAnnouncements/',
  params: {
  'fromDate' => 'string',
'toDate' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.get('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/bseDataFetcher/corpAnnouncements/', params={
  'fromDate': 'string',  'toDate': 'string'
}, headers = headers)

print(r.json())

```

`GET /api/v1/admin/bseDataFetcher/corpAnnouncements/`

<h3 id="getcorporateannouncementsfordaterange-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|fromDate|query|string|true|none|
|toDate|query|string|true|none|

> Example responses

> 200 Response

<h3 id="getcorporateannouncementsfordaterange-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[BseDataFetchResponseDto](#schemabsedatafetchresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

<h1 id="sample-api-user-refer-and-earn-controller">user-refer-and-earn-controller</h1>

## updateUserInstrumentTracking_4

<a id="opIdupdateUserInstrumentTracking_4"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.get 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/users/referral/link',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.get('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/users/referral/link', headers = headers)

print(r.json())

```

`GET /api/v1/users/referral/link`

> Example responses

> 200 Response

<h3 id="updateuserinstrumenttracking_4-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[UserReferralLinkResponseDto](#schemauserreferrallinkresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

<h1 id="sample-api-power-automate-feed-controller">power-automate-feed-controller</h1>

## getLastFewUpdates

<a id="opIdgetLastFewUpdates"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.get 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/pa/feed/updates',
  params: {
  'id' => 'string',
'idType' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.get('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/pa/feed/updates', params={
  'id': 'string',  'idType': 'BSE_SCRIP_CODE'
}, headers = headers)

print(r.json())

```

`GET /api/v1/pa/feed/updates`

<h3 id="getlastfewupdates-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|pageSize|query|integer(int32)|false|none|
|sortBy|query|string|false|none|
|sortDirection|query|string|false|none|
|id|query|string|true|none|
|idType|query|string|true|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|idType|BSE_SCRIP_CODE|
|idType|ISIN|
|idType|NSE_TICKR|
|idType|BSE_TICKR|

> Example responses

> 200 Response

<h3 id="getlastfewupdates-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="getlastfewupdates-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[IndividualInstrumentUpdateResponseDto](#schemaindividualinstrumentupdateresponsedto)]|false|none|none|
|» id|integer(int64)|false|none|none|
|» scripDetails|[ScripDetailResponseDto](#schemascripdetailresponsedto)|false|none|none|
|»» scripCode|string|false|none|none|
|»» scripName|string|false|none|none|
|»» bseTickr|string|false|none|none|
|»» nseTickr|string|false|none|none|
|»» isin|string|false|none|none|
|» linkDetail|[LinkDetailResponseDto](#schemalinkdetailresponsedto)|false|none|none|
|»» shortLink|string|false|none|none|
|»» linkSource|string|false|none|none|
|»» effectiveLink|string|false|none|none|
|»» linkSourceRaw|string|false|none|none|
|» updateType|string|false|none|none|
|» updateSubTypeRaw|string|false|none|none|
|» source|string|false|none|none|
|» title|string|false|none|none|
|» description|string|false|none|none|
|» content|string|false|none|none|
|» link|string|false|none|none|
|» creationTime|integer(int64)|false|none|none|
|» lastUpdateTime|integer(int64)|false|none|none|
|» caSpecificCategory|string|false|none|none|
|» filterCategory|string|false|none|none|
|» filterCategoryId|string|false|none|none|
|» additionalInformation|[JsonNode](#schemajsonnode)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|linkSource|BSE|
|linkSource|MONEYCONTROL|
|linkSource|CNBCTV18|
|linkSource|BUSINESS_STANDARD|
|linkSource|TRADING_VIEW|
|linkSource|ALPHASTREET|
|linkSource|TWITTER|
|linkSource|YOUTUBE|
|linkSource|MINT|
|linkSource|UNKNOWN|
|linkSource|SCOUTQUEST|
|linkSource|NSE|
|updateType|CORPORATE_ANNOUNCEMENT|
|updateType|TECHNICAL_ANALYSIS|
|updateType|GENERAL_NEWS|
|updateType|TELEGRAM|
|updateType|TWEET|
|updateType|BULLETIN|
|updateType|RSS|
|updateType|CONCALL_HIGHLIGHTS|
|updateType|CONCALL_SUMMARY|
|updateType|FUTURE_OUTLOOK|
|updateType|BULK_BLOCK|
|updateType|SQ_SPVMA_INTRADAY_VOLUME_SPURT|
|updateType|ANALYST_VIEWS|
|source|CORPORATE_ANNOUNCEMENT|
|source|CORPORATE_ANNOUNCEMENT_PDF_AI|
|source|CORPORATE_ANNOUNCEMENT_SAST|
|source|TRADINGVIEW|
|source|MONEYCONTROL_NEWS|
|source|CNBCTV18|
|source|CNBCTV18_MARKET_LIVE|
|source|NA|
|source|RSS_BUSINESS_STANDARD|
|source|RSS_LIVE_MINT|
|source|RSS_MONEYCONTROL|
|source|RSS|
|source|ALPHASTREET_CONCALL_HIGHLIGHTS|
|source|YOUTUBE_NEWS|
|source|SQ_CONCALL_DECODER|
|source|SQ_CRYSTAL_BALL|
|source|BULK_DEALS|
|source|BLOCK_DEALS|
|source|SQ_SPVMA_INTRADAY_VOLUME_SPURT|
|source|ANALYST_VIEWS|
|filterCategory|UNPROCESSED|
|filterCategory|KEY_UPDATE|
|filterCategory|UNCLASSIFIED|
|filterCategory|ANALYTICAL_UPDATE|
|filterCategory|EVENT_SCHEDULE|
|filterCategory|TECHNICAL_IDEA|
|filterCategory|MEDIA_COVERAGE|
|filterCategory|SPVMA|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

<h1 id="sample-api-mobile-user-feed-controller">mobile-user-feed-controller</h1>

## getAllInstrumentUpdateMessages

<a id="opIdgetAllInstrumentUpdateMessages"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.get 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/mobile/user/updates',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.get('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/mobile/user/updates', headers = headers)

print(r.json())

```

`GET /api/v1/mobile/user/updates`

<h3 id="getallinstrumentupdatemessages-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|pageNo|query|integer(int32)|false|none|
|pageSize|query|integer(int32)|false|none|
|sortBy|query|string|false|none|
|sortDirection|query|string|false|none|
|userId|query|integer(int64)|false|none|
|startTime|query|string|false|none|

> Example responses

> 200 Response

<h3 id="getallinstrumentupdatemessages-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[UserMobileResponseDto](#schemausermobileresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

## searchInstruments

<a id="opIdsearchInstruments"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.get 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/mobile/search',
  params: {
  'id' => 'string',
'idType' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.get('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/mobile/search', params={
  'id': 'string',  'idType': 'BSE_SCRIP_CODE'
}, headers = headers)

print(r.json())

```

`GET /api/v1/mobile/search`

<h3 id="searchinstruments-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|pageNo|query|integer(int32)|false|none|
|pageSize|query|integer(int32)|false|none|
|sortBy|query|string|false|none|
|sortDirection|query|string|false|none|
|id|query|string|true|none|
|idType|query|string|true|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|idType|BSE_SCRIP_CODE|
|idType|ISIN|
|idType|NSE_TICKR|
|idType|BSE_TICKR|

> Example responses

> 200 Response

<h3 id="searchinstruments-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[UserMobileResponseDto](#schemausermobileresponsedto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

<h1 id="sample-api-sse-feed-controller">sse-feed-controller</h1>

## createPaymentMandateForUser_7

<a id="opIdcreatePaymentMandateForUser_7"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'text/event-stream',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.get 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/feed/sse/test/subscribe/{id}',
  params: {
  'key' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'text/event-stream',
  'Authorization': 'Basic {access-token}'
}

r = requests.get('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/feed/sse/test/subscribe/{id}', params={
  'key': 'string'
}, headers = headers)

print(r.json())

```

`GET /api/v1/feed/sse/test/subscribe/{id}`

<h3 id="createpaymentmandateforuser_7-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|
|key|query|string|true|none|

> Example responses

> 200 Response

<h3 id="createpaymentmandateforuser_7-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[SseEmitter](#schemasseemitter)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

<h1 id="sample-api-broker-detail-controller">broker-detail-controller</h1>

## getBrokerDetails

<a id="opIdgetBrokerDetails"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.get 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/brokers/lookup',
  params: {
  'name' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.get('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/brokers/lookup', params={
  'name': 'string'
}, headers = headers)

print(r.json())

```

`GET /api/v1/brokers/lookup`

<h3 id="getbrokerdetails-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|name|query|string|true|none|

> Example responses

> 200 Response

<h3 id="getbrokerdetails-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="getbrokerdetails-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[BrokerDetail](#schemabrokerdetail)]|false|none|none|
|» id|integer(int32)|false|none|none|
|» aka|string|false|none|none|
|» company|string|false|none|none|
|» symbol|string|false|none|none|
|» gatewayHoldingSupported|boolean|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

<h1 id="sample-api-admin-analytics-controller">admin-analytics-controller</h1>

## getCountOfUsers

<a id="opIdgetCountOfUsers"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => '*/*',
  'Authorization' => 'Basic {access-token}'
}

result = RestClient.get 'http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/analytics/dashboard',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*',
  'Authorization': 'Basic {access-token}'
}

r = requests.get('http://scoutquest-backend-service-staging.fundsmap.com/api/v1/admin/analytics/dashboard', headers = headers)

print(r.json())

```

`GET /api/v1/admin/analytics/dashboard`

<h3 id="getcountofusers-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|magnitude|query|integer(int32)|false|none|
|timeUnit|query|string|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|timeUnit|DAY|
|timeUnit|WEEK|
|timeUnit|MONTH|
|timeUnit|YEAR|

> Example responses

> 200 Response

<h3 id="getcountofusers-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DashboardAnalyticsDto](#schemadashboardanalyticsdto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
basicAuth
</aside>

# Schemas

<h2 id="tocS_CumulativeDiscountReminderMessageEditRequest">CumulativeDiscountReminderMessageEditRequest</h2>

<a id="schemacumulativediscountremindermessageeditrequest"></a>
<a id="schema_CumulativeDiscountReminderMessageEditRequest"></a>
<a id="tocScumulativediscountremindermessageeditrequest"></a>
<a id="tocscumulativediscountremindermessageeditrequest"></a>

```json
{
  "surveyIds": [
    0
  ],
  "bodyValues": [
    "string"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|surveyIds|[integer]|true|none|none|
|bodyValues|[string]|true|none|none|

<h2 id="tocS_DiscountReminderMessageResponseDto">DiscountReminderMessageResponseDto</h2>

<a id="schemadiscountremindermessageresponsedto"></a>
<a id="schema_DiscountReminderMessageResponseDto"></a>
<a id="tocSdiscountremindermessageresponsedto"></a>
<a id="tocsdiscountremindermessageresponsedto"></a>

```json
{
  "id": 0,
  "creationTime": 0,
  "userId": 0,
  "countryCode": "string",
  "mobileNumber": 0,
  "createdByUserId": 0,
  "scheduledNextMessageTime": 0,
  "scheduledNextMessageType": "MARKETING_REMINDER",
  "scheduledNextMessageReminderType": "FIRST_MESSAGE",
  "noOfTimesReminderMessagesToBeSent": 0,
  "noOfTimesReminderMessagesAlreadySent": 0,
  "startTime": 0,
  "endTime": 0,
  "sentMessageLog": [
    {
      "messageSentReceipt": "string",
      "id": "string",
      "creationTime": 0,
      "messageType": "MARKETING_REMINDER",
      "reminderType": "FIRST_MESSAGE"
    }
  ],
  "templateId": "string",
  "userPaidMarkTime": 0,
  "surveyStatus": "CREATED",
  "surveyType": "TRIAL_USER_FEEDBACK",
  "reminderTimes": [
    0
  ],
  "bodyValues": [
    "string"
  ],
  "ctaValue": "string",
  "headerValue": "string",
  "headerType": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer(int64)|false|none|none|
|creationTime|integer(int64)|false|none|none|
|userId|integer(int64)|false|none|none|
|countryCode|string|false|none|none|
|mobileNumber|integer(int64)|false|none|none|
|createdByUserId|integer(int64)|false|none|none|
|scheduledNextMessageTime|integer(int64)|false|none|none|
|scheduledNextMessageType|string|false|none|none|
|scheduledNextMessageReminderType|string|false|none|none|
|noOfTimesReminderMessagesToBeSent|integer(int32)|false|none|none|
|noOfTimesReminderMessagesAlreadySent|integer(int32)|false|none|none|
|startTime|integer(int64)|false|none|none|
|endTime|integer(int64)|false|none|none|
|sentMessageLog|[[DiscountReminderSentMessage](#schemadiscountremindersentmessage)]|false|none|none|
|templateId|string|false|none|none|
|userPaidMarkTime|integer(int64)|false|none|none|
|surveyStatus|string|false|none|none|
|surveyType|string|false|none|none|
|reminderTimes|[integer]|false|none|none|
|bodyValues|[string]|false|none|none|
|ctaValue|string|false|none|none|
|headerValue|string|false|none|none|
|headerType|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|scheduledNextMessageType|MARKETING_REMINDER|
|scheduledNextMessageReminderType|FIRST_MESSAGE|
|scheduledNextMessageReminderType|FOLLOW_UP|
|scheduledNextMessageReminderType|FINAL_MESSAGE|
|surveyStatus|CREATED|
|surveyStatus|REMINDER_SENT|
|surveyStatus|USER_PAID|
|surveyStatus|REMINDER_COMPLETE|
|surveyStatus|USER_UNSUBSCRIBED|
|surveyType|TRIAL_USER_FEEDBACK|
|surveyType|CONVERT_TRIAL_TO_PAID_SURVEY_CASUAL|
|surveyType|CONVERT_TRIAL_TO_PAID_SURVEY_CORPORATE|
|surveyType|FLASH_SALE|
|surveyType|FESTIVE_DISCOUNT|

<h2 id="tocS_DiscountReminderSentMessage">DiscountReminderSentMessage</h2>

<a id="schemadiscountremindersentmessage"></a>
<a id="schema_DiscountReminderSentMessage"></a>
<a id="tocSdiscountremindersentmessage"></a>
<a id="tocsdiscountremindersentmessage"></a>

```json
{
  "messageSentReceipt": "string",
  "id": "string",
  "creationTime": 0,
  "messageType": "MARKETING_REMINDER",
  "reminderType": "FIRST_MESSAGE"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|messageSentReceipt|string|false|none|none|
|id|string|false|none|none|
|creationTime|integer(int64)|false|none|none|
|messageType|string|false|none|none|
|reminderType|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|messageType|MARKETING_REMINDER|
|reminderType|FIRST_MESSAGE|
|reminderType|FOLLOW_UP|
|reminderType|FINAL_MESSAGE|

<h2 id="tocS_CorporateDomainUpdateRequestDto">CorporateDomainUpdateRequestDto</h2>

<a id="schemacorporatedomainupdaterequestdto"></a>
<a id="schema_CorporateDomainUpdateRequestDto"></a>
<a id="tocScorporatedomainupdaterequestdto"></a>
<a id="tocscorporatedomainupdaterequestdto"></a>

```json
{
  "id": "string",
  "website": "string",
  "companyName": "string",
  "industry": "string",
  "budgetForFreeUser": 400,
  "status": "PRIVILEGED"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|true|none|none|
|website|string|false|none|none|
|companyName|string|false|none|none|
|industry|string|false|none|none|
|budgetForFreeUser|integer(int32)|false|none|none|
|status|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|PRIVILEGED|
|status|NOT_PRIVILEGED|
|status|UNDETERMINED|

<h2 id="tocS_CorporateDomainResponseDto">CorporateDomainResponseDto</h2>

<a id="schemacorporatedomainresponsedto"></a>
<a id="schema_CorporateDomainResponseDto"></a>
<a id="tocScorporatedomainresponsedto"></a>
<a id="tocscorporatedomainresponsedto"></a>

```json
{
  "id": "string",
  "domain": "string",
  "website": "string",
  "companyName": "string",
  "industry": "string",
  "creationTime": 0,
  "budgetForFreeUser": 0,
  "status": "PRIVILEGED",
  "companyId": 0,
  "userCount": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|none|none|
|domain|string|false|none|none|
|website|string|false|none|none|
|companyName|string|false|none|none|
|industry|string|false|none|none|
|creationTime|integer(int64)|false|none|none|
|budgetForFreeUser|integer(int32)|false|none|none|
|status|string|false|none|none|
|companyId|integer(int64)|false|none|none|
|userCount|integer(int64)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|PRIVILEGED|
|status|NOT_PRIVILEGED|
|status|UNDETERMINED|

<h2 id="tocS_CorporateDomainUpdateResponseDto">CorporateDomainUpdateResponseDto</h2>

<a id="schemacorporatedomainupdateresponsedto"></a>
<a id="schema_CorporateDomainUpdateResponseDto"></a>
<a id="tocScorporatedomainupdateresponsedto"></a>
<a id="tocscorporatedomainupdateresponsedto"></a>

```json
{
  "corporateDomainResponseDto": {
    "id": "string",
    "domain": "string",
    "website": "string",
    "companyName": "string",
    "industry": "string",
    "creationTime": 0,
    "budgetForFreeUser": 0,
    "status": "PRIVILEGED",
    "companyId": 0,
    "userCount": 0
  },
  "totalAffectedUsers": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|corporateDomainResponseDto|[CorporateDomainResponseDto](#schemacorporatedomainresponsedto)|false|none|none|
|totalAffectedUsers|integer(int32)|false|none|none|

<h2 id="tocS_BackPopulateUserCorporateInformationRequestDto">BackPopulateUserCorporateInformationRequestDto</h2>

<a id="schemabackpopulateusercorporateinformationrequestdto"></a>
<a id="schema_BackPopulateUserCorporateInformationRequestDto"></a>
<a id="tocSbackpopulateusercorporateinformationrequestdto"></a>
<a id="tocsbackpopulateusercorporateinformationrequestdto"></a>

```json
{
  "userIds": [
    0
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|userIds|[integer]|false|none|none|

<h2 id="tocS_BackPopulateUserCorporateInformationResponseDto">BackPopulateUserCorporateInformationResponseDto</h2>

<a id="schemabackpopulateusercorporateinformationresponsedto"></a>
<a id="schema_BackPopulateUserCorporateInformationResponseDto"></a>
<a id="tocSbackpopulateusercorporateinformationresponsedto"></a>
<a id="tocsbackpopulateusercorporateinformationresponsedto"></a>

```json
{
  "totalCount": 0,
  "successCount": 0,
  "errorCount": 0,
  "success": [
    {
      "id": 0,
      "companyName": "string",
      "email": "string",
      "domain": "string",
      "corporateDomainId": 0
    }
  ],
  "errors": {
    "property1": "string",
    "property2": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|totalCount|integer(int32)|false|none|none|
|successCount|integer(int32)|false|none|none|
|errorCount|integer(int32)|false|none|none|
|success|[[BackPopulatedUpdatedUserCorporateInformationResponseDto](#schemabackpopulatedupdatedusercorporateinformationresponsedto)]|false|none|none|
|errors|object|false|none|none|
|» **additionalProperties**|string|false|none|none|

<h2 id="tocS_BackPopulatedUpdatedUserCorporateInformationResponseDto">BackPopulatedUpdatedUserCorporateInformationResponseDto</h2>

<a id="schemabackpopulatedupdatedusercorporateinformationresponsedto"></a>
<a id="schema_BackPopulatedUpdatedUserCorporateInformationResponseDto"></a>
<a id="tocSbackpopulatedupdatedusercorporateinformationresponsedto"></a>
<a id="tocsbackpopulatedupdatedusercorporateinformationresponsedto"></a>

```json
{
  "id": 0,
  "companyName": "string",
  "email": "string",
  "domain": "string",
  "corporateDomainId": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer(int64)|false|none|none|
|companyName|string|false|none|none|
|email|string|false|none|none|
|domain|string|false|none|none|
|corporateDomainId|integer(int64)|false|none|none|

<h2 id="tocS_UserCreationRequestDto">UserCreationRequestDto</h2>

<a id="schemausercreationrequestdto"></a>
<a id="schema_UserCreationRequestDto"></a>
<a id="tocSusercreationrequestdto"></a>
<a id="tocsusercreationrequestdto"></a>

```json
{
  "countryCode": "string",
  "mobileNumber": 0,
  "userType": "RETAIL_USER",
  "referralCode": "string",
  "email": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|countryCode|string|false|none|none|
|mobileNumber|integer(int64)|false|none|none|
|userType|string|false|none|none|
|referralCode|string|false|none|none|
|email|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|userType|RETAIL_USER|
|userType|PMS|

<h2 id="tocS_UserProfilingQuestionRequestDto">UserProfilingQuestionRequestDto</h2>

<a id="schemauserprofilingquestionrequestdto"></a>
<a id="schema_UserProfilingQuestionRequestDto"></a>
<a id="tocSuserprofilingquestionrequestdto"></a>
<a id="tocsuserprofilingquestionrequestdto"></a>

```json
{
  "investmentPreference": "FUNDAMENTAL_BASED",
  "tradingFrequency": "EVERY_DAY",
  "profession": "FULL_TIME_TRADER"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|investmentPreference|string|false|none|none|
|tradingFrequency|string|false|none|none|
|profession|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|investmentPreference|FUNDAMENTAL_BASED|
|investmentPreference|EVENT_BASED|
|investmentPreference|BOTH|
|tradingFrequency|EVERY_DAY|
|tradingFrequency|EVERY_WEEK|
|tradingFrequency|EVERY_MONTH|
|tradingFrequency|LESS_THAN_ONCE_A_MONTH|
|profession|FULL_TIME_TRADER|
|profession|STOCK_MARKET_SECONDARY_PROFESSION|

<h2 id="tocS_UserProfilingQuestionResponseDto">UserProfilingQuestionResponseDto</h2>

<a id="schemauserprofilingquestionresponsedto"></a>
<a id="schema_UserProfilingQuestionResponseDto"></a>
<a id="tocSuserprofilingquestionresponsedto"></a>
<a id="tocsuserprofilingquestionresponsedto"></a>

```json
{
  "investmentPreference": "FUNDAMENTAL_BASED",
  "tradingFrequency": "EVERY_DAY",
  "profession": "FULL_TIME_TRADER"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|investmentPreference|string|false|none|none|
|tradingFrequency|string|false|none|none|
|profession|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|investmentPreference|FUNDAMENTAL_BASED|
|investmentPreference|EVENT_BASED|
|investmentPreference|BOTH|
|tradingFrequency|EVERY_DAY|
|tradingFrequency|EVERY_WEEK|
|tradingFrequency|EVERY_MONTH|
|tradingFrequency|LESS_THAN_ONCE_A_MONTH|
|profession|FULL_TIME_TRADER|
|profession|STOCK_MARKET_SECONDARY_PROFESSION|

<h2 id="tocS_UserNotificationPreferenceUpdateRequestDto">UserNotificationPreferenceUpdateRequestDto</h2>

<a id="schemausernotificationpreferenceupdaterequestdto"></a>
<a id="schema_UserNotificationPreferenceUpdateRequestDto"></a>
<a id="tocSusernotificationpreferenceupdaterequestdto"></a>
<a id="tocsusernotificationpreferenceupdaterequestdto"></a>

```json
{
  "generalNewsPreference": "NONE",
  "technicalAnalysisPreference": "NONE",
  "stopUserNotification": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|generalNewsPreference|string|false|none|none|
|technicalAnalysisPreference|string|false|none|none|
|stopUserNotification|boolean|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|generalNewsPreference|NONE|
|generalNewsPreference|SELECTED|
|generalNewsPreference|ALL|
|technicalAnalysisPreference|NONE|
|technicalAnalysisPreference|SELECTED|
|technicalAnalysisPreference|ALL|

<h2 id="tocS_UserNotificationPreferenceResponseDto">UserNotificationPreferenceResponseDto</h2>

<a id="schemausernotificationpreferenceresponsedto"></a>
<a id="schema_UserNotificationPreferenceResponseDto"></a>
<a id="tocSusernotificationpreferenceresponsedto"></a>
<a id="tocsusernotificationpreferenceresponsedto"></a>

```json
{
  "userId": 0,
  "generalNewsFilter": "NONE",
  "technicalAnalysisFilter": "NONE",
  "active": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|userId|integer(int64)|false|none|none|
|generalNewsFilter|string|false|none|none|
|technicalAnalysisFilter|string|false|none|none|
|active|boolean|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|generalNewsFilter|NONE|
|generalNewsFilter|SELECTED|
|generalNewsFilter|ALL|
|technicalAnalysisFilter|NONE|
|technicalAnalysisFilter|SELECTED|
|technicalAnalysisFilter|ALL|

<h2 id="tocS_UserInstrumentUpdateCategoryFilterMappingRequestDto">UserInstrumentUpdateCategoryFilterMappingRequestDto</h2>

<a id="schemauserinstrumentupdatecategoryfiltermappingrequestdto"></a>
<a id="schema_UserInstrumentUpdateCategoryFilterMappingRequestDto"></a>
<a id="tocSuserinstrumentupdatecategoryfiltermappingrequestdto"></a>
<a id="tocsuserinstrumentupdatecategoryfiltermappingrequestdto"></a>

```json
{
  "userId": 0,
  "category": "KEY_UPDATE",
  "filterScope": "NONE"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|userId|integer(int64)|false|none|none|
|category|string|false|none|none|
|filterScope|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|category|KEY_UPDATE|
|category|UNCLASSIFIED|
|category|ANALYTICAL_UPDATE|
|category|EVENT_SCHEDULE|
|category|TECHNICAL_IDEA|
|category|MEDIA_COVERAGE|
|category|SPVMA|
|filterScope|NONE|
|filterScope|SELECTED|
|filterScope|ALL|

<h2 id="tocS_UserInstrumentUpdateCategoryFilterMappingResponseDto">UserInstrumentUpdateCategoryFilterMappingResponseDto</h2>

<a id="schemauserinstrumentupdatecategoryfiltermappingresponsedto"></a>
<a id="schema_UserInstrumentUpdateCategoryFilterMappingResponseDto"></a>
<a id="tocSuserinstrumentupdatecategoryfiltermappingresponsedto"></a>
<a id="tocsuserinstrumentupdatecategoryfiltermappingresponsedto"></a>

```json
{
  "id": 0,
  "userId": 0,
  "mappingType": "CATEGORY_FILTER",
  "category": "KEY_UPDATE",
  "filterScope": "NONE",
  "lastUpdateTime": 0,
  "isInactive": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer(int64)|false|none|none|
|userId|integer(int64)|false|none|none|
|mappingType|string|false|none|none|
|category|string|false|none|none|
|filterScope|string|false|none|none|
|lastUpdateTime|integer(int64)|false|none|none|
|isInactive|boolean|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|mappingType|CATEGORY_FILTER|
|category|KEY_UPDATE|
|category|UNCLASSIFIED|
|category|ANALYTICAL_UPDATE|
|category|EVENT_SCHEDULE|
|category|TECHNICAL_IDEA|
|category|MEDIA_COVERAGE|
|category|SPVMA|
|filterScope|NONE|
|filterScope|SELECTED|
|filterScope|ALL|

<h2 id="tocS_GenerateOtpRequestDto">GenerateOtpRequestDto</h2>

<a id="schemagenerateotprequestdto"></a>
<a id="schema_GenerateOtpRequestDto"></a>
<a id="tocSgenerateotprequestdto"></a>
<a id="tocsgenerateotprequestdto"></a>

```json
{
  "countryCode": "string",
  "mobileNumber": 0,
  "referralCode": "string",
  "referralSource": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|countryCode|string|true|none|none|
|mobileNumber|integer(int64)|false|none|none|
|referralCode|string|false|none|none|
|referralSource|string|false|none|none|

<h2 id="tocS_GenerateOtpResponseDto">GenerateOtpResponseDto</h2>

<a id="schemagenerateotpresponsedto"></a>
<a id="schema_GenerateOtpResponseDto"></a>
<a id="tocSgenerateotpresponsedto"></a>
<a id="tocsgenerateotpresponsedto"></a>

```json
{
  "signupStatus": "NEW",
  "txnId": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|signupStatus|string|false|none|none|
|txnId|string|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|signupStatus|NEW|
|signupStatus|EXISTING|
|signupStatus|SUSPENDED|

<h2 id="tocS_UserEmailUpdateRequestDto">UserEmailUpdateRequestDto</h2>

<a id="schemauseremailupdaterequestdto"></a>
<a id="schema_UserEmailUpdateRequestDto"></a>
<a id="tocSuseremailupdaterequestdto"></a>
<a id="tocsuseremailupdaterequestdto"></a>

```json
{
  "email": "string",
  "name": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|email|string|true|none|none|
|name|string|true|none|none|

<h2 id="tocS_CorporateEmailResponseDto">CorporateEmailResponseDto</h2>

<a id="schemacorporateemailresponsedto"></a>
<a id="schema_CorporateEmailResponseDto"></a>
<a id="tocScorporateemailresponsedto"></a>
<a id="tocscorporateemailresponsedto"></a>

```json
{
  "id": 0,
  "domain": "string",
  "website": "string",
  "companyName": "string",
  "companyProfile": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer(int64)|false|none|none|
|domain|string|false|none|none|
|website|string|false|none|none|
|companyName|string|false|none|none|
|companyProfile|string|false|none|none|

<h2 id="tocS_UserEmailUpdateEmailResponseDto">UserEmailUpdateEmailResponseDto</h2>

<a id="schemauseremailupdateemailresponsedto"></a>
<a id="schema_UserEmailUpdateEmailResponseDto"></a>
<a id="tocSuseremailupdateemailresponsedto"></a>
<a id="tocsuseremailupdateemailresponsedto"></a>

```json
{
  "user": {
    "countryCode": "string",
    "mobileNumber": 0,
    "userId": "string",
    "userName": "string",
    "name": "string",
    "emailId": "string",
    "roles": [
      "CLIENT"
    ],
    "planType": "TRIAL",
    "creationTime": 0,
    "userPlanExpiryDate": "2019-08-24",
    "isUserProfilingComplete": true,
    "stockTrackingLimit": 0,
    "planNameSchemeRefId": "string",
    "userPrivileged": true,
    "emailVerified": true
  },
  "corporateEmailDetails": {
    "id": 0,
    "domain": "string",
    "website": "string",
    "companyName": "string",
    "companyProfile": "string"
  },
  "corporateProfile": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|user|[UserResponseDto](#schemauserresponsedto)|false|none|none|
|corporateEmailDetails|[CorporateEmailResponseDto](#schemacorporateemailresponsedto)|false|none|none|
|corporateProfile|boolean|false|none|none|

<h2 id="tocS_UserResponseDto">UserResponseDto</h2>

<a id="schemauserresponsedto"></a>
<a id="schema_UserResponseDto"></a>
<a id="tocSuserresponsedto"></a>
<a id="tocsuserresponsedto"></a>

```json
{
  "countryCode": "string",
  "mobileNumber": 0,
  "userId": "string",
  "userName": "string",
  "name": "string",
  "emailId": "string",
  "roles": [
    "CLIENT"
  ],
  "planType": "TRIAL",
  "creationTime": 0,
  "userPlanExpiryDate": "2019-08-24",
  "isUserProfilingComplete": true,
  "stockTrackingLimit": 0,
  "planNameSchemeRefId": "string",
  "userPrivileged": true,
  "emailVerified": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|countryCode|string|false|none|none|
|mobileNumber|integer(int64)|false|none|none|
|userId|string|false|none|none|
|userName|string|false|none|none|
|name|string|false|none|none|
|emailId|string|false|none|none|
|roles|[string]|false|none|none|
|planType|string|false|none|none|
|creationTime|integer(int64)|false|none|none|
|userPlanExpiryDate|string(date)|false|none|none|
|isUserProfilingComplete|boolean|false|none|none|
|stockTrackingLimit|integer(int32)|false|none|none|
|planNameSchemeRefId|string|false|none|none|
|userPrivileged|boolean|false|none|none|
|emailVerified|boolean|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|planType|TRIAL|
|planType|TRIAL_EXPIRED|
|planType|PAID_BASIC|
|planType|PAID_PROFESSIONAL|
|planType|PAID_POWER_USER|
|planType|TRIAL_BASIC|
|planType|TRIAL_PROFESSIONAL|
|planType|TRIAL_POWER_USER|
|planType|FREE|

<h2 id="tocS_CorporateEmailUpdateRequestDto">CorporateEmailUpdateRequestDto</h2>

<a id="schemacorporateemailupdaterequestdto"></a>
<a id="schema_CorporateEmailUpdateRequestDto"></a>
<a id="tocScorporateemailupdaterequestdto"></a>
<a id="tocscorporateemailupdaterequestdto"></a>

```json
{
  "website": "string",
  "designation": "string",
  "companyProfile": "string",
  "companyName": "string",
  "companyId": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|website|string|true|none|none|
|designation|string|false|none|none|
|companyProfile|string|false|none|none|
|companyName|string|true|none|none|
|companyId|integer(int64)|false|none|none|

<h2 id="tocS_UserCorporateInformationResponseDto">UserCorporateInformationResponseDto</h2>

<a id="schemausercorporateinformationresponsedto"></a>
<a id="schema_UserCorporateInformationResponseDto"></a>
<a id="tocSusercorporateinformationresponsedto"></a>
<a id="tocsusercorporateinformationresponsedto"></a>

```json
{
  "companyName": "string",
  "companyProfile": "string",
  "companyWebsite": "string",
  "designation": "string",
  "emailId": "string",
  "userId": "string",
  "name": "string",
  "emailType": "CORPORATE",
  "emailVerified": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|companyName|string|false|none|none|
|companyProfile|string|false|none|none|
|companyWebsite|string|false|none|none|
|designation|string|false|none|none|
|emailId|string|false|none|none|
|userId|string|false|none|none|
|name|string|false|none|none|
|emailType|string|false|none|none|
|emailVerified|boolean|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|emailType|CORPORATE|
|emailType|CASUAL|

<h2 id="tocS_ContinueWithMobileRequestDto">ContinueWithMobileRequestDto</h2>

<a id="schemacontinuewithmobilerequestdto"></a>
<a id="schema_ContinueWithMobileRequestDto"></a>
<a id="tocScontinuewithmobilerequestdto"></a>
<a id="tocscontinuewithmobilerequestdto"></a>

```json
{
  "key": "string",
  "otp": 0,
  "userType": "NEW"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|key|string|true|none|none|
|otp|integer(int32)|true|none|none|
|userType|string|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|userType|NEW|
|userType|EXISTING|
|userType|SUSPENDED|

<h2 id="tocS_ContinueWithMobileResponseDto">ContinueWithMobileResponseDto</h2>

<a id="schemacontinuewithmobileresponsedto"></a>
<a id="schema_ContinueWithMobileResponseDto"></a>
<a id="tocScontinuewithmobileresponsedto"></a>
<a id="tocscontinuewithmobileresponsedto"></a>

```json
{
  "userDetails": {
    "countryCode": "string",
    "mobileNumber": 0,
    "userId": "string",
    "userName": "string",
    "name": "string",
    "emailId": "string",
    "roles": [
      "CLIENT"
    ],
    "planType": "TRIAL",
    "creationTime": 0,
    "userPlanExpiryDate": "2019-08-24",
    "isUserProfilingComplete": true,
    "stockTrackingLimit": 0,
    "planNameSchemeRefId": "string",
    "userPrivileged": true,
    "emailVerified": true
  },
  "token": "string",
  "onboardingStatus": "MOBILE_VERIFIED"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|userDetails|[UserResponseDto](#schemauserresponsedto)|false|none|none|
|token|string|false|none|none|
|onboardingStatus|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|onboardingStatus|MOBILE_VERIFIED|
|onboardingStatus|STOCKS_ADDED|
|onboardingStatus|EMAIL_VERIFIED|
|onboardingStatus|PROFILE_COMPLETE|

<h2 id="tocS_UserDiscountPlanCreationRequestDto">UserDiscountPlanCreationRequestDto</h2>

<a id="schemauserdiscountplancreationrequestdto"></a>
<a id="schema_UserDiscountPlanCreationRequestDto"></a>
<a id="tocSuserdiscountplancreationrequestdto"></a>
<a id="tocsuserdiscountplancreationrequestdto"></a>

```json
{
  "userIds": [
    0
  ],
  "couponCode": "string",
  "startTime": "2019-08-24T14:15:22Z",
  "endTime": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|userIds|[integer]|true|none|none|
|couponCode|string|true|none|none|
|startTime|string(date-time)|true|none|none|
|endTime|string(date-time)|true|none|none|

<h2 id="tocS_CumulativeUserDiscountPlanResponseDto">CumulativeUserDiscountPlanResponseDto</h2>

<a id="schemacumulativeuserdiscountplanresponsedto"></a>
<a id="schema_CumulativeUserDiscountPlanResponseDto"></a>
<a id="tocScumulativeuserdiscountplanresponsedto"></a>
<a id="tocscumulativeuserdiscountplanresponsedto"></a>

```json
{
  "totalCount": 0,
  "successCount": 0,
  "failureCount": 0,
  "failedDiscounts": [
    {
      "user": 0,
      "isSuccess": true,
      "reason": "string",
      "success": true
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|totalCount|integer(int32)|false|none|none|
|successCount|integer(int32)|false|none|none|
|failureCount|integer(int32)|false|none|none|
|failedDiscounts|[[UserDiscountPlanCreationIndividualResponseDto](#schemauserdiscountplancreationindividualresponsedto)]|false|none|none|

<h2 id="tocS_UserDiscountPlanCreationIndividualResponseDto">UserDiscountPlanCreationIndividualResponseDto</h2>

<a id="schemauserdiscountplancreationindividualresponsedto"></a>
<a id="schema_UserDiscountPlanCreationIndividualResponseDto"></a>
<a id="tocSuserdiscountplancreationindividualresponsedto"></a>
<a id="tocsuserdiscountplancreationindividualresponsedto"></a>

```json
{
  "user": 0,
  "isSuccess": true,
  "reason": "string",
  "success": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|user|integer(int64)|false|none|none|
|isSuccess|boolean|false|none|none|
|reason|string|false|none|none|
|success|boolean|false|none|none|

<h2 id="tocS_JsonNode">JsonNode</h2>

<a id="schemajsonnode"></a>
<a id="schema_JsonNode"></a>
<a id="tocSjsonnode"></a>
<a id="tocsjsonnode"></a>

```json
{}

```

### Properties

*None*

<h2 id="tocS_SmallcaseTransactionCreationRequestDto">SmallcaseTransactionCreationRequestDto</h2>

<a id="schemasmallcasetransactioncreationrequestdto"></a>
<a id="schema_SmallcaseTransactionCreationRequestDto"></a>
<a id="tocSsmallcasetransactioncreationrequestdto"></a>
<a id="tocssmallcasetransactioncreationrequestdto"></a>

```json
{
  "brokerName": "string",
  "brokerSymbol": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|brokerName|string|false|none|none|
|brokerSymbol|string|false|none|none|

<h2 id="tocS_SmallcaseTransactionCreationResponseDto">SmallcaseTransactionCreationResponseDto</h2>

<a id="schemasmallcasetransactioncreationresponsedto"></a>
<a id="schema_SmallcaseTransactionCreationResponseDto"></a>
<a id="tocSsmallcasetransactioncreationresponsedto"></a>
<a id="tocssmallcasetransactioncreationresponsedto"></a>

```json
{
  "authToken": "string",
  "gatewayName": "string",
  "brokers": [
    "string"
  ],
  "transactionId": "string",
  "expireAt": "string",
  "smallcaseImportId": "string",
  "userId": 0,
  "transactionStatus": "CREATED"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|authToken|string|false|none|none|
|gatewayName|string|false|none|none|
|brokers|[string]|false|none|none|
|transactionId|string|false|none|none|
|expireAt|string|false|none|none|
|smallcaseImportId|string|false|none|none|
|userId|integer(int64)|false|none|none|
|transactionStatus|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|transactionStatus|CREATED|
|transactionStatus|SUCCESS|
|transactionStatus|FAILED|

<h2 id="tocS_SmallcaseHoldingSuccessPostbackRequestDto">SmallcaseHoldingSuccessPostbackRequestDto</h2>

<a id="schemasmallcaseholdingsuccesspostbackrequestdto"></a>
<a id="schema_SmallcaseHoldingSuccessPostbackRequestDto"></a>
<a id="tocSsmallcaseholdingsuccesspostbackrequestdto"></a>
<a id="tocssmallcaseholdingsuccesspostbackrequestdto"></a>

```json
{
  "smallcaseAuthToken": "string",
  "transactionId": "string",
  "broker": "string",
  "success": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|smallcaseAuthToken|string|false|none|none|
|transactionId|string|false|none|none|
|broker|string|false|none|none|
|success|string|false|none|none|

<h2 id="tocS_SmallcaseHoldingSuccessPostbackResponseDto">SmallcaseHoldingSuccessPostbackResponseDto</h2>

<a id="schemasmallcaseholdingsuccesspostbackresponsedto"></a>
<a id="schema_SmallcaseHoldingSuccessPostbackResponseDto"></a>
<a id="tocSsmallcaseholdingsuccesspostbackresponsedto"></a>
<a id="tocssmallcaseholdingsuccesspostbackresponsedto"></a>

```json
{
  "importId": "string",
  "addedStocks": 0,
  "addedAccounts": 0,
  "stocksAddedToTrackList": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|importId|string|false|none|none|
|addedStocks|integer(int32)|false|none|none|
|addedAccounts|integer(int32)|false|none|none|
|stocksAddedToTrackList|integer(int32)|false|none|none|

<h2 id="tocS_MultiplePricingDetailRequestDto">MultiplePricingDetailRequestDto</h2>

<a id="schemamultiplepricingdetailrequestdto"></a>
<a id="schema_MultiplePricingDetailRequestDto"></a>
<a id="tocSmultiplepricingdetailrequestdto"></a>
<a id="tocsmultiplepricingdetailrequestdto"></a>

```json
{
  "pricingDetail": [
    {
      "name": "string",
      "planType": "BASIC",
      "frequency": "MONTHLY",
      "maximumAmount": 0,
      "firstPaymentAmount": 0,
      "minimumPaymentCount": 0,
      "mandateStrategy": "FIRST_CYCLE_DISCOUNT",
      "mandateFrequency": "ONETIME",
      "initialWindowSizeInDays": 0,
      "firstPaymentBaseAmount": 0,
      "firstPaymentTaxAmount": 0,
      "firstPaymentNonRoundedTotalAmount": 0,
      "firstPaymentRoundedTotalAmount": 0,
      "maximumBaseAmount": 0,
      "maximumTaxAmount": 0,
      "maximumNonRoundedTotalAmount": 0,
      "maximumRoundedTotalAmount": 0,
      "stockTrackingLimit": 0,
      "couponCode": "string",
      "isDiscounted": true,
      "discountPercent": 0,
      "cancelledPerMonthPrice": 0,
      "subscriptionAmountType": "FIX"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|pricingDetail|[[PricingDetailRequestDto](#schemapricingdetailrequestdto)]|false|none|none|

<h2 id="tocS_PricingDetailRequestDto">PricingDetailRequestDto</h2>

<a id="schemapricingdetailrequestdto"></a>
<a id="schema_PricingDetailRequestDto"></a>
<a id="tocSpricingdetailrequestdto"></a>
<a id="tocspricingdetailrequestdto"></a>

```json
{
  "name": "string",
  "planType": "BASIC",
  "frequency": "MONTHLY",
  "maximumAmount": 0,
  "firstPaymentAmount": 0,
  "minimumPaymentCount": 0,
  "mandateStrategy": "FIRST_CYCLE_DISCOUNT",
  "mandateFrequency": "ONETIME",
  "initialWindowSizeInDays": 0,
  "firstPaymentBaseAmount": 0,
  "firstPaymentTaxAmount": 0,
  "firstPaymentNonRoundedTotalAmount": 0,
  "firstPaymentRoundedTotalAmount": 0,
  "maximumBaseAmount": 0,
  "maximumTaxAmount": 0,
  "maximumNonRoundedTotalAmount": 0,
  "maximumRoundedTotalAmount": 0,
  "stockTrackingLimit": 0,
  "couponCode": "string",
  "isDiscounted": true,
  "discountPercent": 0,
  "cancelledPerMonthPrice": 0,
  "subscriptionAmountType": "FIX"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|false|none|none|
|planType|string|false|none|none|
|frequency|string|false|none|none|
|maximumAmount|integer(int32)|false|none|none|
|firstPaymentAmount|integer(int32)|false|none|none|
|minimumPaymentCount|integer(int32)|false|none|none|
|mandateStrategy|string|false|none|none|
|mandateFrequency|string|false|none|none|
|initialWindowSizeInDays|integer(int32)|false|none|none|
|firstPaymentBaseAmount|number|false|none|none|
|firstPaymentTaxAmount|number|false|none|none|
|firstPaymentNonRoundedTotalAmount|number|false|none|none|
|firstPaymentRoundedTotalAmount|number|false|none|none|
|maximumBaseAmount|number|false|none|none|
|maximumTaxAmount|number|false|none|none|
|maximumNonRoundedTotalAmount|number|false|none|none|
|maximumRoundedTotalAmount|number|false|none|none|
|stockTrackingLimit|integer(int32)|false|none|none|
|couponCode|string|false|none|none|
|isDiscounted|boolean|false|none|none|
|discountPercent|integer(int32)|false|none|none|
|cancelledPerMonthPrice|integer(int32)|false|none|none|
|subscriptionAmountType|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|planType|BASIC|
|planType|PROFESSIONAL|
|planType|POWER_USER|
|planType|FREE|
|planType|EXPIRED|
|frequency|MONTHLY|
|frequency|YEARLY|
|mandateStrategy|FIRST_CYCLE_DISCOUNT|
|mandateStrategy|INITIAL_WINDOW_FREE|
|mandateStrategy|DEFAULT|
|mandateFrequency|ONETIME|
|mandateFrequency|ADHOC|
|mandateFrequency|INTRADAY|
|mandateFrequency|DAILY|
|mandateFrequency|WEEKLY|
|mandateFrequency|MONTHLY|
|mandateFrequency|BIMONTHLY|
|mandateFrequency|QUARTERLY|
|mandateFrequency|SEMIANNUALLY|
|mandateFrequency|YEARLY|
|subscriptionAmountType|FIX|
|subscriptionAmountType|VARIABLE|

<h2 id="tocS_MultiplePricingDetailResponse">MultiplePricingDetailResponse</h2>

<a id="schemamultiplepricingdetailresponse"></a>
<a id="schema_MultiplePricingDetailResponse"></a>
<a id="tocSmultiplepricingdetailresponse"></a>
<a id="tocsmultiplepricingdetailresponse"></a>

```json
{
  "pricingInformationList": [
    {
      "name": "string",
      "planType": "BASIC",
      "planFrequency": "MONTHLY",
      "maximumAmount": 0,
      "minimumPaymentCount": 0,
      "mandateStrategy": "FIRST_CYCLE_DISCOUNT",
      "firstPaymentAmount": 0,
      "mandateFrequency": "ONETIME",
      "initialWindowSizeInDays": 0,
      "schemeReferenceId": "string",
      "firstPaymentBaseAmount": 0,
      "firstPaymentTaxAmount": 0,
      "firstPaymentNonRoundedTotalAmount": 0,
      "firstPaymentRoundedTotalAmount": 0,
      "maximumBaseAmount": 0,
      "maximumTaxAmount": 0,
      "maximumNonRoundedTotalAmount": 0,
      "maximumRoundedTotalAmount": 0,
      "stockTrackingLimit": 0,
      "couponCode": "string",
      "isDiscounted": true,
      "discountPercent": 0,
      "cancelledPerMonthPrice": 0,
      "subscriptionAmountType": "FIX"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|pricingInformationList|[[PricingInformationResponseDto](#schemapricinginformationresponsedto)]|false|none|none|

<h2 id="tocS_PricingInformationResponseDto">PricingInformationResponseDto</h2>

<a id="schemapricinginformationresponsedto"></a>
<a id="schema_PricingInformationResponseDto"></a>
<a id="tocSpricinginformationresponsedto"></a>
<a id="tocspricinginformationresponsedto"></a>

```json
{
  "name": "string",
  "planType": "BASIC",
  "planFrequency": "MONTHLY",
  "maximumAmount": 0,
  "minimumPaymentCount": 0,
  "mandateStrategy": "FIRST_CYCLE_DISCOUNT",
  "firstPaymentAmount": 0,
  "mandateFrequency": "ONETIME",
  "initialWindowSizeInDays": 0,
  "schemeReferenceId": "string",
  "firstPaymentBaseAmount": 0,
  "firstPaymentTaxAmount": 0,
  "firstPaymentNonRoundedTotalAmount": 0,
  "firstPaymentRoundedTotalAmount": 0,
  "maximumBaseAmount": 0,
  "maximumTaxAmount": 0,
  "maximumNonRoundedTotalAmount": 0,
  "maximumRoundedTotalAmount": 0,
  "stockTrackingLimit": 0,
  "couponCode": "string",
  "isDiscounted": true,
  "discountPercent": 0,
  "cancelledPerMonthPrice": 0,
  "subscriptionAmountType": "FIX"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|false|none|none|
|planType|string|false|none|none|
|planFrequency|string|false|none|none|
|maximumAmount|integer(int32)|false|none|none|
|minimumPaymentCount|integer(int32)|false|none|none|
|mandateStrategy|string|false|none|none|
|firstPaymentAmount|integer(int32)|false|none|none|
|mandateFrequency|string|false|none|none|
|initialWindowSizeInDays|integer(int32)|false|none|none|
|schemeReferenceId|string|false|none|none|
|firstPaymentBaseAmount|number|false|none|none|
|firstPaymentTaxAmount|number|false|none|none|
|firstPaymentNonRoundedTotalAmount|number|false|none|none|
|firstPaymentRoundedTotalAmount|number|false|none|none|
|maximumBaseAmount|number|false|none|none|
|maximumTaxAmount|number|false|none|none|
|maximumNonRoundedTotalAmount|number|false|none|none|
|maximumRoundedTotalAmount|number|false|none|none|
|stockTrackingLimit|integer(int32)|false|none|none|
|couponCode|string|false|none|none|
|isDiscounted|boolean|false|none|none|
|discountPercent|integer(int32)|false|none|none|
|cancelledPerMonthPrice|integer(int32)|false|none|none|
|subscriptionAmountType|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|planType|BASIC|
|planType|PROFESSIONAL|
|planType|POWER_USER|
|planType|FREE|
|planType|EXPIRED|
|planFrequency|MONTHLY|
|planFrequency|YEARLY|
|mandateStrategy|FIRST_CYCLE_DISCOUNT|
|mandateStrategy|INITIAL_WINDOW_FREE|
|mandateStrategy|DEFAULT|
|mandateFrequency|ONETIME|
|mandateFrequency|ADHOC|
|mandateFrequency|INTRADAY|
|mandateFrequency|DAILY|
|mandateFrequency|WEEKLY|
|mandateFrequency|MONTHLY|
|mandateFrequency|BIMONTHLY|
|mandateFrequency|QUARTERLY|
|mandateFrequency|SEMIANNUALLY|
|mandateFrequency|YEARLY|
|subscriptionAmountType|FIX|
|subscriptionAmountType|VARIABLE|

<h2 id="tocS_MultiValueMapStringString">MultiValueMapStringString</h2>

<a id="schemamultivaluemapstringstring"></a>
<a id="schema_MultiValueMapStringString"></a>
<a id="tocSmultivaluemapstringstring"></a>
<a id="tocsmultivaluemapstringstring"></a>

```json
{
  "all": {
    "property1": "string",
    "property2": "string"
  },
  "empty": true,
  "property1": [
    "string"
  ],
  "property2": [
    "string"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|**additionalProperties**|[string]|false|none|none|
|all|object|false|write-only|none|
|» **additionalProperties**|string|false|none|none|
|empty|boolean|false|none|none|

<h2 id="tocS_TransactionStatusResponseBodyDto">TransactionStatusResponseBodyDto</h2>

<a id="schematransactionstatusresponsebodydto"></a>
<a id="schema_TransactionStatusResponseBodyDto"></a>
<a id="tocStransactionstatusresponsebodydto"></a>
<a id="tocstransactionstatusresponsebodydto"></a>

```json
{
  "userId": "string",
  "schemeRefId": "string",
  "resultInfo": {
    "resultCode": "string",
    "resultStatus": "TXN_SUCCESS",
    "resultMsg": "string"
  },
  "txnId": "string",
  "bankTxnId": "string",
  "orderId": "string",
  "txnAmount": 0,
  "txnType": "string",
  "gatewayName": "string",
  "gatewayInfo": "string",
  "bankName": "string",
  "mid": "string",
  "paymentMode": "CC",
  "txnDate": "string",
  "subsId": "string",
  "merchantUniqueReference": "string",
  "udf1": "string",
  "udf2": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|userId|string|false|none|none|
|schemeRefId|string|false|none|none|
|resultInfo|[TransactionStatusResponseResultInfo](#schematransactionstatusresponseresultinfo)|false|none|none|
|txnId|string|false|none|none|
|bankTxnId|string|false|none|none|
|orderId|string|false|none|none|
|txnAmount|number|false|none|none|
|txnType|string|false|none|none|
|gatewayName|string|false|none|none|
|gatewayInfo|string|false|none|none|
|bankName|string|false|none|none|
|mid|string|false|none|none|
|paymentMode|string|false|none|none|
|txnDate|string|false|none|none|
|subsId|string|false|none|none|
|merchantUniqueReference|string|false|none|none|
|udf1|string|false|none|none|
|udf2|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|paymentMode|CC|
|paymentMode|DC|
|paymentMode|PPI|
|paymentMode|BANK_MANDATE|
|paymentMode|UPI|

<h2 id="tocS_TransactionStatusResponseDto">TransactionStatusResponseDto</h2>

<a id="schematransactionstatusresponsedto"></a>
<a id="schema_TransactionStatusResponseDto"></a>
<a id="tocStransactionstatusresponsedto"></a>
<a id="tocstransactionstatusresponsedto"></a>

```json
{
  "body": {
    "userId": "string",
    "schemeRefId": "string",
    "resultInfo": {
      "resultCode": "string",
      "resultStatus": "TXN_SUCCESS",
      "resultMsg": "string"
    },
    "txnId": "string",
    "bankTxnId": "string",
    "orderId": "string",
    "txnAmount": 0,
    "txnType": "string",
    "gatewayName": "string",
    "gatewayInfo": "string",
    "bankName": "string",
    "mid": "string",
    "paymentMode": "CC",
    "txnDate": "string",
    "subsId": "string",
    "merchantUniqueReference": "string",
    "udf1": "string",
    "udf2": "string"
  },
  "head": {
    "responseTimestamp": "string",
    "signature": "string",
    "version": "string",
    "channelId": "string",
    "clientId": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|body|[TransactionStatusResponseBodyDto](#schematransactionstatusresponsebodydto)|false|none|none|
|head|[TransactionStatusResponseHeadDto](#schematransactionstatusresponseheaddto)|false|none|none|

<h2 id="tocS_TransactionStatusResponseHeadDto">TransactionStatusResponseHeadDto</h2>

<a id="schematransactionstatusresponseheaddto"></a>
<a id="schema_TransactionStatusResponseHeadDto"></a>
<a id="tocStransactionstatusresponseheaddto"></a>
<a id="tocstransactionstatusresponseheaddto"></a>

```json
{
  "responseTimestamp": "string",
  "signature": "string",
  "version": "string",
  "channelId": "string",
  "clientId": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|responseTimestamp|string|false|none|none|
|signature|string|false|none|none|
|version|string|false|none|none|
|channelId|string|false|none|none|
|clientId|string|false|none|none|

<h2 id="tocS_TransactionStatusResponseResultInfo">TransactionStatusResponseResultInfo</h2>

<a id="schematransactionstatusresponseresultinfo"></a>
<a id="schema_TransactionStatusResponseResultInfo"></a>
<a id="tocStransactionstatusresponseresultinfo"></a>
<a id="tocstransactionstatusresponseresultinfo"></a>

```json
{
  "resultCode": "string",
  "resultStatus": "TXN_SUCCESS",
  "resultMsg": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|resultCode|string|false|none|none|
|resultStatus|string|false|none|none|
|resultMsg|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|resultStatus|TXN_SUCCESS|
|resultStatus|TXN_FAILURE|
|resultStatus|PENDING|
|resultStatus|NO_RECORD_FOUND|

<h2 id="tocS_PaytmSubscriptionRevocationRequest">PaytmSubscriptionRevocationRequest</h2>

<a id="schemapaytmsubscriptionrevocationrequest"></a>
<a id="schema_PaytmSubscriptionRevocationRequest"></a>
<a id="tocSpaytmsubscriptionrevocationrequest"></a>
<a id="tocspaytmsubscriptionrevocationrequest"></a>

```json
{
  "subscriptionId": "string",
  "internalOrderId": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|subscriptionId|string|false|none|none|
|internalOrderId|string|false|none|none|

<h2 id="tocS_RenewSubscriptionsList">RenewSubscriptionsList</h2>

<a id="schemarenewsubscriptionslist"></a>
<a id="schema_RenewSubscriptionsList"></a>
<a id="tocSrenewsubscriptionslist"></a>
<a id="tocsrenewsubscriptionslist"></a>

```json
{
  "subscriptionIds": [
    "string"
  ],
  "noOfDays": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|subscriptionIds|[string]|false|none|none|
|noOfDays|integer(int32)|false|none|none|

<h2 id="tocS_IndividualRenewSubscriptionResponseDto">IndividualRenewSubscriptionResponseDto</h2>

<a id="schemaindividualrenewsubscriptionresponsedto"></a>
<a id="schema_IndividualRenewSubscriptionResponseDto"></a>
<a id="tocSindividualrenewsubscriptionresponsedto"></a>
<a id="tocsindividualrenewsubscriptionresponsedto"></a>

```json
{
  "subscriptionId": "string",
  "paytmTxnId": "string",
  "orderId": "string",
  "transactionDate": "string",
  "amount": "string",
  "responseResultInfoDto": {
    "resultStatus": "S",
    "resultCode": "string",
    "resultMsg": "string"
  },
  "preNotificationPaytmReference": "string",
  "preNotificationInternalReference": "string",
  "exceptionMessage": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|subscriptionId|string|false|none|none|
|paytmTxnId|string|false|none|none|
|orderId|string|false|none|none|
|transactionDate|string|false|none|none|
|amount|string|false|none|none|
|responseResultInfoDto|[InitiateSubscriptionResponseResultInfoDto](#schemainitiatesubscriptionresponseresultinfodto)|false|none|none|
|preNotificationPaytmReference|string|false|none|none|
|preNotificationInternalReference|string|false|none|none|
|exceptionMessage|string|false|none|none|

<h2 id="tocS_InitiateSubscriptionResponseResultInfoDto">InitiateSubscriptionResponseResultInfoDto</h2>

<a id="schemainitiatesubscriptionresponseresultinfodto"></a>
<a id="schema_InitiateSubscriptionResponseResultInfoDto"></a>
<a id="tocSinitiatesubscriptionresponseresultinfodto"></a>
<a id="tocsinitiatesubscriptionresponseresultinfodto"></a>

```json
{
  "resultStatus": "S",
  "resultCode": "string",
  "resultMsg": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|resultStatus|string|false|none|none|
|resultCode|string|false|none|none|
|resultMsg|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|resultStatus|S|
|resultStatus|F|
|resultStatus|U|
|resultStatus|TXN_FAILURE|

<h2 id="tocS_RenewSubscriptionDirectly">RenewSubscriptionDirectly</h2>

<a id="schemarenewsubscriptiondirectly"></a>
<a id="schema_RenewSubscriptionDirectly"></a>
<a id="tocSrenewsubscriptiondirectly"></a>
<a id="tocsrenewsubscriptiondirectly"></a>

```json
{
  "subscriptionId": "string",
  "debitDate": "2019-08-24",
  "schemeRefId": "string",
  "custId": "string",
  "amount": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|subscriptionId|string|false|none|none|
|debitDate|string(date)|false|none|none|
|schemeRefId|string|false|none|none|
|custId|string|false|none|none|
|amount|number|false|none|none|

<h2 id="tocS_RenewSubscriptionResponseBodyDto">RenewSubscriptionResponseBodyDto</h2>

<a id="schemarenewsubscriptionresponsebodydto"></a>
<a id="schema_RenewSubscriptionResponseBodyDto"></a>
<a id="tocSrenewsubscriptionresponsebodydto"></a>
<a id="tocsrenewsubscriptionresponsebodydto"></a>

```json
{
  "renewSubscriptionSuccessful": true,
  "resultInfo": {
    "resultStatus": "S",
    "resultCode": "string",
    "resultMsg": "string"
  },
  "txnId": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|renewSubscriptionSuccessful|boolean|false|none|none|
|resultInfo|[InitiateSubscriptionResponseResultInfoDto](#schemainitiatesubscriptionresponseresultinfodto)|false|none|none|
|txnId|string|false|none|none|

<h2 id="tocS_RenewSubscriptionResponseDto">RenewSubscriptionResponseDto</h2>

<a id="schemarenewsubscriptionresponsedto"></a>
<a id="schema_RenewSubscriptionResponseDto"></a>
<a id="tocSrenewsubscriptionresponsedto"></a>
<a id="tocsrenewsubscriptionresponsedto"></a>

```json
{
  "renewSubscriptionSuccessful": true,
  "head": {
    "responseTimestamp": "string",
    "signature": "string",
    "version": "string",
    "clientId": "string"
  },
  "body": {
    "renewSubscriptionSuccessful": true,
    "resultInfo": {
      "resultStatus": "S",
      "resultCode": "string",
      "resultMsg": "string"
    },
    "txnId": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|renewSubscriptionSuccessful|boolean|false|none|none|
|head|[RenewSubscriptionResponseHeadDto](#schemarenewsubscriptionresponseheaddto)|false|none|none|
|body|[RenewSubscriptionResponseBodyDto](#schemarenewsubscriptionresponsebodydto)|false|none|none|

<h2 id="tocS_RenewSubscriptionResponseHeadDto">RenewSubscriptionResponseHeadDto</h2>

<a id="schemarenewsubscriptionresponseheaddto"></a>
<a id="schema_RenewSubscriptionResponseHeadDto"></a>
<a id="tocSrenewsubscriptionresponseheaddto"></a>
<a id="tocsrenewsubscriptionresponseheaddto"></a>

```json
{
  "responseTimestamp": "string",
  "signature": "string",
  "version": "string",
  "clientId": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|responseTimestamp|string|false|none|none|
|signature|string|false|none|none|
|version|string|false|none|none|
|clientId|string|false|none|none|

<h2 id="tocS_PaytmPreNotificationErrorResponseDto">PaytmPreNotificationErrorResponseDto</h2>

<a id="schemapaytmprenotificationerrorresponsedto"></a>
<a id="schema_PaytmPreNotificationErrorResponseDto"></a>
<a id="tocSpaytmprenotificationerrorresponsedto"></a>
<a id="tocspaytmprenotificationerrorresponsedto"></a>

```json
{
  "subscriptionId": "string",
  "error": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|subscriptionId|string|false|none|none|
|error|string|false|none|none|

<h2 id="tocS_PaytmPreNotificationResponseDto">PaytmPreNotificationResponseDto</h2>

<a id="schemapaytmprenotificationresponsedto"></a>
<a id="schema_PaytmPreNotificationResponseDto"></a>
<a id="tocSpaytmprenotificationresponsedto"></a>
<a id="tocspaytmprenotificationresponsedto"></a>

```json
{
  "id": "string",
  "paytmSubscriptionId": "string",
  "transactionDate": "2019-08-24",
  "invoiceDisplayId": "string",
  "mid": "string",
  "amount": 0,
  "paytmReferenceId": "string",
  "orderId": "string",
  "notificationSentTime": "2019-08-24T14:15:22Z",
  "creationTimestamp": 0,
  "notificationSuccessTime": "2019-08-24T14:15:22Z",
  "notificationStatus": "SUCCESS",
  "notificationStatusCode": "string",
  "notificationStatusMessage": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|none|none|
|paytmSubscriptionId|string|false|none|none|
|transactionDate|string(date)|false|none|none|
|invoiceDisplayId|string|false|none|none|
|mid|string|false|none|none|
|amount|number|false|none|none|
|paytmReferenceId|string|false|none|none|
|orderId|string|false|none|none|
|notificationSentTime|string(date-time)|false|none|none|
|creationTimestamp|integer(int64)|false|none|none|
|notificationSuccessTime|string(date-time)|false|none|none|
|notificationStatus|string|false|none|none|
|notificationStatusCode|string|false|none|none|
|notificationStatusMessage|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|notificationStatus|SUCCESS|
|notificationStatus|FAILURE|
|notificationStatus|PENDING|
|notificationStatus|REVOKED|
|notificationStatus|BLOCKED|
|notificationStatus|CLOSED|

<h2 id="tocS_PaytmPreNotificationResponseListDto">PaytmPreNotificationResponseListDto</h2>

<a id="schemapaytmprenotificationresponselistdto"></a>
<a id="schema_PaytmPreNotificationResponseListDto"></a>
<a id="tocSpaytmprenotificationresponselistdto"></a>
<a id="tocspaytmprenotificationresponselistdto"></a>

```json
{
  "success": [
    {
      "id": "string",
      "paytmSubscriptionId": "string",
      "transactionDate": "2019-08-24",
      "invoiceDisplayId": "string",
      "mid": "string",
      "amount": 0,
      "paytmReferenceId": "string",
      "orderId": "string",
      "notificationSentTime": "2019-08-24T14:15:22Z",
      "creationTimestamp": 0,
      "notificationSuccessTime": "2019-08-24T14:15:22Z",
      "notificationStatus": "SUCCESS",
      "notificationStatusCode": "string",
      "notificationStatusMessage": "string"
    }
  ],
  "errors": [
    {
      "subscriptionId": "string",
      "error": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|success|[[PaytmPreNotificationResponseDto](#schemapaytmprenotificationresponsedto)]|false|none|none|
|errors|[[PaytmPreNotificationErrorResponseDto](#schemapaytmprenotificationerrorresponsedto)]|false|none|none|

<h2 id="tocS_PaytmSubscriptionPostbackSuccessDto">PaytmSubscriptionPostbackSuccessDto</h2>

<a id="schemapaytmsubscriptionpostbacksuccessdto"></a>
<a id="schema_PaytmSubscriptionPostbackSuccessDto"></a>
<a id="tocSpaytmsubscriptionpostbacksuccessdto"></a>
<a id="tocspaytmsubscriptionpostbacksuccessdto"></a>

```json
{
  "BANKTXNID": "string",
  "CHECKSUMHASH": "string",
  "CURRENCY": "string",
  "GATEWAYNAME": "string",
  "MERC_UNQ_REF": "string",
  "MID": "string",
  "ORDERID": "string",
  "PAYMENTMODE": "string",
  "RESPCODE": "string",
  "RESPMSG": "string",
  "STATUS": "TXN_SUCCESS",
  "SUBS_ID": "string",
  "TXNAMOUNT": 0,
  "TXNDATE": "string",
  "TXNID": "string",
  "UDF_1": "string",
  "UDF_2": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|BANKTXNID|string|false|none|none|
|CHECKSUMHASH|string|false|none|none|
|CURRENCY|string|false|none|none|
|GATEWAYNAME|string|false|none|none|
|MERC_UNQ_REF|string|false|none|none|
|MID|string|false|none|none|
|ORDERID|string|false|none|none|
|PAYMENTMODE|string|false|none|none|
|RESPCODE|string|false|none|none|
|RESPMSG|string|false|none|none|
|STATUS|string|false|none|none|
|SUBS_ID|string|false|none|none|
|TXNAMOUNT|number|false|none|none|
|TXNDATE|string|false|none|none|
|TXNID|string|false|none|none|
|UDF_1|string|false|none|none|
|UDF_2|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|STATUS|TXN_SUCCESS|
|STATUS|TXN_FAILURE|

<h2 id="tocS_DigioManadateCreationSuccessPostbackResponseDto">DigioManadateCreationSuccessPostbackResponseDto</h2>

<a id="schemadigiomanadatecreationsuccesspostbackresponsedto"></a>
<a id="schema_DigioManadateCreationSuccessPostbackResponseDto"></a>
<a id="tocSdigiomanadatecreationsuccesspostbackresponsedto"></a>
<a id="tocsdigiomanadatecreationsuccesspostbackresponsedto"></a>

```json
{
  "upcomingSchedulePlanDetails": {
    "upcomingTransactionDate": "string",
    "upcomingTransactionAmount": 0,
    "currentDebitAmount": 0,
    "planType": "string"
  },
  "upiMandate": {
    "id": "string",
    "state": "INIT",
    "source": "DIGIO",
    "internalMandateStatus": "CREATED",
    "umrn": "string",
    "customerName": "string",
    "customerVpa": "string",
    "maximumAmount": 0,
    "firstCollectionDate": "string",
    "finalCollectionDate": "string",
    "frequency": "Adhoc",
    "customerIdentifier": "string",
    "schemeRefNumber": "string",
    "userId": 0,
    "creationTime": 0,
    "recurring": true
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|upcomingSchedulePlanDetails|[UpcomingSchedulePlanDetailsResponseDto](#schemaupcomingscheduleplandetailsresponsedto)|false|none|none|
|upiMandate|[UpiMandateResponseDto](#schemaupimandateresponsedto)|false|none|none|

<h2 id="tocS_UpcomingSchedulePlanDetailsResponseDto">UpcomingSchedulePlanDetailsResponseDto</h2>

<a id="schemaupcomingscheduleplandetailsresponsedto"></a>
<a id="schema_UpcomingSchedulePlanDetailsResponseDto"></a>
<a id="tocSupcomingscheduleplandetailsresponsedto"></a>
<a id="tocsupcomingscheduleplandetailsresponsedto"></a>

```json
{
  "upcomingTransactionDate": "string",
  "upcomingTransactionAmount": 0,
  "currentDebitAmount": 0,
  "planType": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|upcomingTransactionDate|string|false|none|none|
|upcomingTransactionAmount|number|false|none|none|
|currentDebitAmount|number|false|none|none|
|planType|string|false|none|none|

<h2 id="tocS_UpiMandateResponseDto">UpiMandateResponseDto</h2>

<a id="schemaupimandateresponsedto"></a>
<a id="schema_UpiMandateResponseDto"></a>
<a id="tocSupimandateresponsedto"></a>
<a id="tocsupimandateresponsedto"></a>

```json
{
  "id": "string",
  "state": "INIT",
  "source": "DIGIO",
  "internalMandateStatus": "CREATED",
  "umrn": "string",
  "customerName": "string",
  "customerVpa": "string",
  "maximumAmount": 0,
  "firstCollectionDate": "string",
  "finalCollectionDate": "string",
  "frequency": "Adhoc",
  "customerIdentifier": "string",
  "schemeRefNumber": "string",
  "userId": 0,
  "creationTime": 0,
  "recurring": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|none|none|
|state|string|false|none|none|
|source|string|false|none|none|
|internalMandateStatus|string|false|none|none|
|umrn|string|false|none|none|
|customerName|string|false|none|none|
|customerVpa|string|false|none|none|
|maximumAmount|number|false|none|none|
|firstCollectionDate|string|false|none|none|
|finalCollectionDate|string|false|none|none|
|frequency|string|false|none|none|
|customerIdentifier|string|false|none|none|
|schemeRefNumber|string|false|none|none|
|userId|integer(int64)|false|none|none|
|creationTime|integer(int64)|false|none|none|
|recurring|boolean|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|state|INIT|
|state|IN_AUTHORIZATION|
|state|EXPIRED|
|state|PAUSED|
|state|partial|
|state|auth_success|
|state|dest_register_success|
|state|auth_failed|
|state|revoked|
|source|DIGIO|
|source|PAYTM|
|internalMandateStatus|CREATED|
|internalMandateStatus|AUTHENTICATED|
|internalMandateStatus|REGISTERED|
|internalMandateStatus|SCHEDULED|
|internalMandateStatus|CANCELLED|
|internalMandateStatus|EXPIRED|
|internalMandateStatus|COMPLETED|
|frequency|Adhoc|
|frequency|Daily|
|frequency|Weekly|
|frequency|Monthly|
|frequency|BiMonthly|
|frequency|Quarterly|
|frequency|Semiannually|
|frequency|Yearly|

<h2 id="tocS_PaytmPaymentStatusWebhook">PaytmPaymentStatusWebhook</h2>

<a id="schemapaytmpaymentstatuswebhook"></a>
<a id="schema_PaytmPaymentStatusWebhook"></a>
<a id="tocSpaytmpaymentstatuswebhook"></a>
<a id="tocspaytmpaymentstatuswebhook"></a>

```json
{
  "ORDERID": "string",
  "MID": "string",
  "TXNID": "string",
  "TXNAMOUNT": 0,
  "PAYMENTMODE": "CC",
  "CURRENCY": "INR",
  "TXNDATETIME": "2019-08-24T14:15:22Z",
  "TXNDATE": "2019-08-24",
  "STATUS": "TXN_SUCCESS",
  "RESPCODE": "string",
  "RESPMSG": "string",
  "GATEWAYNAME": "string",
  "BANKTXNID": "string",
  "CHECKSUMHASH": "string",
  "MERC_UNQ_REF": "string",
  "udf_1": "string",
  "udf_2": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|ORDERID|string|false|none|none|
|MID|string|false|none|none|
|TXNID|string|false|none|none|
|TXNAMOUNT|number|false|none|none|
|PAYMENTMODE|string|false|none|none|
|CURRENCY|string|false|none|none|
|TXNDATETIME|string(date-time)|false|none|none|
|TXNDATE|string(date)|false|none|none|
|STATUS|string|false|none|none|
|RESPCODE|string|false|none|none|
|RESPMSG|string|false|none|none|
|GATEWAYNAME|string|false|none|none|
|BANKTXNID|string|false|none|none|
|CHECKSUMHASH|string|false|none|none|
|MERC_UNQ_REF|string|false|none|none|
|udf_1|string|false|none|none|
|udf_2|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|PAYMENTMODE|CC|
|PAYMENTMODE|DC|
|PAYMENTMODE|PPI|
|PAYMENTMODE|BANK_MANDATE|
|PAYMENTMODE|UPI|
|CURRENCY|INR|
|CURRENCY|USD|
|STATUS|TXN_SUCCESS|
|STATUS|TXN_FAILURE|

<h2 id="tocS_PaytmPreNotificationUpdateWebhook">PaytmPreNotificationUpdateWebhook</h2>

<a id="schemapaytmprenotificationupdatewebhook"></a>
<a id="schema_PaytmPreNotificationUpdateWebhook"></a>
<a id="tocSpaytmprenotificationupdatewebhook"></a>
<a id="tocspaytmprenotificationupdatewebhook"></a>

```json
{
  "TXNDATE": "2019-08-24T14:15:22Z",
  "TXNMESSAGE": "string",
  "REFERENCEID": "string",
  "CHECKSUMHASH": "string",
  "NOTIFICATIONDATE": "2019-08-24T14:15:22Z",
  "NOTIFICATIONSTATUS": "SUCCESS",
  "NOTIFICATIONSTATUSCODE": "string",
  "NOTIFICATIONSTATUSMESSAGE": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|TXNDATE|string(date-time)|false|none|none|
|TXNMESSAGE|string|false|none|none|
|REFERENCEID|string|false|none|none|
|CHECKSUMHASH|string|false|none|none|
|NOTIFICATIONDATE|string(date-time)|false|none|none|
|NOTIFICATIONSTATUS|string|false|none|none|
|NOTIFICATIONSTATUSCODE|string|false|none|none|
|NOTIFICATIONSTATUSMESSAGE|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|NOTIFICATIONSTATUS|SUCCESS|
|NOTIFICATIONSTATUS|FAILURE|
|NOTIFICATIONSTATUS|PENDING|
|NOTIFICATIONSTATUS|REVOKED|
|NOTIFICATIONSTATUS|BLOCKED|
|NOTIFICATIONSTATUS|CLOSED|

<h2 id="tocS_PaytmSubscriptionCreationRequestDto">PaytmSubscriptionCreationRequestDto</h2>

<a id="schemapaytmsubscriptioncreationrequestdto"></a>
<a id="schema_PaytmSubscriptionCreationRequestDto"></a>
<a id="tocSpaytmsubscriptioncreationrequestdto"></a>
<a id="tocspaytmsubscriptioncreationrequestdto"></a>

```json
{
  "plan": "BASIC",
  "frequency": "MONTHLY",
  "discountCode": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|plan|string|true|none|none|
|frequency|string|true|none|none|
|discountCode|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|plan|BASIC|
|plan|PROFESSIONAL|
|plan|POWER_USER|
|plan|FREE|
|plan|EXPIRED|
|frequency|MONTHLY|
|frequency|YEARLY|

<h2 id="tocS_CreatedMandateDetailResponseDto">CreatedMandateDetailResponseDto</h2>

<a id="schemacreatedmandatedetailresponsedto"></a>
<a id="schema_CreatedMandateDetailResponseDto"></a>
<a id="tocScreatedmandatedetailresponsedto"></a>
<a id="tocscreatedmandatedetailresponsedto"></a>

```json
{
  "maximumAmount": 0,
  "authType": "upi",
  "firstCollectionDate": "string",
  "finalCollectionDate": "string",
  "frequency": "Adhoc",
  "customerIdentifier": "string",
  "customerRefNumber": "string",
  "schemeRefNumber": "string",
  "recurring": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|maximumAmount|number|false|none|none|
|authType|string|false|none|none|
|firstCollectionDate|string|false|none|none|
|finalCollectionDate|string|false|none|none|
|frequency|string|false|none|none|
|customerIdentifier|string|false|none|none|
|customerRefNumber|string|false|none|none|
|schemeRefNumber|string|false|none|none|
|recurring|boolean|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|authType|upi|
|frequency|Adhoc|
|frequency|Daily|
|frequency|Weekly|
|frequency|Monthly|
|frequency|BiMonthly|
|frequency|Quarterly|
|frequency|Semiannually|
|frequency|Yearly|

<h2 id="tocS_PaytmSubscriptionCreationResponseDto">PaytmSubscriptionCreationResponseDto</h2>

<a id="schemapaytmsubscriptioncreationresponsedto"></a>
<a id="schema_PaytmSubscriptionCreationResponseDto"></a>
<a id="tocSpaytmsubscriptioncreationresponsedto"></a>
<a id="tocspaytmsubscriptioncreationresponsedto"></a>

```json
{
  "paytmTokenResponseDto": {
    "txnToken": "string",
    "subscriptionId": "string",
    "orderId": "string",
    "amount": 0,
    "creationTime": 0,
    "tokenType": "string"
  },
  "mandateDetailResponseDto": {
    "maximumAmount": 0,
    "authType": "upi",
    "firstCollectionDate": "string",
    "finalCollectionDate": "string",
    "frequency": "Adhoc",
    "customerIdentifier": "string",
    "customerRefNumber": "string",
    "schemeRefNumber": "string",
    "recurring": true
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|paytmTokenResponseDto|[PaytmTokenResponseDto](#schemapaytmtokenresponsedto)|false|none|none|
|mandateDetailResponseDto|[CreatedMandateDetailResponseDto](#schemacreatedmandatedetailresponsedto)|false|none|none|

<h2 id="tocS_PaytmTokenResponseDto">PaytmTokenResponseDto</h2>

<a id="schemapaytmtokenresponsedto"></a>
<a id="schema_PaytmTokenResponseDto"></a>
<a id="tocSpaytmtokenresponsedto"></a>
<a id="tocspaytmtokenresponsedto"></a>

```json
{
  "txnToken": "string",
  "subscriptionId": "string",
  "orderId": "string",
  "amount": 0,
  "creationTime": 0,
  "tokenType": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|txnToken|string|false|none|none|
|subscriptionId|string|false|none|none|
|orderId|string|false|none|none|
|amount|number|false|none|none|
|creationTime|integer(int64)|false|none|none|
|tokenType|string|false|none|none|

<h2 id="tocS_CancelSubscriptionResponseBodyDto">CancelSubscriptionResponseBodyDto</h2>

<a id="schemacancelsubscriptionresponsebodydto"></a>
<a id="schema_CancelSubscriptionResponseBodyDto"></a>
<a id="tocScancelsubscriptionresponsebodydto"></a>
<a id="tocscancelsubscriptionresponsebodydto"></a>

```json
{
  "resultInfo": {
    "status": "SUCCESS",
    "code": "string",
    "message": "string"
  },
  "mid": "string",
  "subsId": "string",
  "custId": "string",
  "createdDate": "string",
  "expiryDate": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|resultInfo|[CancelSubscriptionResultInfoResponseDto](#schemacancelsubscriptionresultinforesponsedto)|false|none|none|
|mid|string|false|none|none|
|subsId|string|false|none|none|
|custId|string|false|none|none|
|createdDate|string|false|none|none|
|expiryDate|string|false|none|none|

<h2 id="tocS_CancelSubscriptionResponseDto">CancelSubscriptionResponseDto</h2>

<a id="schemacancelsubscriptionresponsedto"></a>
<a id="schema_CancelSubscriptionResponseDto"></a>
<a id="tocScancelsubscriptionresponsedto"></a>
<a id="tocscancelsubscriptionresponsedto"></a>

```json
{
  "head": {
    "responseTimestamp": "string",
    "signature": "string"
  },
  "body": {
    "resultInfo": {
      "status": "SUCCESS",
      "code": "string",
      "message": "string"
    },
    "mid": "string",
    "subsId": "string",
    "custId": "string",
    "createdDate": "string",
    "expiryDate": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|head|[CancelSubscriptionResponseHeadDto](#schemacancelsubscriptionresponseheaddto)|false|none|none|
|body|[CancelSubscriptionResponseBodyDto](#schemacancelsubscriptionresponsebodydto)|false|none|none|

<h2 id="tocS_CancelSubscriptionResponseHeadDto">CancelSubscriptionResponseHeadDto</h2>

<a id="schemacancelsubscriptionresponseheaddto"></a>
<a id="schema_CancelSubscriptionResponseHeadDto"></a>
<a id="tocScancelsubscriptionresponseheaddto"></a>
<a id="tocscancelsubscriptionresponseheaddto"></a>

```json
{
  "responseTimestamp": "string",
  "signature": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|responseTimestamp|string|false|none|none|
|signature|string|false|none|none|

<h2 id="tocS_CancelSubscriptionResultInfoResponseDto">CancelSubscriptionResultInfoResponseDto</h2>

<a id="schemacancelsubscriptionresultinforesponsedto"></a>
<a id="schema_CancelSubscriptionResultInfoResponseDto"></a>
<a id="tocScancelsubscriptionresultinforesponsedto"></a>
<a id="tocscancelsubscriptionresultinforesponsedto"></a>

```json
{
  "status": "SUCCESS",
  "code": "string",
  "message": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|status|string|false|none|none|
|code|string|false|none|none|
|message|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|SUCCESS|
|status|FAILURE|

<h2 id="tocS_OneTimePaymentResponseDto">OneTimePaymentResponseDto</h2>

<a id="schemaonetimepaymentresponsedto"></a>
<a id="schema_OneTimePaymentResponseDto"></a>
<a id="tocSonetimepaymentresponsedto"></a>
<a id="tocsonetimepaymentresponsedto"></a>

```json
{
  "orderId": "string",
  "externalTransactionId": "string",
  "bankTransactionId": "string",
  "schemeReference": "string",
  "amount": 0,
  "transactionType": "string",
  "creationTime": 0,
  "paymentChannel": "PAYTM",
  "paymentMode": "PPI",
  "paymentTime": "2019-08-24T14:15:22Z",
  "transactionStatus": "CREATED",
  "customerRefNumber": "string",
  "paidAmount": 0,
  "planType": "BASIC",
  "expiryDate": "2019-08-24",
  "mandateFrequency": "Adhoc"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|orderId|string|false|none|none|
|externalTransactionId|string|false|none|none|
|bankTransactionId|string|false|none|none|
|schemeReference|string|false|none|none|
|amount|number|false|none|none|
|transactionType|string|false|none|none|
|creationTime|integer(int64)|false|none|none|
|paymentChannel|string|false|none|none|
|paymentMode|string|false|none|none|
|paymentTime|string(date-time)|false|none|none|
|transactionStatus|string|false|none|none|
|customerRefNumber|string|false|none|none|
|paidAmount|number|false|none|none|
|planType|string|false|none|none|
|expiryDate|string(date)|false|none|none|
|mandateFrequency|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|paymentChannel|PAYTM|
|paymentChannel|DIGIO|
|paymentChannel|PAYTM_CHECKOUT|
|paymentChannel|PAYTM_INTEGRATED|
|paymentChannel|BROKER_TIE_UP|
|paymentMode|PPI|
|paymentMode|CC|
|paymentMode|DB|
|paymentMode|NB|
|paymentMode|UPI|
|paymentMode|DC|
|transactionStatus|CREATED|
|transactionStatus|FAILED|
|transactionStatus|SUCCESS|
|planType|BASIC|
|planType|PROFESSIONAL|
|planType|POWER_USER|
|planType|FREE|
|planType|EXPIRED|
|mandateFrequency|Adhoc|
|mandateFrequency|Daily|
|mandateFrequency|Weekly|
|mandateFrequency|Monthly|
|mandateFrequency|BiMonthly|
|mandateFrequency|Quarterly|
|mandateFrequency|Semiannually|
|mandateFrequency|Yearly|

<h2 id="tocS_OneTimePaymentCreationResponseDto">OneTimePaymentCreationResponseDto</h2>

<a id="schemaonetimepaymentcreationresponsedto"></a>
<a id="schema_OneTimePaymentCreationResponseDto"></a>
<a id="tocSonetimepaymentcreationresponsedto"></a>
<a id="tocsonetimepaymentcreationresponsedto"></a>

```json
{
  "paytmTokenResponseDto": {
    "txnToken": "string",
    "subscriptionId": "string",
    "orderId": "string",
    "amount": 0,
    "creationTime": 0,
    "tokenType": "string"
  },
  "oneTimePaymentResponseDto": {
    "orderId": "string",
    "externalTransactionId": "string",
    "bankTransactionId": "string",
    "schemeReference": "string",
    "amount": 0,
    "transactionType": "string",
    "creationTime": 0,
    "paymentChannel": "PAYTM",
    "paymentMode": "PPI",
    "paymentTime": "2019-08-24T14:15:22Z",
    "transactionStatus": "CREATED",
    "customerRefNumber": "string",
    "paidAmount": 0,
    "planType": "BASIC",
    "expiryDate": "2019-08-24",
    "mandateFrequency": "Adhoc"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|paytmTokenResponseDto|[PaytmTokenResponseDto](#schemapaytmtokenresponsedto)|false|none|none|
|oneTimePaymentResponseDto|[OneTimePaymentResponseDto](#schemaonetimepaymentresponsedto)|false|none|none|

<h2 id="tocS_MandateCreationRequestDto">MandateCreationRequestDto</h2>

<a id="schemamandatecreationrequestdto"></a>
<a id="schema_MandateCreationRequestDto"></a>
<a id="tocSmandatecreationrequestdto"></a>
<a id="tocsmandatecreationrequestdto"></a>

```json
{
  "vpa": "string",
  "plan": "BASIC",
  "frequency": "MONTHLY",
  "discountCode": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|vpa|string|true|none|none|
|plan|string|true|none|none|
|frequency|string|true|none|none|
|discountCode|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|plan|BASIC|
|plan|PROFESSIONAL|
|plan|POWER_USER|
|plan|FREE|
|plan|EXPIRED|
|frequency|MONTHLY|
|frequency|YEARLY|

<h2 id="tocS_DigioAccessTokenResponseDto">DigioAccessTokenResponseDto</h2>

<a id="schemadigioaccesstokenresponsedto"></a>
<a id="schema_DigioAccessTokenResponseDto"></a>
<a id="tocSdigioaccesstokenresponsedto"></a>
<a id="tocsdigioaccesstokenresponsedto"></a>

```json
{
  "createdAt": "string",
  "id": "string",
  "entityId": "string",
  "validTill": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|createdAt|string|false|none|none|
|id|string|false|none|none|
|entityId|string|false|none|none|
|validTill|string|false|none|none|

<h2 id="tocS_MandateCreationResponseDto">MandateCreationResponseDto</h2>

<a id="schemamandatecreationresponsedto"></a>
<a id="schema_MandateCreationResponseDto"></a>
<a id="tocSmandatecreationresponsedto"></a>
<a id="tocsmandatecreationresponsedto"></a>

```json
{
  "mandateDetailResponseDto": {
    "maximumAmount": 0,
    "authType": "upi",
    "firstCollectionDate": "string",
    "finalCollectionDate": "string",
    "frequency": "Adhoc",
    "customerIdentifier": "string",
    "customerRefNumber": "string",
    "schemeRefNumber": "string",
    "recurring": true
  },
  "accessTokenResponseDto": {
    "createdAt": "string",
    "id": "string",
    "entityId": "string",
    "validTill": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|mandateDetailResponseDto|[CreatedMandateDetailResponseDto](#schemacreatedmandatedetailresponsedto)|false|none|none|
|accessTokenResponseDto|[DigioAccessTokenResponseDto](#schemadigioaccesstokenresponsedto)|false|none|none|

<h2 id="tocS_DigioMandateCreationSuccessPostbackRequestDto">DigioMandateCreationSuccessPostbackRequestDto</h2>

<a id="schemadigiomandatecreationsuccesspostbackrequestdto"></a>
<a id="schema_DigioMandateCreationSuccessPostbackRequestDto"></a>
<a id="tocSdigiomandatecreationsuccesspostbackrequestdto"></a>
<a id="tocsdigiomandatecreationsuccesspostbackrequestdto"></a>

```json
{
  "txn_id": "string",
  "digio_doc_id": "string",
  "message": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|txn_id|string|false|none|none|
|digio_doc_id|string|false|none|none|
|message|string|false|none|none|

<h2 id="tocS_ExternalPaymentCreationRequestDto">ExternalPaymentCreationRequestDto</h2>

<a id="schemaexternalpaymentcreationrequestdto"></a>
<a id="schema_ExternalPaymentCreationRequestDto"></a>
<a id="tocSexternalpaymentcreationrequestdto"></a>
<a id="tocsexternalpaymentcreationrequestdto"></a>

```json
{
  "userId": "string",
  "amountPaid": 0,
  "destinationPlanType": "TRIAL",
  "paymentTime": "2019-08-24T14:15:22Z",
  "paymentId": "string",
  "planId": "string",
  "transactionId": "string",
  "expiryDate": "2019-08-24",
  "channel": "PAYTM",
  "duration": "Adhoc"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|userId|string|true|none|none|
|amountPaid|number|true|none|none|
|destinationPlanType|string|true|none|none|
|paymentTime|string(date-time)|true|none|none|
|paymentId|string|true|none|none|
|planId|string|true|none|none|
|transactionId|string|false|none|none|
|expiryDate|string(date)|true|none|none|
|channel|string|true|none|none|
|duration|string|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|destinationPlanType|TRIAL|
|destinationPlanType|TRIAL_EXPIRED|
|destinationPlanType|PAID_BASIC|
|destinationPlanType|PAID_PROFESSIONAL|
|destinationPlanType|PAID_POWER_USER|
|destinationPlanType|TRIAL_BASIC|
|destinationPlanType|TRIAL_PROFESSIONAL|
|destinationPlanType|TRIAL_POWER_USER|
|destinationPlanType|FREE|
|channel|PAYTM|
|channel|DIGIO|
|channel|PAYTM_CHECKOUT|
|channel|PAYTM_INTEGRATED|
|channel|BROKER_TIE_UP|
|duration|Adhoc|
|duration|Daily|
|duration|Weekly|
|duration|Monthly|
|duration|BiMonthly|
|duration|Quarterly|
|duration|Semiannually|
|duration|Yearly|

<h2 id="tocS_ExternalPaymentResponseDto">ExternalPaymentResponseDto</h2>

<a id="schemaexternalpaymentresponsedto"></a>
<a id="schema_ExternalPaymentResponseDto"></a>
<a id="tocSexternalpaymentresponsedto"></a>
<a id="tocsexternalpaymentresponsedto"></a>

```json
{
  "id": 0,
  "userId": 0,
  "externalPaymentId": "string",
  "externalOrderId": "string",
  "amount": 0,
  "creationTime": 0,
  "paymentDateTime": "2019-08-24T14:15:22Z",
  "expiryDate": "2019-08-24",
  "paymentChannel": "PAYTM",
  "duration": "Adhoc",
  "destinationPlanType": "TRIAL",
  "previousUserPlan": "TRIAL"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer(int64)|false|none|none|
|userId|integer(int64)|false|none|none|
|externalPaymentId|string|false|none|none|
|externalOrderId|string|false|none|none|
|amount|number|false|none|none|
|creationTime|integer(int64)|false|none|none|
|paymentDateTime|string(date-time)|false|none|none|
|expiryDate|string(date)|false|none|none|
|paymentChannel|string|false|none|none|
|duration|string|false|none|none|
|destinationPlanType|string|false|none|none|
|previousUserPlan|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|paymentChannel|PAYTM|
|paymentChannel|DIGIO|
|paymentChannel|PAYTM_CHECKOUT|
|paymentChannel|PAYTM_INTEGRATED|
|paymentChannel|BROKER_TIE_UP|
|duration|Adhoc|
|duration|Daily|
|duration|Weekly|
|duration|Monthly|
|duration|BiMonthly|
|duration|Quarterly|
|duration|Semiannually|
|duration|Yearly|
|destinationPlanType|TRIAL|
|destinationPlanType|TRIAL_EXPIRED|
|destinationPlanType|PAID_BASIC|
|destinationPlanType|PAID_PROFESSIONAL|
|destinationPlanType|PAID_POWER_USER|
|destinationPlanType|TRIAL_BASIC|
|destinationPlanType|TRIAL_PROFESSIONAL|
|destinationPlanType|TRIAL_POWER_USER|
|destinationPlanType|FREE|
|previousUserPlan|TRIAL|
|previousUserPlan|TRIAL_EXPIRED|
|previousUserPlan|PAID_BASIC|
|previousUserPlan|PAID_PROFESSIONAL|
|previousUserPlan|PAID_POWER_USER|
|previousUserPlan|TRIAL_BASIC|
|previousUserPlan|TRIAL_PROFESSIONAL|
|previousUserPlan|TRIAL_POWER_USER|
|previousUserPlan|FREE|

<h2 id="tocS_AudioTranslationRequestDto">AudioTranslationRequestDto</h2>

<a id="schemaaudiotranslationrequestdto"></a>
<a id="schema_AudioTranslationRequestDto"></a>
<a id="tocSaudiotranslationrequestdto"></a>
<a id="tocsaudiotranslationrequestdto"></a>

```json
{
  "id": "string",
  "base64File": "string",
  "fileName": "string",
  "prompt": "string",
  "model": "string",
  "fileUrl": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|none|none|
|base64File|string|false|none|none|
|fileName|string|false|none|none|
|prompt|string|false|none|none|
|model|string|false|none|none|
|fileUrl|string|false|none|none|

<h2 id="tocS_OtpDTO">OtpDTO</h2>

<a id="schemaotpdto"></a>
<a id="schema_OtpDTO"></a>
<a id="tocSotpdto"></a>
<a id="tocsotpdto"></a>

```json
{
  "otp": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|otp|integer(int32)|true|none|none|

<h2 id="tocS_DiscountMessageSurveySurveyTriggerRequestDto">DiscountMessageSurveySurveyTriggerRequestDto</h2>

<a id="schemadiscountmessagesurveysurveytriggerrequestdto"></a>
<a id="schema_DiscountMessageSurveySurveyTriggerRequestDto"></a>
<a id="tocSdiscountmessagesurveysurveytriggerrequestdto"></a>
<a id="tocsdiscountmessagesurveysurveytriggerrequestdto"></a>

```json
{
  "userId": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|userId|string|false|none|none|

<h2 id="tocS_CumulativeDiscountReminderMessageRequest">CumulativeDiscountReminderMessageRequest</h2>

<a id="schemacumulativediscountremindermessagerequest"></a>
<a id="schema_CumulativeDiscountReminderMessageRequest"></a>
<a id="tocScumulativediscountremindermessagerequest"></a>
<a id="tocscumulativediscountremindermessagerequest"></a>

```json
{
  "userId": [
    0
  ],
  "startTime": "2019-08-24T14:15:22Z",
  "endTime": "2019-08-24T14:15:22Z",
  "noOfTimesRemindersToBeSent": 0,
  "reminderTimes": [
    "2019-08-24T14:15:22Z"
  ],
  "templateId": "string",
  "bodyValues": [
    "string"
  ],
  "appendCtaValue": "string",
  "headerValue": "string",
  "headerType": "string",
  "initiationType": "IMMEDIATE",
  "surveyName": "TRIAL_USER_FEEDBACK"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|userId|[integer]|true|none|none|
|startTime|string(date-time)|true|none|none|
|endTime|string(date-time)|true|none|none|
|noOfTimesRemindersToBeSent|integer(int32)|true|none|none|
|reminderTimes|[string]|true|none|none|
|templateId|string|true|none|none|
|bodyValues|[string]|true|none|none|
|appendCtaValue|string|true|none|none|
|headerValue|string|false|none|none|
|headerType|string|false|none|none|
|initiationType|string|true|none|none|
|surveyName|string|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|initiationType|IMMEDIATE|
|initiationType|SCHEDULED|
|surveyName|TRIAL_USER_FEEDBACK|
|surveyName|CONVERT_TRIAL_TO_PAID_SURVEY_CASUAL|
|surveyName|CONVERT_TRIAL_TO_PAID_SURVEY_CORPORATE|
|surveyName|FLASH_SALE|
|surveyName|FESTIVE_DISCOUNT|

<h2 id="tocS_CumulativeReminderMessageResponse">CumulativeReminderMessageResponse</h2>

<a id="schemacumulativeremindermessageresponse"></a>
<a id="schema_CumulativeReminderMessageResponse"></a>
<a id="tocScumulativeremindermessageresponse"></a>
<a id="tocscumulativeremindermessageresponse"></a>

```json
{
  "totalRequests": 0,
  "successCount": 0,
  "failureCount": 0,
  "failedReasons": {
    "property1": "string",
    "property2": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|totalRequests|integer(int32)|false|none|none|
|successCount|integer(int32)|false|none|none|
|failureCount|integer(int32)|false|none|none|
|failedReasons|object|false|none|none|
|» **additionalProperties**|string|false|none|none|

<h2 id="tocS_MarketingRequestUserIdListDto">MarketingRequestUserIdListDto</h2>

<a id="schemamarketingrequestuseridlistdto"></a>
<a id="schema_MarketingRequestUserIdListDto"></a>
<a id="tocSmarketingrequestuseridlistdto"></a>
<a id="tocsmarketingrequestuseridlistdto"></a>

```json
{
  "userIds": [
    0
  ],
  "heading": "string",
  "plan": "string",
  "validity": "string",
  "templateId": "string",
  "chatLink": "string",
  "redirectionLink": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|userIds|[integer]|false|none|none|
|heading|string|false|none|none|
|plan|string|false|none|none|
|validity|string|false|none|none|
|templateId|string|false|none|none|
|chatLink|string|false|none|none|
|redirectionLink|string|false|none|none|

<h2 id="tocS_MarketingResponseDto">MarketingResponseDto</h2>

<a id="schemamarketingresponsedto"></a>
<a id="schema_MarketingResponseDto"></a>
<a id="tocSmarketingresponsedto"></a>
<a id="tocsmarketingresponsedto"></a>

```json
{
  "successCount": 0,
  "failureCount": 0,
  "failureDetails": {
    "property1": "string",
    "property2": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|successCount|integer(int32)|false|none|none|
|failureCount|integer(int32)|false|none|none|
|failureDetails|object|false|none|none|
|» **additionalProperties**|string|false|none|none|

<h2 id="tocS_InstrumentDetailRequestDto">InstrumentDetailRequestDto</h2>

<a id="schemainstrumentdetailrequestdto"></a>
<a id="schema_InstrumentDetailRequestDto"></a>
<a id="tocSinstrumentdetailrequestdto"></a>
<a id="tocsinstrumentdetailrequestdto"></a>

```json
{
  "isin": "string",
  "tickr": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isin|string|true|none|none|
|tickr|string|true|none|none|

<h2 id="tocS_UpdateUserStockSubscriptionRequestDto">UpdateUserStockSubscriptionRequestDto</h2>

<a id="schemaupdateuserstocksubscriptionrequestdto"></a>
<a id="schema_UpdateUserStockSubscriptionRequestDto"></a>
<a id="tocSupdateuserstocksubscriptionrequestdto"></a>
<a id="tocsupdateuserstocksubscriptionrequestdto"></a>

```json
{
  "instruments": [
    {
      "isin": "string",
      "tickr": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|instruments|[[InstrumentDetailRequestDto](#schemainstrumentdetailrequestdto)]|true|none|none|

<h2 id="tocS_TrackInstrumentsUpdateResponseDto">TrackInstrumentsUpdateResponseDto</h2>

<a id="schematrackinstrumentsupdateresponsedto"></a>
<a id="schema_TrackInstrumentsUpdateResponseDto"></a>
<a id="tocStrackinstrumentsupdateresponsedto"></a>
<a id="tocstrackinstrumentsupdateresponsedto"></a>

```json
{
  "currentTrackedInstruments": [
    {
      "subscriptionId": 0,
      "isin": "string",
      "tickr": "string",
      "name": "string",
      "source": "MANUAL"
    }
  ],
  "newErrorIsin": [
    "string"
  ],
  "inactiveErrorIsin": [
    "string"
  ],
  "newErrorIsinCount": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|currentTrackedInstruments|[[TrackedInstrumentsResponseDto](#schematrackedinstrumentsresponsedto)]|false|none|none|
|newErrorIsin|[string]|false|none|none|
|inactiveErrorIsin|[string]|false|none|none|
|newErrorIsinCount|integer(int32)|false|none|none|

<h2 id="tocS_TrackedInstrumentsResponseDto">TrackedInstrumentsResponseDto</h2>

<a id="schematrackedinstrumentsresponsedto"></a>
<a id="schema_TrackedInstrumentsResponseDto"></a>
<a id="tocStrackedinstrumentsresponsedto"></a>
<a id="tocstrackedinstrumentsresponsedto"></a>

```json
{
  "subscriptionId": 0,
  "isin": "string",
  "tickr": "string",
  "name": "string",
  "source": "MANUAL"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|subscriptionId|integer(int64)|true|none|none|
|isin|string|true|none|none|
|tickr|string|true|none|none|
|name|string|true|none|none|
|source|string|true|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|source|MANUAL|
|source|GATEWAY|
|source|CAS|
|source|HOLDINGPARSER|

<h2 id="tocS_CompanyNameLookupBuildStatistic">CompanyNameLookupBuildStatistic</h2>

<a id="schemacompanynamelookupbuildstatistic"></a>
<a id="schema_CompanyNameLookupBuildStatistic"></a>
<a id="tocScompanynamelookupbuildstatistic"></a>
<a id="tocscompanynamelookupbuildstatistic"></a>

```json
{
  "companiesSize": 0,
  "treeSize": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|companiesSize|integer(int32)|false|none|none|
|treeSize|integer(int32)|false|none|none|

<h2 id="tocS_FileImportBhavCopyReport">FileImportBhavCopyReport</h2>

<a id="schemafileimportbhavcopyreport"></a>
<a id="schema_FileImportBhavCopyReport"></a>
<a id="tocSfileimportbhavcopyreport"></a>
<a id="tocsfileimportbhavcopyreport"></a>

```json
{
  "errors": {
    "property1": "string",
    "property2": "string"
  },
  "successSize": 0,
  "errorSize": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|errors|object|false|none|none|
|» **additionalProperties**|string|false|none|none|
|successSize|integer(int32)|false|none|none|
|errorSize|integer(int32)|false|none|none|

<h2 id="tocS_FileImportDataDto">FileImportDataDto</h2>

<a id="schemafileimportdatadto"></a>
<a id="schema_FileImportDataDto"></a>
<a id="tocSfileimportdatadto"></a>
<a id="tocsfileimportdatadto"></a>

```json
{
  "importedInstruments": [
    {
      "isin": "string",
      "tickr": "string",
      "bseId": 0,
      "longName": "string",
      "instrumentType": "E",
      "groupName": "string",
      "bseExclusive": "string",
      "tradingStatus": "A",
      "securityType": "EQ",
      "gsmFlag": 0
    }
  ],
  "totalSize": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|importedInstruments|[[IndividualBseInstrument](#schemaindividualbseinstrument)]|false|none|none|
|totalSize|integer(int32)|false|none|none|

<h2 id="tocS_FileImportReportDto">FileImportReportDto</h2>

<a id="schemafileimportreportdto"></a>
<a id="schema_FileImportReportDto"></a>
<a id="tocSfileimportreportdto"></a>
<a id="tocsfileimportreportdto"></a>

```json
{
  "fileImportInstruments": {
    "importedInstruments": [
      {
        "isin": "string",
        "tickr": "string",
        "bseId": 0,
        "longName": "string",
        "instrumentType": "E",
        "groupName": "string",
        "bseExclusive": "string",
        "tradingStatus": "A",
        "securityType": "EQ",
        "gsmFlag": 0
      }
    ],
    "totalSize": 0
  },
  "newInstruments": {
    "errors": [
      {
        "isin": "string",
        "tickr": "string",
        "bseId": 0,
        "longName": "string",
        "instrumentType": "E",
        "groupName": "string",
        "bseExclusive": "string",
        "tradingStatus": "A",
        "securityType": "EQ",
        "gsmFlag": 0
      }
    ],
    "success": [
      {
        "isin": "string",
        "tickr": "string",
        "bseId": 0,
        "longName": "string",
        "instrumentType": "E",
        "groupName": "string",
        "bseExclusive": "string",
        "tradingStatus": "A",
        "securityType": "EQ",
        "gsmFlag": 0
      }
    ],
    "successSize": 0,
    "errorSize": 0,
    "totalSize": 0
  },
  "inactiveInstruments": {
    "success": [
      "string"
    ],
    "errors": [
      "string"
    ],
    "successSize": 0,
    "errorSize": 0,
    "totalSize": 0
  },
  "fileImportBhavCopyReport": {
    "errors": {
      "property1": "string",
      "property2": "string"
    },
    "successSize": 0,
    "errorSize": 0
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|fileImportInstruments|[FileImportDataDto](#schemafileimportdatadto)|false|none|none|
|newInstruments|[FileImportReportIndividualActionDto](#schemafileimportreportindividualactiondto)|false|none|none|
|inactiveInstruments|[FileImportReportUpdatedInstrumentsDto](#schemafileimportreportupdatedinstrumentsdto)|false|none|none|
|fileImportBhavCopyReport|[FileImportBhavCopyReport](#schemafileimportbhavcopyreport)|false|none|none|

<h2 id="tocS_FileImportReportIndividualActionDto">FileImportReportIndividualActionDto</h2>

<a id="schemafileimportreportindividualactiondto"></a>
<a id="schema_FileImportReportIndividualActionDto"></a>
<a id="tocSfileimportreportindividualactiondto"></a>
<a id="tocsfileimportreportindividualactiondto"></a>

```json
{
  "errors": [
    {
      "isin": "string",
      "tickr": "string",
      "bseId": 0,
      "longName": "string",
      "instrumentType": "E",
      "groupName": "string",
      "bseExclusive": "string",
      "tradingStatus": "A",
      "securityType": "EQ",
      "gsmFlag": 0
    }
  ],
  "success": [
    {
      "isin": "string",
      "tickr": "string",
      "bseId": 0,
      "longName": "string",
      "instrumentType": "E",
      "groupName": "string",
      "bseExclusive": "string",
      "tradingStatus": "A",
      "securityType": "EQ",
      "gsmFlag": 0
    }
  ],
  "successSize": 0,
  "errorSize": 0,
  "totalSize": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|errors|[[IndividualBseInstrument](#schemaindividualbseinstrument)]|false|none|none|
|success|[[IndividualBseInstrument](#schemaindividualbseinstrument)]|false|none|none|
|successSize|integer(int32)|false|none|none|
|errorSize|integer(int32)|false|none|none|
|totalSize|integer(int32)|false|none|none|

<h2 id="tocS_FileImportReportUpdatedInstrumentsDto">FileImportReportUpdatedInstrumentsDto</h2>

<a id="schemafileimportreportupdatedinstrumentsdto"></a>
<a id="schema_FileImportReportUpdatedInstrumentsDto"></a>
<a id="tocSfileimportreportupdatedinstrumentsdto"></a>
<a id="tocsfileimportreportupdatedinstrumentsdto"></a>

```json
{
  "success": [
    "string"
  ],
  "errors": [
    "string"
  ],
  "successSize": 0,
  "errorSize": 0,
  "totalSize": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|success|[string]|false|none|none|
|errors|[string]|false|none|none|
|successSize|integer(int32)|false|none|none|
|errorSize|integer(int32)|false|none|none|
|totalSize|integer(int32)|false|none|none|

<h2 id="tocS_IndividualBseInstrument">IndividualBseInstrument</h2>

<a id="schemaindividualbseinstrument"></a>
<a id="schema_IndividualBseInstrument"></a>
<a id="tocSindividualbseinstrument"></a>
<a id="tocsindividualbseinstrument"></a>

```json
{
  "isin": "string",
  "tickr": "string",
  "bseId": 0,
  "longName": "string",
  "instrumentType": "E",
  "groupName": "string",
  "bseExclusive": "string",
  "tradingStatus": "A",
  "securityType": "EQ",
  "gsmFlag": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isin|string|false|none|none|
|tickr|string|false|none|none|
|bseId|integer(int32)|false|none|none|
|longName|string|false|none|none|
|instrumentType|string|false|none|none|
|groupName|string|false|none|none|
|bseExclusive|string|false|none|none|
|tradingStatus|string|false|none|none|
|securityType|string|false|none|none|
|gsmFlag|integer(int32)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|instrumentType|E|
|instrumentType|D|
|instrumentType|C|
|tradingStatus|A|
|tradingStatus|S|
|tradingStatus|I|
|securityType|EQ|
|securityType|MF|
|securityType|DB|
|securityType|GS|
|securityType|NA|

<h2 id="tocS_UserInstrumentFileUploadResponseDto">UserInstrumentFileUploadResponseDto</h2>

<a id="schemauserinstrumentfileuploadresponsedto"></a>
<a id="schema_UserInstrumentFileUploadResponseDto"></a>
<a id="tocSuserinstrumentfileuploadresponsedto"></a>
<a id="tocsuserinstrumentfileuploadresponsedto"></a>

```json
{
  "totalIsinInFile": 0,
  "errorIsin": 0,
  "newErrorIsin": [
    "string"
  ],
  "inactiveErrorIsin": [
    "string"
  ],
  "mode": "APPEND"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|totalIsinInFile|integer(int32)|false|none|none|
|errorIsin|integer(int32)|false|none|none|
|newErrorIsin|[string]|false|none|none|
|inactiveErrorIsin|[string]|false|none|none|
|mode|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|mode|APPEND|
|mode|REPLACE|

<h2 id="tocS_ConsolidatedImportedHoldingsFromHoldingAIParseImportResponseDto">ConsolidatedImportedHoldingsFromHoldingAIParseImportResponseDto</h2>

<a id="schemaconsolidatedimportedholdingsfromholdingaiparseimportresponsedto"></a>
<a id="schema_ConsolidatedImportedHoldingsFromHoldingAIParseImportResponseDto"></a>
<a id="tocSconsolidatedimportedholdingsfromholdingaiparseimportresponsedto"></a>
<a id="tocsconsolidatedimportedholdingsfromholdingaiparseimportresponsedto"></a>

```json
{
  "requestId": "string",
  "importActivityId": "string",
  "identifiedHoldings": [
    "string"
  ],
  "totalIdentifiedHoldings": 0,
  "totalSuccessImportedHoldings": 0,
  "totalErrorImportedHoldings": 0,
  "errorInstruments": [
    {
      "instrument": "string",
      "error": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|requestId|string|false|none|none|
|importActivityId|string|false|none|none|
|identifiedHoldings|[string]|false|none|none|
|totalIdentifiedHoldings|integer(int32)|false|none|none|
|totalSuccessImportedHoldings|integer(int32)|false|none|none|
|totalErrorImportedHoldings|integer(int32)|false|none|none|
|errorInstruments|[[ErrorInstrumentDetailResponseDto](#schemaerrorinstrumentdetailresponsedto)]|false|none|none|

<h2 id="tocS_ErrorInstrumentDetailResponseDto">ErrorInstrumentDetailResponseDto</h2>

<a id="schemaerrorinstrumentdetailresponsedto"></a>
<a id="schema_ErrorInstrumentDetailResponseDto"></a>
<a id="tocSerrorinstrumentdetailresponsedto"></a>
<a id="tocserrorinstrumentdetailresponsedto"></a>

```json
{
  "instrument": "string",
  "error": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|instrument|string|false|none|none|
|error|string|false|none|none|

<h2 id="tocS_CorporateData">CorporateData</h2>

<a id="schemacorporatedata"></a>
<a id="schema_CorporateData"></a>
<a id="tocScorporatedata"></a>
<a id="tocscorporatedata"></a>

```json
{
  "name": "string",
  "subIndustries": "string",
  "website": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|false|none|none|
|subIndustries|string|false|none|none|
|website|string|false|none|none|

<h2 id="tocS_ImportReport">ImportReport</h2>

<a id="schemaimportreport"></a>
<a id="schema_ImportReport"></a>
<a id="tocSimportreport"></a>
<a id="tocsimportreport"></a>

```json
{
  "corporateDataErrorList": [
    {
      "name": "string",
      "subIndustries": "string",
      "website": "string"
    }
  ],
  "successImports": [
    "string"
  ],
  "totalEntries": 0,
  "success": 0,
  "errors": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|corporateDataErrorList|[[CorporateData](#schemacorporatedata)]|false|none|none|
|successImports|[string]|false|none|none|
|totalEntries|integer(int32)|false|none|none|
|success|integer(int32)|false|none|none|
|errors|integer(int32)|false|none|none|

<h2 id="tocS_CasUploadResponseDto">CasUploadResponseDto</h2>

<a id="schemacasuploadresponsedto"></a>
<a id="schema_CasUploadResponseDto"></a>
<a id="tocScasuploadresponsedto"></a>
<a id="tocscasuploadresponsedto"></a>

```json
{
  "importId": "string",
  "addedStocks": 0,
  "addedAccounts": 0,
  "stocksAddedToTrackList": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|importId|string|false|none|none|
|addedStocks|integer(int32)|false|none|none|
|addedAccounts|integer(int32)|false|none|none|
|stocksAddedToTrackList|integer(int32)|false|none|none|

<h2 id="tocS_UpdateUserPreferenceRequestDto">UpdateUserPreferenceRequestDto</h2>

<a id="schemaupdateuserpreferencerequestdto"></a>
<a id="schema_UpdateUserPreferenceRequestDto"></a>
<a id="tocSupdateuserpreferencerequestdto"></a>
<a id="tocsupdateuserpreferencerequestdto"></a>

```json
{
  "stopUserNotification": true,
  "sessionId": "string",
  "mobileNo": 0,
  "countryCode": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|stopUserNotification|boolean|false|none|none|
|sessionId|string|false|none|none|
|mobileNo|integer(int64)|false|none|none|
|countryCode|integer(int32)|false|none|none|

<h2 id="tocS_UserLookupResponseDto">UserLookupResponseDto</h2>

<a id="schemauserlookupresponsedto"></a>
<a id="schema_UserLookupResponseDto"></a>
<a id="tocSuserlookupresponsedto"></a>
<a id="tocsuserlookupresponsedto"></a>

```json
{
  "sessionId": "string",
  "userId": 0,
  "signupStatus": "NEW",
  "countryCode": "string",
  "mobileNo": 0,
  "previouslyUserIsActive": true,
  "currentlyUserIsActive": true,
  "token": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|sessionId|string|false|none|none|
|userId|integer(int64)|false|none|none|
|signupStatus|string|false|none|none|
|countryCode|string|false|none|none|
|mobileNo|integer(int64)|false|none|none|
|previouslyUserIsActive|boolean|false|none|none|
|currentlyUserIsActive|boolean|false|none|none|
|token|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|signupStatus|NEW|
|signupStatus|EXISTING|

<h2 id="tocS_UserLookupRequestDto">UserLookupRequestDto</h2>

<a id="schemauserlookuprequestdto"></a>
<a id="schema_UserLookupRequestDto"></a>
<a id="tocSuserlookuprequestdto"></a>
<a id="tocsuserlookuprequestdto"></a>

```json
{
  "countryCode": 0,
  "mobileNo": 0,
  "source": "string",
  "name": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|countryCode|integer(int32)|true|none|none|
|mobileNo|integer(int64)|true|none|none|
|source|string|false|none|none|
|name|string|false|none|none|

<h2 id="tocS_BrokeUserSignupRequestDto">BrokeUserSignupRequestDto</h2>

<a id="schemabrokeusersignuprequestdto"></a>
<a id="schema_BrokeUserSignupRequestDto"></a>
<a id="tocSbrokeusersignuprequestdto"></a>
<a id="tocsbrokeusersignuprequestdto"></a>

```json
{
  "countryCode": 0,
  "mobileNo": 0,
  "source": "string",
  "name": "string",
  "brokerName": "string",
  "holdingFetchConsent": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|countryCode|integer(int32)|true|none|none|
|mobileNo|integer(int64)|true|none|none|
|source|string|false|none|none|
|name|string|false|none|none|
|brokerName|string|false|none|none|
|holdingFetchConsent|boolean|false|none|none|

<h2 id="tocS_UserPaidShiftSurveyResponseDto">UserPaidShiftSurveyResponseDto</h2>

<a id="schemauserpaidshiftsurveyresponsedto"></a>
<a id="schema_UserPaidShiftSurveyResponseDto"></a>
<a id="tocSuserpaidshiftsurveyresponsedto"></a>
<a id="tocsuserpaidshiftsurveyresponsedto"></a>

```json
{
  "sessionId": "string",
  "userId": 0,
  "mobileNo": 0,
  "countryCode": 0,
  "responseTime": 0,
  "vendorResponseTime": "string",
  "response": "UPGRADE_NOW"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|sessionId|string|false|none|none|
|userId|integer(int64)|false|none|none|
|mobileNo|integer(int64)|false|none|none|
|countryCode|integer(int64)|false|none|none|
|responseTime|integer(int64)|false|none|none|
|vendorResponseTime|string|false|none|none|
|response|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|response|UPGRADE_NOW|
|response|DONT_UPGRADE|
|response|PAYMENT_ISSUE|
|response|PRICE_TOO_HIGH|
|response|NOT_USEFUL|
|response|OTHER_ISSUE|
|response|FREE_TRIAL_START|
|response|UPGRADE_AFTER_FREE_TRIAL_EXTENSION|
|response|STOP_AFTER_FREE_TRIAL_EXTENSION|

<h2 id="tocS_TrialUserFeedBackSurveyChannelRequestDto">TrialUserFeedBackSurveyChannelRequestDto</h2>

<a id="schematrialuserfeedbacksurveychannelrequestdto"></a>
<a id="schema_TrialUserFeedBackSurveyChannelRequestDto"></a>
<a id="tocStrialuserfeedbacksurveychannelrequestdto"></a>
<a id="tocstrialuserfeedbacksurveychannelrequestdto"></a>

```json
{
  "sessionId": "string",
  "userId": 0,
  "mobileNo": 0,
  "countryCode": 0,
  "responseTime": 0,
  "vendorResponseTime": "string",
  "channel": "TWITTER"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|sessionId|string|false|none|none|
|userId|integer(int64)|false|none|none|
|mobileNo|integer(int64)|false|none|none|
|countryCode|integer(int64)|false|none|none|
|responseTime|integer(int64)|false|none|none|
|vendorResponseTime|string|false|none|none|
|channel|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|channel|TWITTER|
|channel|WHATSAPP|

<h2 id="tocS_TrialUserFeedBackSurveyInitialResponseRequestDto">TrialUserFeedBackSurveyInitialResponseRequestDto</h2>

<a id="schematrialuserfeedbacksurveyinitialresponserequestdto"></a>
<a id="schema_TrialUserFeedBackSurveyInitialResponseRequestDto"></a>
<a id="tocStrialuserfeedbacksurveyinitialresponserequestdto"></a>
<a id="tocstrialuserfeedbacksurveyinitialresponserequestdto"></a>

```json
{
  "sessionId": "string",
  "userId": 0,
  "mobileNo": 0,
  "countryCode": 0,
  "responseTime": 0,
  "vendorResponseTime": "string",
  "isSqHelpful": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|sessionId|string|false|none|none|
|userId|integer(int64)|false|none|none|
|mobileNo|integer(int64)|false|none|none|
|countryCode|integer(int64)|false|none|none|
|responseTime|integer(int64)|false|none|none|
|vendorResponseTime|string|false|none|none|
|isSqHelpful|boolean|false|none|none|

<h2 id="tocS_UserPrivilegeUpdateRequestDto">UserPrivilegeUpdateRequestDto</h2>

<a id="schemauserprivilegeupdaterequestdto"></a>
<a id="schema_UserPrivilegeUpdateRequestDto"></a>
<a id="tocSuserprivilegeupdaterequestdto"></a>
<a id="tocsuserprivilegeupdaterequestdto"></a>

```json
{
  "userId": "string",
  "userPrivileged": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|userId|string|true|none|none|
|userPrivileged|boolean|false|none|none|

<h2 id="tocS_UserNotesUpdateRequestDto">UserNotesUpdateRequestDto</h2>

<a id="schemausernotesupdaterequestdto"></a>
<a id="schema_UserNotesUpdateRequestDto"></a>
<a id="tocSusernotesupdaterequestdto"></a>
<a id="tocsusernotesupdaterequestdto"></a>

```json
{
  "userId": "string",
  "userType": "string",
  "companyName": "string",
  "userDesignation": "string",
  "payPotential": "string",
  "source": "string",
  "additionalNotes": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|userId|string|true|none|none|
|userType|string|false|none|none|
|companyName|string|false|none|none|
|userDesignation|string|false|none|none|
|payPotential|string|false|none|none|
|source|string|false|none|none|
|additionalNotes|string|false|none|none|

<h2 id="tocS_UserNotesResponseDto">UserNotesResponseDto</h2>

<a id="schemausernotesresponsedto"></a>
<a id="schema_UserNotesResponseDto"></a>
<a id="tocSusernotesresponsedto"></a>
<a id="tocsusernotesresponsedto"></a>

```json
{
  "userId": "string",
  "userType": "string",
  "companyName": "string",
  "userDesignation": "string",
  "payPotential": "string",
  "source": "string",
  "additionalNotes": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|userId|string|false|none|none|
|userType|string|false|none|none|
|companyName|string|false|none|none|
|userDesignation|string|false|none|none|
|payPotential|string|false|none|none|
|source|string|false|none|none|
|additionalNotes|string|false|none|none|

<h2 id="tocS_AdminUpdateUserStockSubscriptionRequestDto">AdminUpdateUserStockSubscriptionRequestDto</h2>

<a id="schemaadminupdateuserstocksubscriptionrequestdto"></a>
<a id="schema_AdminUpdateUserStockSubscriptionRequestDto"></a>
<a id="tocSadminupdateuserstocksubscriptionrequestdto"></a>
<a id="tocsadminupdateuserstocksubscriptionrequestdto"></a>

```json
{
  "instruments": [
    {
      "isin": "string",
      "tickr": "string"
    }
  ],
  "userId": "string",
  "mode": "APPEND"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|instruments|[[InstrumentDetailRequestDto](#schemainstrumentdetailrequestdto)]|true|none|none|
|userId|string|false|none|none|
|mode|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|mode|APPEND|
|mode|REPLACE|

<h2 id="tocS_AdminUserCreationRequestDto">AdminUserCreationRequestDto</h2>

<a id="schemaadminusercreationrequestdto"></a>
<a id="schema_AdminUserCreationRequestDto"></a>
<a id="tocSadminusercreationrequestdto"></a>
<a id="tocsadminusercreationrequestdto"></a>

```json
{
  "mobileNo": 0,
  "countryCode": 0,
  "name": "string",
  "source": "string",
  "referralCode": "string",
  "userPlanType": "TRIAL",
  "noOfDaysTillPlanExpiry": 0,
  "stockTrackingLimit": 0,
  "planSchemeRefId": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|mobileNo|integer(int64)|true|none|none|
|countryCode|integer(int32)|true|none|none|
|name|string|false|none|none|
|source|string|false|none|none|
|referralCode|string|false|none|none|
|userPlanType|string|false|none|none|
|noOfDaysTillPlanExpiry|integer(int32)|false|none|none|
|stockTrackingLimit|integer(int32)|false|none|none|
|planSchemeRefId|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|userPlanType|TRIAL|
|userPlanType|TRIAL_EXPIRED|
|userPlanType|PAID_BASIC|
|userPlanType|PAID_PROFESSIONAL|
|userPlanType|PAID_POWER_USER|
|userPlanType|TRIAL_BASIC|
|userPlanType|TRIAL_PROFESSIONAL|
|userPlanType|TRIAL_POWER_USER|
|userPlanType|FREE|

<h2 id="tocS_BrokerUserAccountInfoResponseDto">BrokerUserAccountInfoResponseDto</h2>

<a id="schemabrokeruseraccountinforesponsedto"></a>
<a id="schema_BrokerUserAccountInfoResponseDto"></a>
<a id="tocSbrokeruseraccountinforesponsedto"></a>
<a id="tocsbrokeruseraccountinforesponsedto"></a>

```json
{
  "id": 0,
  "clientName": "string",
  "countryCode": "string",
  "uploadRequestId": 0,
  "brokerName": "string",
  "creationTime": 0,
  "brokerId": "PMSECURITIES",
  "brokerSignupRequestId": "string",
  "userId": 0,
  "validityStatus": "VALID",
  "noOfStocks": 0,
  "value": 0,
  "importedByAdminUserId": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer(int64)|false|none|none|
|clientName|string|false|none|none|
|countryCode|string|false|none|none|
|uploadRequestId|integer(int64)|false|none|none|
|brokerName|string|false|none|none|
|creationTime|integer(int64)|false|none|none|
|brokerId|string|false|none|none|
|brokerSignupRequestId|string|false|none|none|
|userId|integer(int64)|false|none|none|
|validityStatus|string|false|none|none|
|noOfStocks|integer(int64)|false|none|none|
|value|number|false|none|none|
|importedByAdminUserId|integer(int64)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|brokerId|PMSECURITIES|
|brokerId|ABANS_SECURITIES|
|brokerId|AJAY_JAIN|
|brokerId|ALACRITY_SECURITIES|
|brokerId|ALDAN_INVESTMENTS|
|brokerId|ALLWIN_SECURITIES|
|brokerId|AMIT_SAHITA_SEC|
|brokerId|ANANT_INVESTMENTS|
|brokerId|ASHISH_VAID|
|brokerId|ASIAN_BROKING|
|brokerId|AXIOM_BROKING|
|brokerId|BD_SHAH_SECURITIES|
|brokerId|BD_SHROFF_SECURITIES|
|brokerId|BAJAJ_SHARES|
|brokerId|BIGCAPITA_SECURITIES|
|brokerId|CHIMANLAL_MANEKLAL_SECURITIES|
|brokerId|CHURIWALA_SECURITIES|
|brokerId|CROSSEAS_CAPITAL_SERVICES|
|brokerId|DALAL_BROACHA_STOCK_BROKING|
|brokerId|DARASHAW_COMPANY|
|brokerId|DEEP_FINANCIAL_CONSULTANTS|
|brokerId|DHANKI_SECURITIES|
|brokerId|DHARAMSHI_SECURITIES|
|brokerId|DHWAJA_SHARES|
|brokerId|DHYAN_STOCKS|
|brokerId|ELIXIR_EQUITIES|
|brokerId|FIRST_INDIA_SECURITIES|
|brokerId|GNG_INVESTMENTS|
|brokerId|GHANSHYAM_SHARES_STOCK_BROKERS|
|brokerId|HARENDRA_D_MEHTA_SHARE_AND_STOCK_BROKER|
|brokerId|HARJIVANDAS_NEMIDAS_SECURITIES|
|brokerId|HORNIC_INVESTMENT|
|brokerId|INA_STOCK_BROKING|
|brokerId|JAS_ONE_SECURITIES|
|brokerId|JMP_SECURITIES|
|brokerId|RRS_SHARES_STOCK_BROKERS|
|brokerId|KAI_SECURITIES|
|brokerId|KALASH_SHARES|
|brokerId|KANTILAL_CHHAGANLAL_SEC|
|brokerId|KAUSHIK_SHAH_SHARES_SECURITIES|
|brokerId|KAVIRAJ_SECURITIES|
|brokerId|KIMAYA_SECURITIES|
|brokerId|LOTUS_GLOBAL_EQUITIES|
|brokerId|LPC_SECURITIES|
|brokerId|MD_SHUKLA_SHARE_AND_SECURITIES|
|brokerId|MJ_PATEL_SHARE|
|brokerId|VC_MEHTA|
|brokerId|MACY_SECURITIES|
|brokerId|MACY_SHARES_AND_STOCK_BROKERS|
|brokerId|MANUBHAI_MANGALDAS_SEC|
|brokerId|MANYOG_SECURITIES|
|brokerId|MARKETWOLF_SECURITIES|
|brokerId|MAXIMUS_SECURITIES|
|brokerId|MDN_SHARES_AND_STOCK_BROKERS|
|brokerId|MEHTA_VAKIL|
|brokerId|MESH_STOCK_BROKERS|
|brokerId|MUKUL_AMRUTLAL_SONAWALA|
|brokerId|NANGALIA_STOCK_BROKING|
|brokerId|PSURYAKANT_SHARE_STOCK_BROKERS|
|brokerId|PAVAK_SECURITIES|
|brokerId|PRAKASH_K_SHAH_SHARES_SECURITIES|
|brokerId|PRAKASH_SECURITIES|
|brokerId|PRARAMBH_SECURITIES|
|brokerId|PRL_STOCK_AND_SHARE_BROKERS|
|brokerId|RN_PATWA_SHARES_STOCK_BROKERS|
|brokerId|RAMESH_DAMANI|
|brokerId|RASHI_EQUISEARCH|
|brokerId|SHARAD_AGARWAL_BROKING_SERVICES|
|brokerId|SHREE_NAMAN_SECURITIES|
|brokerId|SHREEHARI_SHARES_AND_STOCK_BROKERS|
|brokerId|SURESH_KHANDELWAL|
|brokerId|TRUSTED_SHARES_INVESTMENTS|
|brokerId|UNIQUE_STOCKBRO|
|brokerId|UPMOVE_FINANCIAL_TECHNOLOGIES|
|brokerId|WELATHMILLS_SECURITIES|
|brokerId|YOGEN_BABU_SECURITIES|
|brokerId|CHOICE_BROKING|
|validityStatus|VALID|
|validityStatus|INVALID|

<h2 id="tocS_BrokerUserHoldingResponseDto">BrokerUserHoldingResponseDto</h2>

<a id="schemabrokeruserholdingresponsedto"></a>
<a id="schema_BrokerUserHoldingResponseDto"></a>
<a id="tocSbrokeruserholdingresponsedto"></a>
<a id="tocsbrokeruserholdingresponsedto"></a>

```json
{
  "accountInfo": {
    "id": 0,
    "clientName": "string",
    "countryCode": "string",
    "uploadRequestId": 0,
    "brokerName": "string",
    "creationTime": 0,
    "brokerId": "PMSECURITIES",
    "brokerSignupRequestId": "string",
    "userId": 0,
    "validityStatus": "VALID",
    "noOfStocks": 0,
    "value": 0,
    "importedByAdminUserId": 0
  },
  "individualHoldings": [
    {
      "id": 0,
      "brokerUserAccountInfoId": 0,
      "qty": 0,
      "isin": "string",
      "creationTime": 0
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|accountInfo|[BrokerUserAccountInfoResponseDto](#schemabrokeruseraccountinforesponsedto)|false|none|none|
|individualHoldings|[[BrokerUserIndividualHoldingsResponseDto](#schemabrokeruserindividualholdingsresponsedto)]|false|none|none|

<h2 id="tocS_BrokerUserIndividualHoldingsResponseDto">BrokerUserIndividualHoldingsResponseDto</h2>

<a id="schemabrokeruserindividualholdingsresponsedto"></a>
<a id="schema_BrokerUserIndividualHoldingsResponseDto"></a>
<a id="tocSbrokeruserindividualholdingsresponsedto"></a>
<a id="tocsbrokeruserindividualholdingsresponsedto"></a>

```json
{
  "id": 0,
  "brokerUserAccountInfoId": 0,
  "qty": 0,
  "isin": "string",
  "creationTime": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer(int64)|false|none|none|
|brokerUserAccountInfoId|integer(int64)|false|none|none|
|qty|integer(int32)|false|none|none|
|isin|string|false|none|none|
|creationTime|integer(int64)|false|none|none|

<h2 id="tocS_UserPaidPlanShiftSurveyTriggerRequestDto">UserPaidPlanShiftSurveyTriggerRequestDto</h2>

<a id="schemauserpaidplanshiftsurveytriggerrequestdto"></a>
<a id="schema_UserPaidPlanShiftSurveyTriggerRequestDto"></a>
<a id="tocSuserpaidplanshiftsurveytriggerrequestdto"></a>
<a id="tocsuserpaidplanshiftsurveytriggerrequestdto"></a>

```json
{
  "userId": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|userId|string|false|none|none|

<h2 id="tocS_UserPaidPlanShiftSurveyUploadCumulativeResponseDto">UserPaidPlanShiftSurveyUploadCumulativeResponseDto</h2>

<a id="schemauserpaidplanshiftsurveyuploadcumulativeresponsedto"></a>
<a id="schema_UserPaidPlanShiftSurveyUploadCumulativeResponseDto"></a>
<a id="tocSuserpaidplanshiftsurveyuploadcumulativeresponsedto"></a>
<a id="tocsuserpaidplanshiftsurveyuploadcumulativeresponsedto"></a>

```json
{
  "success": [
    {
      "userId": 0,
      "failureReason": "string"
    }
  ],
  "failure": [
    {
      "userId": 0,
      "failureReason": "string"
    }
  ],
  "successCount": 0,
  "failureCount": 0,
  "requestCount": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|success|[[UserPaidPlanShiftSurveyUploadResponseDto](#schemauserpaidplanshiftsurveyuploadresponsedto)]|false|none|none|
|failure|[[UserPaidPlanShiftSurveyUploadResponseDto](#schemauserpaidplanshiftsurveyuploadresponsedto)]|false|none|none|
|successCount|integer(int32)|false|none|none|
|failureCount|integer(int32)|false|none|none|
|requestCount|integer(int32)|false|none|none|

<h2 id="tocS_UserPaidPlanShiftSurveyUploadResponseDto">UserPaidPlanShiftSurveyUploadResponseDto</h2>

<a id="schemauserpaidplanshiftsurveyuploadresponsedto"></a>
<a id="schema_UserPaidPlanShiftSurveyUploadResponseDto"></a>
<a id="tocSuserpaidplanshiftsurveyuploadresponsedto"></a>
<a id="tocsuserpaidplanshiftsurveyuploadresponsedto"></a>

```json
{
  "userId": 0,
  "failureReason": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|userId|integer(int64)|false|none|none|
|failureReason|string|false|none|none|

<h2 id="tocS_SurveyFileResponse">SurveyFileResponse</h2>

<a id="schemasurveyfileresponse"></a>
<a id="schema_SurveyFileResponse"></a>
<a id="tocSsurveyfileresponse"></a>
<a id="tocssurveyfileresponse"></a>

```json
{
  "success": [
    {
      "userId": 0,
      "failureReason": "string"
    }
  ],
  "failure": [
    {
      "userId": 0,
      "failureReason": "string"
    }
  ],
  "successCount": 0,
  "failureCount": 0,
  "requestCount": 0,
  "htmlResponse": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|success|[[SurveyRequestResponseDto](#schemasurveyrequestresponsedto)]|false|none|none|
|failure|[[SurveyRequestResponseDto](#schemasurveyrequestresponsedto)]|false|none|none|
|successCount|integer(int32)|false|none|none|
|failureCount|integer(int32)|false|none|none|
|requestCount|integer(int32)|false|none|none|
|htmlResponse|string|false|none|none|

<h2 id="tocS_SurveyRequestResponseDto">SurveyRequestResponseDto</h2>

<a id="schemasurveyrequestresponsedto"></a>
<a id="schema_SurveyRequestResponseDto"></a>
<a id="tocSsurveyrequestresponsedto"></a>
<a id="tocssurveyrequestresponsedto"></a>

```json
{
  "userId": 0,
  "failureReason": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|userId|integer(int64)|false|none|none|
|failureReason|string|false|none|none|

<h2 id="tocS_AdminUserDataReportGenerationRequestDto">AdminUserDataReportGenerationRequestDto</h2>

<a id="schemaadminuserdatareportgenerationrequestdto"></a>
<a id="schema_AdminUserDataReportGenerationRequestDto"></a>
<a id="tocSadminuserdatareportgenerationrequestdto"></a>
<a id="tocsadminuserdatareportgenerationrequestdto"></a>

```json
{
  "startTime": "2019-08-24T14:15:22Z",
  "endTime": "2019-08-24T14:15:22Z",
  "emailIds": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|startTime|string(date-time)|false|none|none|
|endTime|string(date-time)|false|none|none|
|emailIds|string|false|none|none|

<h2 id="tocS_AdminReportGenerationResponseDto">AdminReportGenerationResponseDto</h2>

<a id="schemaadminreportgenerationresponsedto"></a>
<a id="schema_AdminReportGenerationResponseDto"></a>
<a id="tocSadminreportgenerationresponsedto"></a>
<a id="tocsadminreportgenerationresponsedto"></a>

```json
{
  "reportType": "CONSOLIDATED_USER_DATA",
  "message": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|reportType|string|false|none|none|
|message|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|reportType|CONSOLIDATED_USER_DATA|
|reportType|PAYMENTS_DATA|
|reportType|DISCOUNT_REMINDER_RUN_STATISTIC|
|reportType|USER_PAID_PLAN_SHIFT_SURVEY_STATISTIC|
|reportType|EXPLAINER_VIDEO_SENT_STATISTIC|

<h2 id="tocS_InstrumentUpdateReplayRequestDto">InstrumentUpdateReplayRequestDto</h2>

<a id="schemainstrumentupdatereplayrequestdto"></a>
<a id="schema_InstrumentUpdateReplayRequestDto"></a>
<a id="tocSinstrumentupdatereplayrequestdto"></a>
<a id="tocsinstrumentupdatereplayrequestdto"></a>

```json
{
  "instrumentUpdateId": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|instrumentUpdateId|integer(int64)|false|none|none|

<h2 id="tocS_AdminFileNseImportResponseDto">AdminFileNseImportResponseDto</h2>

<a id="schemaadminfilenseimportresponsedto"></a>
<a id="schema_AdminFileNseImportResponseDto"></a>
<a id="tocSadminfilenseimportresponsedto"></a>
<a id="tocsadminfilenseimportresponsedto"></a>

```json
{
  "nseInstrumentCountBefore": 0,
  "nseInstrumentCountAfter": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|nseInstrumentCountBefore|integer(int64)|false|none|none|
|nseInstrumentCountAfter|integer(int64)|false|none|none|

<h2 id="tocS_AdminFileImportReportResponseDto">AdminFileImportReportResponseDto</h2>

<a id="schemaadminfileimportreportresponsedto"></a>
<a id="schema_AdminFileImportReportResponseDto"></a>
<a id="tocSadminfileimportreportresponsedto"></a>
<a id="tocsadminfileimportreportresponsedto"></a>

```json
{
  "instrumentCountImportedFromFile": 0,
  "rebuiltTreeSize": 0,
  "companyTreeSize": 0,
  "newInstruments": {
    "errors": [
      {
        "isin": "string",
        "tickr": "string",
        "bseId": 0,
        "longName": "string",
        "instrumentType": "E",
        "groupName": "string",
        "bseExclusive": "string",
        "tradingStatus": "A",
        "securityType": "EQ",
        "gsmFlag": 0
      }
    ],
    "success": [
      {
        "isin": "string",
        "tickr": "string",
        "bseId": 0,
        "longName": "string",
        "instrumentType": "E",
        "groupName": "string",
        "bseExclusive": "string",
        "tradingStatus": "A",
        "securityType": "EQ",
        "gsmFlag": 0
      }
    ],
    "successSize": 0,
    "errorSize": 0,
    "totalSize": 0
  },
  "inactiveInstruments": {
    "success": [
      "string"
    ],
    "errors": [
      "string"
    ],
    "successSize": 0,
    "errorSize": 0,
    "totalSize": 0
  },
  "importId": 0,
  "companiesBeforeUpload": 0,
  "companiesAfterUpload": 0,
  "fileImportBhavCopyReport": {
    "errors": {
      "property1": "string",
      "property2": "string"
    },
    "successSize": 0,
    "errorSize": 0
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|instrumentCountImportedFromFile|integer(int64)|false|none|none|
|rebuiltTreeSize|integer(int64)|false|none|none|
|companyTreeSize|integer(int64)|false|none|none|
|newInstruments|[FileImportReportIndividualActionDto](#schemafileimportreportindividualactiondto)|false|none|none|
|inactiveInstruments|[FileImportReportUpdatedInstrumentsDto](#schemafileimportreportupdatedinstrumentsdto)|false|none|none|
|importId|integer(int64)|false|none|none|
|companiesBeforeUpload|integer(int64)|false|none|none|
|companiesAfterUpload|integer(int64)|false|none|none|
|fileImportBhavCopyReport|[FileImportBhavCopyReport](#schemafileimportbhavcopyreport)|false|none|none|

<h2 id="tocS_RetryNewsIdRequestDto">RetryNewsIdRequestDto</h2>

<a id="schemaretrynewsidrequestdto"></a>
<a id="schema_RetryNewsIdRequestDto"></a>
<a id="tocSretrynewsidrequestdto"></a>
<a id="tocsretrynewsidrequestdto"></a>

```json
{
  "newsIds": [
    "string"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|newsIds|[string]|true|none|none|

<h2 id="tocS_RetryNewsIdResponseDto">RetryNewsIdResponseDto</h2>

<a id="schemaretrynewsidresponsedto"></a>
<a id="schema_RetryNewsIdResponseDto"></a>
<a id="tocSretrynewsidresponsedto"></a>
<a id="tocsretrynewsidresponsedto"></a>

```json
{
  "newsId": "string",
  "retryNewsId": "string",
  "status": "string",
  "failureReason": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|newsId|string|false|none|none|
|retryNewsId|string|false|none|none|
|status|string|false|none|none|
|failureReason|string|false|none|none|

<h2 id="tocS_UserReferralLinkResponseDto">UserReferralLinkResponseDto</h2>

<a id="schemauserreferrallinkresponsedto"></a>
<a id="schema_UserReferralLinkResponseDto"></a>
<a id="tocSuserreferrallinkresponsedto"></a>
<a id="tocsuserreferrallinkresponsedto"></a>

```json
{
  "referralLink": "string",
  "referralSource": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|referralLink|string|false|none|none|
|referralSource|string|false|none|none|

<h2 id="tocS_UserPaymentPlanDetailsResponseDto">UserPaymentPlanDetailsResponseDto</h2>

<a id="schemauserpaymentplandetailsresponsedto"></a>
<a id="schema_UserPaymentPlanDetailsResponseDto"></a>
<a id="tocSuserpaymentplandetailsresponsedto"></a>
<a id="tocsuserpaymentplandetailsresponsedto"></a>

```json
{
  "planType": "BASIC",
  "isTrial": true,
  "description": "string",
  "planExpiryDate": "string",
  "stockTrackingLimit": 0,
  "planName": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|planType|string|false|none|none|
|isTrial|boolean|false|none|none|
|description|string|false|none|none|
|planExpiryDate|string|false|none|none|
|stockTrackingLimit|integer(int32)|false|none|none|
|planName|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|planType|BASIC|
|planType|PROFESSIONAL|
|planType|POWER_USER|
|planType|FREE|
|planType|EXPIRED|

<h2 id="tocS_UserProfileResponseDto">UserProfileResponseDto</h2>

<a id="schemauserprofileresponsedto"></a>
<a id="schema_UserProfileResponseDto"></a>
<a id="tocSuserprofileresponsedto"></a>
<a id="tocsuserprofileresponsedto"></a>

```json
{
  "userDetails": {
    "countryCode": "string",
    "mobileNumber": 0,
    "userId": "string",
    "userName": "string",
    "name": "string",
    "emailId": "string",
    "roles": [
      "CLIENT"
    ],
    "planType": "TRIAL",
    "creationTime": 0,
    "userPlanExpiryDate": "2019-08-24",
    "isUserProfilingComplete": true,
    "stockTrackingLimit": 0,
    "planNameSchemeRefId": "string",
    "userPrivileged": true,
    "emailVerified": true
  },
  "notificationPreference": {
    "userId": 0,
    "generalNewsFilter": "NONE",
    "technicalAnalysisFilter": "NONE",
    "active": true
  },
  "userCorporateInformation": {
    "companyName": "string",
    "companyProfile": "string",
    "companyWebsite": "string",
    "designation": "string",
    "emailId": "string",
    "userId": "string",
    "name": "string",
    "emailType": "CORPORATE",
    "emailVerified": true
  },
  "paymentPlanDetails": {
    "planType": "BASIC",
    "isTrial": true,
    "description": "string",
    "planExpiryDate": "string",
    "stockTrackingLimit": 0,
    "planName": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|userDetails|[UserResponseDto](#schemauserresponsedto)|false|none|none|
|notificationPreference|[UserNotificationPreferenceResponseDto](#schemausernotificationpreferenceresponsedto)|false|none|none|
|userCorporateInformation|[UserCorporateInformationResponseDto](#schemausercorporateinformationresponsedto)|false|none|none|
|paymentPlanDetails|[UserPaymentPlanDetailsResponseDto](#schemauserpaymentplandetailsresponsedto)|false|none|none|

<h2 id="tocS_CumulativeUserInstrumentUpdateCategoryFilterMappingResponseDto">CumulativeUserInstrumentUpdateCategoryFilterMappingResponseDto</h2>

<a id="schemacumulativeuserinstrumentupdatecategoryfiltermappingresponsedto"></a>
<a id="schema_CumulativeUserInstrumentUpdateCategoryFilterMappingResponseDto"></a>
<a id="tocScumulativeuserinstrumentupdatecategoryfiltermappingresponsedto"></a>
<a id="tocscumulativeuserinstrumentupdatecategoryfiltermappingresponsedto"></a>

```json
{
  "categoryFilters": [
    {
      "id": 0,
      "userId": 0,
      "mappingType": "CATEGORY_FILTER",
      "category": "KEY_UPDATE",
      "filterScope": "NONE",
      "lastUpdateTime": 0,
      "isInactive": true
    }
  ],
  "isFilterEditAllowed": true,
  "userPlanType": "TRIAL",
  "planName": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|categoryFilters|[[UserInstrumentUpdateCategoryFilterMappingResponseDto](#schemauserinstrumentupdatecategoryfiltermappingresponsedto)]|false|none|none|
|isFilterEditAllowed|boolean|false|none|none|
|userPlanType|string|false|none|none|
|planName|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|userPlanType|TRIAL|
|userPlanType|TRIAL_EXPIRED|
|userPlanType|PAID_BASIC|
|userPlanType|PAID_PROFESSIONAL|
|userPlanType|PAID_POWER_USER|
|userPlanType|TRIAL_BASIC|
|userPlanType|TRIAL_PROFESSIONAL|
|userPlanType|TRIAL_POWER_USER|
|userPlanType|FREE|

<h2 id="tocS_CurrentUserDiscountResponseDto">CurrentUserDiscountResponseDto</h2>

<a id="schemacurrentuserdiscountresponsedto"></a>
<a id="schema_CurrentUserDiscountResponseDto"></a>
<a id="tocScurrentuserdiscountresponsedto"></a>
<a id="tocscurrentuserdiscountresponsedto"></a>

```json
{
  "isDiscountOnBasicMonthly": true,
  "isDiscountOnProfessionalMonthly": true,
  "isDiscountOnPowerUserMonthly": true,
  "isDiscountOnBasicYearly": true,
  "isDiscountOnProfessionalYearly": true,
  "isDiscountOnPowerUserYearly": true,
  "basicDiscountTextMonthly": "string",
  "professionalDiscountTextMonthly": "string",
  "powerUserDiscountTextMonthly": "string",
  "basicDiscountTextYearly": "string",
  "professionalDiscountTextYearly": "string",
  "powerUserDiscountTextYearly": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isDiscountOnBasicMonthly|boolean|false|none|none|
|isDiscountOnProfessionalMonthly|boolean|false|none|none|
|isDiscountOnPowerUserMonthly|boolean|false|none|none|
|isDiscountOnBasicYearly|boolean|false|none|none|
|isDiscountOnProfessionalYearly|boolean|false|none|none|
|isDiscountOnPowerUserYearly|boolean|false|none|none|
|basicDiscountTextMonthly|string|false|none|none|
|professionalDiscountTextMonthly|string|false|none|none|
|powerUserDiscountTextMonthly|string|false|none|none|
|basicDiscountTextYearly|string|false|none|none|
|professionalDiscountTextYearly|string|false|none|none|
|powerUserDiscountTextYearly|string|false|none|none|

<h2 id="tocS_SubscriptionDetailsResponseBodyDto">SubscriptionDetailsResponseBodyDto</h2>

<a id="schemasubscriptiondetailsresponsebodydto"></a>
<a id="schema_SubscriptionDetailsResponseBodyDto"></a>
<a id="tocSsubscriptiondetailsresponsebodydto"></a>
<a id="tocssubscriptiondetailsresponsebodydto"></a>

```json
{
  "resultInfo": {
    "code": "string",
    "message": "string",
    "status": "string"
  },
  "subsId": "string",
  "status": "INIT",
  "subStatus": "INIT",
  "activationDate": "string",
  "vpa": "string",
  "orderId": "string",
  "subsPaymentInstDetails": {
    "maskedAccountNumber": "string",
    "ifsc": "string",
    "maskedVpa": "string",
    "bankName": "string",
    "paymentMode": "NORMAL",
    "instrumentStatus": "EXPIRED"
  },
  "subsLastRetryDone": {
    "status": "string",
    "attemptedTime": "string"
  },
  "subsNextRetry": {
    "attemptedTime": "string"
  },
  "subsRetryDetails": {
    "totalRetryCount": "string",
    "retriesLeft": "string"
  },
  "lastOrderId": "string",
  "lastOrderStatus": "string",
  "lastOrderCreationDate": "string",
  "lastOrderAmount": "string",
  "amountType": "FIX",
  "maxAmount": "string",
  "mid": "string",
  "frequencyUnit": "DAY",
  "frequency": "string",
  "merchantName": "string",
  "expiryDate": "string",
  "createdDate": "string",
  "updatedDate": "string",
  "custId": "string",
  "custEmailId": "string",
  "custMobileNo": "string",
  "respCode": "string",
  "respMsg": "string",
  "upfrontTxnAmount": "string",
  "upfrontTxnId": "string",
  "linkDetails": {
    "linkId": "string",
    "linkNotes": "string",
    "expiryDate": "string",
    "shortUrl": "string"
  },
  "pauseStartDate": "string",
  "pauseEndDate": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|resultInfo|[SubscriptionDetailsResponseResultInfoDto](#schemasubscriptiondetailsresponseresultinfodto)|false|none|none|
|subsId|string|false|none|none|
|status|string|false|none|none|
|subStatus|string|false|none|none|
|activationDate|string|false|none|none|
|vpa|string|false|none|none|
|orderId|string|false|none|none|
|subsPaymentInstDetails|[SubscriptionDetailsResponseSubPaymentInstDetailsDto](#schemasubscriptiondetailsresponsesubpaymentinstdetailsdto)|false|none|none|
|subsLastRetryDone|[SubscriptionDetailsResponseLastRetryStatusDto](#schemasubscriptiondetailsresponselastretrystatusdto)|false|none|none|
|subsNextRetry|[SubscriptionDetailsResponseNextRetryDto](#schemasubscriptiondetailsresponsenextretrydto)|false|none|none|
|subsRetryDetails|[SubscriptionDetailsResponseRetryDetailsDto](#schemasubscriptiondetailsresponseretrydetailsdto)|false|none|none|
|lastOrderId|string|false|none|none|
|lastOrderStatus|string|false|none|none|
|lastOrderCreationDate|string|false|none|none|
|lastOrderAmount|string|false|none|none|
|amountType|string|false|none|none|
|maxAmount|string|false|none|none|
|mid|string|false|none|none|
|frequencyUnit|string|false|none|none|
|frequency|string|false|none|none|
|merchantName|string|false|none|none|
|expiryDate|string|false|none|none|
|createdDate|string|false|none|none|
|updatedDate|string|false|none|none|
|custId|string|false|none|none|
|custEmailId|string|false|none|none|
|custMobileNo|string|false|none|none|
|respCode|string|false|none|none|
|respMsg|string|false|none|none|
|upfrontTxnAmount|string|false|none|none|
|upfrontTxnId|string|false|none|none|
|linkDetails|[SubscriptionDetailsResponseLinkDetailsDto](#schemasubscriptiondetailsresponselinkdetailsdto)|false|none|none|
|pauseStartDate|string|false|none|none|
|pauseEndDate|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|INIT|
|status|ACTIVE|
|status|REJECT|
|status|IN_AUTHORIZATION|
|status|AUTHORIZED|
|status|AUTHORIZATION_FAILED|
|status|EXPIRED|
|status|CLOSED|
|status|SUSPENDED|
|subStatus|INIT|
|subStatus|PPBL_PENDING|
|subStatus|PPBL_REJECT|
|subStatus|NPCI_PENDING|
|subStatus|NPCI_REJECT|
|subStatus|ACTIVE|
|subStatus|MERCHANT_CANCELLED|
|subStatus|USER_CANCELLED|
|subStatus|TIMED_OUT|
|subStatus|ORDER_CLOSED|
|subStatus|CONFIRMED|
|subStatus|ISSUING_BANK_CANCELLED|
|subStatus|USER_SUSPENDED|
|subStatus|MERCHANT_SUSPENDED|
|subStatus|PPBL_SUSPENDED|
|subStatus|RESUMED|
|amountType|FIX|
|amountType|VARIABLE|
|frequencyUnit|DAY|
|frequencyUnit|WEEK|
|frequencyUnit|MONTH|
|frequencyUnit|BI_MONTHLY|
|frequencyUnit|QUARTER|
|frequencyUnit|SEMI_ANNUALLY|
|frequencyUnit|YEAR|
|frequencyUnit|ONDEMAND|

<h2 id="tocS_SubscriptionDetailsResponseDto">SubscriptionDetailsResponseDto</h2>

<a id="schemasubscriptiondetailsresponsedto"></a>
<a id="schema_SubscriptionDetailsResponseDto"></a>
<a id="tocSsubscriptiondetailsresponsedto"></a>
<a id="tocssubscriptiondetailsresponsedto"></a>

```json
{
  "subscriptionComplete": true,
  "head": {
    "responseTimestamp": "string",
    "signature": "string",
    "tokenType": "string"
  },
  "body": {
    "resultInfo": {
      "code": "string",
      "message": "string",
      "status": "string"
    },
    "subsId": "string",
    "status": "INIT",
    "subStatus": "INIT",
    "activationDate": "string",
    "vpa": "string",
    "orderId": "string",
    "subsPaymentInstDetails": {
      "maskedAccountNumber": "string",
      "ifsc": "string",
      "maskedVpa": "string",
      "bankName": "string",
      "paymentMode": "NORMAL",
      "instrumentStatus": "EXPIRED"
    },
    "subsLastRetryDone": {
      "status": "string",
      "attemptedTime": "string"
    },
    "subsNextRetry": {
      "attemptedTime": "string"
    },
    "subsRetryDetails": {
      "totalRetryCount": "string",
      "retriesLeft": "string"
    },
    "lastOrderId": "string",
    "lastOrderStatus": "string",
    "lastOrderCreationDate": "string",
    "lastOrderAmount": "string",
    "amountType": "FIX",
    "maxAmount": "string",
    "mid": "string",
    "frequencyUnit": "DAY",
    "frequency": "string",
    "merchantName": "string",
    "expiryDate": "string",
    "createdDate": "string",
    "updatedDate": "string",
    "custId": "string",
    "custEmailId": "string",
    "custMobileNo": "string",
    "respCode": "string",
    "respMsg": "string",
    "upfrontTxnAmount": "string",
    "upfrontTxnId": "string",
    "linkDetails": {
      "linkId": "string",
      "linkNotes": "string",
      "expiryDate": "string",
      "shortUrl": "string"
    },
    "pauseStartDate": "string",
    "pauseEndDate": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|subscriptionComplete|boolean|false|none|none|
|head|[SubscriptionDetailsResponseHeadDto](#schemasubscriptiondetailsresponseheaddto)|false|none|none|
|body|[SubscriptionDetailsResponseBodyDto](#schemasubscriptiondetailsresponsebodydto)|false|none|none|

<h2 id="tocS_SubscriptionDetailsResponseHeadDto">SubscriptionDetailsResponseHeadDto</h2>

<a id="schemasubscriptiondetailsresponseheaddto"></a>
<a id="schema_SubscriptionDetailsResponseHeadDto"></a>
<a id="tocSsubscriptiondetailsresponseheaddto"></a>
<a id="tocssubscriptiondetailsresponseheaddto"></a>

```json
{
  "responseTimestamp": "string",
  "signature": "string",
  "tokenType": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|responseTimestamp|string|false|none|none|
|signature|string|false|none|none|
|tokenType|string|false|none|none|

<h2 id="tocS_SubscriptionDetailsResponseLastRetryStatusDto">SubscriptionDetailsResponseLastRetryStatusDto</h2>

<a id="schemasubscriptiondetailsresponselastretrystatusdto"></a>
<a id="schema_SubscriptionDetailsResponseLastRetryStatusDto"></a>
<a id="tocSsubscriptiondetailsresponselastretrystatusdto"></a>
<a id="tocssubscriptiondetailsresponselastretrystatusdto"></a>

```json
{
  "status": "string",
  "attemptedTime": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|status|string|false|none|none|
|attemptedTime|string|false|none|none|

<h2 id="tocS_SubscriptionDetailsResponseLinkDetailsDto">SubscriptionDetailsResponseLinkDetailsDto</h2>

<a id="schemasubscriptiondetailsresponselinkdetailsdto"></a>
<a id="schema_SubscriptionDetailsResponseLinkDetailsDto"></a>
<a id="tocSsubscriptiondetailsresponselinkdetailsdto"></a>
<a id="tocssubscriptiondetailsresponselinkdetailsdto"></a>

```json
{
  "linkId": "string",
  "linkNotes": "string",
  "expiryDate": "string",
  "shortUrl": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|linkId|string|false|none|none|
|linkNotes|string|false|none|none|
|expiryDate|string|false|none|none|
|shortUrl|string|false|none|none|

<h2 id="tocS_SubscriptionDetailsResponseNextRetryDto">SubscriptionDetailsResponseNextRetryDto</h2>

<a id="schemasubscriptiondetailsresponsenextretrydto"></a>
<a id="schema_SubscriptionDetailsResponseNextRetryDto"></a>
<a id="tocSsubscriptiondetailsresponsenextretrydto"></a>
<a id="tocssubscriptiondetailsresponsenextretrydto"></a>

```json
{
  "attemptedTime": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|attemptedTime|string|false|none|none|

<h2 id="tocS_SubscriptionDetailsResponseResultInfoDto">SubscriptionDetailsResponseResultInfoDto</h2>

<a id="schemasubscriptiondetailsresponseresultinfodto"></a>
<a id="schema_SubscriptionDetailsResponseResultInfoDto"></a>
<a id="tocSsubscriptiondetailsresponseresultinfodto"></a>
<a id="tocssubscriptiondetailsresponseresultinfodto"></a>

```json
{
  "code": "string",
  "message": "string",
  "status": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|code|string|false|none|none|
|message|string|false|none|none|
|status|string|false|none|none|

<h2 id="tocS_SubscriptionDetailsResponseRetryDetailsDto">SubscriptionDetailsResponseRetryDetailsDto</h2>

<a id="schemasubscriptiondetailsresponseretrydetailsdto"></a>
<a id="schema_SubscriptionDetailsResponseRetryDetailsDto"></a>
<a id="tocSsubscriptiondetailsresponseretrydetailsdto"></a>
<a id="tocssubscriptiondetailsresponseretrydetailsdto"></a>

```json
{
  "totalRetryCount": "string",
  "retriesLeft": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|totalRetryCount|string|false|none|none|
|retriesLeft|string|false|none|none|

<h2 id="tocS_SubscriptionDetailsResponseSubPaymentInstDetailsDto">SubscriptionDetailsResponseSubPaymentInstDetailsDto</h2>

<a id="schemasubscriptiondetailsresponsesubpaymentinstdetailsdto"></a>
<a id="schema_SubscriptionDetailsResponseSubPaymentInstDetailsDto"></a>
<a id="tocSsubscriptiondetailsresponsesubpaymentinstdetailsdto"></a>
<a id="tocssubscriptiondetailsresponsesubpaymentinstdetailsdto"></a>

```json
{
  "maskedAccountNumber": "string",
  "ifsc": "string",
  "maskedVpa": "string",
  "bankName": "string",
  "paymentMode": "NORMAL",
  "instrumentStatus": "EXPIRED"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|maskedAccountNumber|string|false|none|none|
|ifsc|string|false|none|none|
|maskedVpa|string|false|none|none|
|bankName|string|false|none|none|
|paymentMode|string|false|none|none|
|instrumentStatus|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|paymentMode|NORMAL|
|paymentMode|PPI|
|paymentMode|CC|
|paymentMode|DC|
|paymentMode|PPBL|
|paymentMode|BANK_MANDATE|
|paymentMode|UPI|
|paymentMode|UNKNOWN|
|instrumentStatus|EXPIRED|
|instrumentStatus|ACTIVE|
|instrumentStatus|INACTIVE|

<h2 id="tocS_PaytmPreNotificationStatusRequestDto">PaytmPreNotificationStatusRequestDto</h2>

<a id="schemapaytmprenotificationstatusrequestdto"></a>
<a id="schema_PaytmPreNotificationStatusRequestDto"></a>
<a id="tocSpaytmprenotificationstatusrequestdto"></a>
<a id="tocspaytmprenotificationstatusrequestdto"></a>

```json
{
  "subscriptionId": "string",
  "preNotificationPaytmReferenceId": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|subscriptionId|string|false|none|none|
|preNotificationPaytmReferenceId|string|false|none|none|

<h2 id="tocS_PreNotifyCheckStatusResponseBodyDto">PreNotifyCheckStatusResponseBodyDto</h2>

<a id="schemaprenotifycheckstatusresponsebodydto"></a>
<a id="schema_PreNotifyCheckStatusResponseBodyDto"></a>
<a id="tocSprenotifycheckstatusresponsebodydto"></a>
<a id="tocsprenotifycheckstatusresponsebodydto"></a>

```json
{
  "resultInfo": {
    "code": "string",
    "status": "SUCCESS",
    "message": "string"
  },
  "txnDate": "2019-08-24T14:15:22Z",
  "txnMessage": "string",
  "notificationStatus": "SUCCESS",
  "notificationStatusCode": "string",
  "notificationStatusMessage": "string",
  "notificationDate": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|resultInfo|[PreNotifyCheckStatusResponseResultInfoDto](#schemaprenotifycheckstatusresponseresultinfodto)|false|none|none|
|txnDate|string(date-time)|false|none|none|
|txnMessage|string|false|none|none|
|notificationStatus|string|false|none|none|
|notificationStatusCode|string|false|none|none|
|notificationStatusMessage|string|false|none|none|
|notificationDate|string(date-time)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|notificationStatus|SUCCESS|
|notificationStatus|FAILURE|
|notificationStatus|PENDING|
|notificationStatus|REVOKED|
|notificationStatus|BLOCKED|
|notificationStatus|CLOSED|

<h2 id="tocS_PreNotifyCheckStatusResponseDto">PreNotifyCheckStatusResponseDto</h2>

<a id="schemaprenotifycheckstatusresponsedto"></a>
<a id="schema_PreNotifyCheckStatusResponseDto"></a>
<a id="tocSprenotifycheckstatusresponsedto"></a>
<a id="tocsprenotifycheckstatusresponsedto"></a>

```json
{
  "head": {
    "clientId": "string",
    "version": "string",
    "timestamp": "string"
  },
  "body": {
    "resultInfo": {
      "code": "string",
      "status": "SUCCESS",
      "message": "string"
    },
    "txnDate": "2019-08-24T14:15:22Z",
    "txnMessage": "string",
    "notificationStatus": "SUCCESS",
    "notificationStatusCode": "string",
    "notificationStatusMessage": "string",
    "notificationDate": "2019-08-24T14:15:22Z"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|head|[PreNotifyCheckStatusResponseHeadDto](#schemaprenotifycheckstatusresponseheaddto)|false|none|none|
|body|[PreNotifyCheckStatusResponseBodyDto](#schemaprenotifycheckstatusresponsebodydto)|false|none|none|

<h2 id="tocS_PreNotifyCheckStatusResponseHeadDto">PreNotifyCheckStatusResponseHeadDto</h2>

<a id="schemaprenotifycheckstatusresponseheaddto"></a>
<a id="schema_PreNotifyCheckStatusResponseHeadDto"></a>
<a id="tocSprenotifycheckstatusresponseheaddto"></a>
<a id="tocsprenotifycheckstatusresponseheaddto"></a>

```json
{
  "clientId": "string",
  "version": "string",
  "timestamp": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|clientId|string|false|none|none|
|version|string|false|none|none|
|timestamp|string|false|none|none|

<h2 id="tocS_PreNotifyCheckStatusResponseResultInfoDto">PreNotifyCheckStatusResponseResultInfoDto</h2>

<a id="schemaprenotifycheckstatusresponseresultinfodto"></a>
<a id="schema_PreNotifyCheckStatusResponseResultInfoDto"></a>
<a id="tocSprenotifycheckstatusresponseresultinfodto"></a>
<a id="tocsprenotifycheckstatusresponseresultinfodto"></a>

```json
{
  "code": "string",
  "status": "SUCCESS",
  "message": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|code|string|false|none|none|
|status|string|false|none|none|
|message|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|SUCCESS|
|status|FAILURE|

<h2 id="tocS_IndividualInstrumentUpdateResponseDto">IndividualInstrumentUpdateResponseDto</h2>

<a id="schemaindividualinstrumentupdateresponsedto"></a>
<a id="schema_IndividualInstrumentUpdateResponseDto"></a>
<a id="tocSindividualinstrumentupdateresponsedto"></a>
<a id="tocsindividualinstrumentupdateresponsedto"></a>

```json
{
  "id": 0,
  "scripDetails": {
    "scripCode": "string",
    "scripName": "string",
    "bseTickr": "string",
    "nseTickr": "string",
    "isin": "string"
  },
  "linkDetail": {
    "shortLink": "string",
    "linkSource": "BSE",
    "effectiveLink": "string",
    "linkSourceRaw": "string"
  },
  "updateType": "CORPORATE_ANNOUNCEMENT",
  "updateSubTypeRaw": "string",
  "source": "CORPORATE_ANNOUNCEMENT",
  "title": "string",
  "description": "string",
  "content": "string",
  "link": "string",
  "creationTime": 0,
  "lastUpdateTime": 0,
  "caSpecificCategory": "string",
  "filterCategory": "UNPROCESSED",
  "filterCategoryId": "string",
  "additionalInformation": {}
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer(int64)|false|none|none|
|scripDetails|[ScripDetailResponseDto](#schemascripdetailresponsedto)|false|none|none|
|linkDetail|[LinkDetailResponseDto](#schemalinkdetailresponsedto)|false|none|none|
|updateType|string|false|none|none|
|updateSubTypeRaw|string|false|none|none|
|source|string|false|none|none|
|title|string|false|none|none|
|description|string|false|none|none|
|content|string|false|none|none|
|link|string|false|none|none|
|creationTime|integer(int64)|false|none|none|
|lastUpdateTime|integer(int64)|false|none|none|
|caSpecificCategory|string|false|none|none|
|filterCategory|string|false|none|none|
|filterCategoryId|string|false|none|none|
|additionalInformation|[JsonNode](#schemajsonnode)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|updateType|CORPORATE_ANNOUNCEMENT|
|updateType|TECHNICAL_ANALYSIS|
|updateType|GENERAL_NEWS|
|updateType|TELEGRAM|
|updateType|TWEET|
|updateType|BULLETIN|
|updateType|RSS|
|updateType|CONCALL_HIGHLIGHTS|
|updateType|CONCALL_SUMMARY|
|updateType|FUTURE_OUTLOOK|
|updateType|BULK_BLOCK|
|updateType|SQ_SPVMA_INTRADAY_VOLUME_SPURT|
|updateType|ANALYST_VIEWS|
|source|CORPORATE_ANNOUNCEMENT|
|source|CORPORATE_ANNOUNCEMENT_PDF_AI|
|source|CORPORATE_ANNOUNCEMENT_SAST|
|source|TRADINGVIEW|
|source|MONEYCONTROL_NEWS|
|source|CNBCTV18|
|source|CNBCTV18_MARKET_LIVE|
|source|NA|
|source|RSS_BUSINESS_STANDARD|
|source|RSS_LIVE_MINT|
|source|RSS_MONEYCONTROL|
|source|RSS|
|source|ALPHASTREET_CONCALL_HIGHLIGHTS|
|source|YOUTUBE_NEWS|
|source|SQ_CONCALL_DECODER|
|source|SQ_CRYSTAL_BALL|
|source|BULK_DEALS|
|source|BLOCK_DEALS|
|source|SQ_SPVMA_INTRADAY_VOLUME_SPURT|
|source|ANALYST_VIEWS|
|filterCategory|UNPROCESSED|
|filterCategory|KEY_UPDATE|
|filterCategory|UNCLASSIFIED|
|filterCategory|ANALYTICAL_UPDATE|
|filterCategory|EVENT_SCHEDULE|
|filterCategory|TECHNICAL_IDEA|
|filterCategory|MEDIA_COVERAGE|
|filterCategory|SPVMA|

<h2 id="tocS_LinkDetailResponseDto">LinkDetailResponseDto</h2>

<a id="schemalinkdetailresponsedto"></a>
<a id="schema_LinkDetailResponseDto"></a>
<a id="tocSlinkdetailresponsedto"></a>
<a id="tocslinkdetailresponsedto"></a>

```json
{
  "shortLink": "string",
  "linkSource": "BSE",
  "effectiveLink": "string",
  "linkSourceRaw": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|shortLink|string|false|none|none|
|linkSource|string|false|none|none|
|effectiveLink|string|false|none|none|
|linkSourceRaw|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|linkSource|BSE|
|linkSource|MONEYCONTROL|
|linkSource|CNBCTV18|
|linkSource|BUSINESS_STANDARD|
|linkSource|TRADING_VIEW|
|linkSource|ALPHASTREET|
|linkSource|TWITTER|
|linkSource|YOUTUBE|
|linkSource|MINT|
|linkSource|UNKNOWN|
|linkSource|SCOUTQUEST|
|linkSource|NSE|

<h2 id="tocS_ScripDetailResponseDto">ScripDetailResponseDto</h2>

<a id="schemascripdetailresponsedto"></a>
<a id="schema_ScripDetailResponseDto"></a>
<a id="tocSscripdetailresponsedto"></a>
<a id="tocsscripdetailresponsedto"></a>

```json
{
  "scripCode": "string",
  "scripName": "string",
  "bseTickr": "string",
  "nseTickr": "string",
  "isin": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|scripCode|string|false|none|none|
|scripName|string|false|none|none|
|bseTickr|string|false|none|none|
|nseTickr|string|false|none|none|
|isin|string|false|none|none|

<h2 id="tocS_PageIndividualInstrumentUpdateResponseDto">PageIndividualInstrumentUpdateResponseDto</h2>

<a id="schemapageindividualinstrumentupdateresponsedto"></a>
<a id="schema_PageIndividualInstrumentUpdateResponseDto"></a>
<a id="tocSpageindividualinstrumentupdateresponsedto"></a>
<a id="tocspageindividualinstrumentupdateresponsedto"></a>

```json
{
  "totalElements": 0,
  "totalPages": 0,
  "size": 0,
  "content": [
    {
      "id": 0,
      "scripDetails": {
        "scripCode": "string",
        "scripName": "string",
        "bseTickr": "string",
        "nseTickr": "string",
        "isin": "string"
      },
      "linkDetail": {
        "shortLink": "string",
        "linkSource": "BSE",
        "effectiveLink": "string",
        "linkSourceRaw": "string"
      },
      "updateType": "CORPORATE_ANNOUNCEMENT",
      "updateSubTypeRaw": "string",
      "source": "CORPORATE_ANNOUNCEMENT",
      "title": "string",
      "description": "string",
      "content": "string",
      "link": "string",
      "creationTime": 0,
      "lastUpdateTime": 0,
      "caSpecificCategory": "string",
      "filterCategory": "UNPROCESSED",
      "filterCategoryId": "string",
      "additionalInformation": {}
    }
  ],
  "number": 0,
  "sort": {
    "empty": true,
    "sorted": true,
    "unsorted": true
  },
  "pageable": {
    "offset": 0,
    "sort": {
      "empty": true,
      "sorted": true,
      "unsorted": true
    },
    "pageNumber": 0,
    "pageSize": 0,
    "paged": true,
    "unpaged": true
  },
  "numberOfElements": 0,
  "first": true,
  "last": true,
  "empty": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|totalElements|integer(int64)|false|none|none|
|totalPages|integer(int32)|false|none|none|
|size|integer(int32)|false|none|none|
|content|[[IndividualInstrumentUpdateResponseDto](#schemaindividualinstrumentupdateresponsedto)]|false|none|none|
|number|integer(int32)|false|none|none|
|sort|[SortObject](#schemasortobject)|false|none|none|
|pageable|[PageableObject](#schemapageableobject)|false|none|none|
|numberOfElements|integer(int32)|false|none|none|
|first|boolean|false|none|none|
|last|boolean|false|none|none|
|empty|boolean|false|none|none|

<h2 id="tocS_PageableObject">PageableObject</h2>

<a id="schemapageableobject"></a>
<a id="schema_PageableObject"></a>
<a id="tocSpageableobject"></a>
<a id="tocspageableobject"></a>

```json
{
  "offset": 0,
  "sort": {
    "empty": true,
    "sorted": true,
    "unsorted": true
  },
  "pageNumber": 0,
  "pageSize": 0,
  "paged": true,
  "unpaged": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|offset|integer(int64)|false|none|none|
|sort|[SortObject](#schemasortobject)|false|none|none|
|pageNumber|integer(int32)|false|none|none|
|pageSize|integer(int32)|false|none|none|
|paged|boolean|false|none|none|
|unpaged|boolean|false|none|none|

<h2 id="tocS_SortObject">SortObject</h2>

<a id="schemasortobject"></a>
<a id="schema_SortObject"></a>
<a id="tocSsortobject"></a>
<a id="tocssortobject"></a>

```json
{
  "empty": true,
  "sorted": true,
  "unsorted": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|empty|boolean|false|none|none|
|sorted|boolean|false|none|none|
|unsorted|boolean|false|none|none|

<h2 id="tocS_UserMobileResponseDto">UserMobileResponseDto</h2>

<a id="schemausermobileresponsedto"></a>
<a id="schema_UserMobileResponseDto"></a>
<a id="tocSusermobileresponsedto"></a>
<a id="tocsusermobileresponsedto"></a>

```json
{
  "instrumentUpdates": {
    "totalElements": 0,
    "totalPages": 0,
    "size": 0,
    "content": [
      {
        "id": 0,
        "scripDetails": {
          "scripCode": "string",
          "scripName": "string",
          "bseTickr": "string",
          "nseTickr": "string",
          "isin": "string"
        },
        "linkDetail": {
          "shortLink": "string",
          "linkSource": "[",
          "effectiveLink": "string",
          "linkSourceRaw": "string"
        },
        "updateType": "CORPORATE_ANNOUNCEMENT",
        "updateSubTypeRaw": "string",
        "source": "CORPORATE_ANNOUNCEMENT",
        "title": "string",
        "description": "string",
        "content": "string",
        "link": "string",
        "creationTime": 0,
        "lastUpdateTime": 0,
        "caSpecificCategory": "string",
        "filterCategory": "UNPROCESSED",
        "filterCategoryId": "string",
        "additionalInformation": {}
      }
    ],
    "number": 0,
    "sort": {
      "empty": true,
      "sorted": true,
      "unsorted": true
    },
    "pageable": {
      "offset": 0,
      "sort": {
        "empty": true,
        "sorted": true,
        "unsorted": true
      },
      "pageNumber": 0,
      "pageSize": 0,
      "paged": true,
      "unpaged": true
    },
    "numberOfElements": 0,
    "first": true,
    "last": true,
    "empty": true
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|instrumentUpdates|[PageIndividualInstrumentUpdateResponseDto](#schemapageindividualinstrumentupdateresponsedto)|false|none|none|

<h2 id="tocS_CompanyNameLookupResponseDto">CompanyNameLookupResponseDto</h2>

<a id="schemacompanynamelookupresponsedto"></a>
<a id="schema_CompanyNameLookupResponseDto"></a>
<a id="tocScompanynamelookupresponsedto"></a>
<a id="tocscompanynamelookupresponsedto"></a>

```json
{
  "isin": "string",
  "tickr": "string",
  "bseScripCode": 0,
  "longName": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isin|string|false|none|none|
|tickr|string|false|none|none|
|bseScripCode|integer(int32)|false|none|none|
|longName|string|false|none|none|

<h2 id="tocS_UserFileUploadPermissionsResponseDto">UserFileUploadPermissionsResponseDto</h2>

<a id="schemauserfileuploadpermissionsresponsedto"></a>
<a id="schema_UserFileUploadPermissionsResponseDto"></a>
<a id="tocSuserfileuploadpermissionsresponsedto"></a>
<a id="tocsuserfileuploadpermissionsresponsedto"></a>

```json
{
  "isFileUploadAllowed": true,
  "totalStockCountAllowedToTrack": 0,
  "isUserOnTrialPlan": true,
  "currentUserPlan": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|isFileUploadAllowed|boolean|false|none|none|
|totalStockCountAllowedToTrack|integer(int32)|false|none|none|
|isUserOnTrialPlan|boolean|false|none|none|
|currentUserPlan|string|false|none|none|

<h2 id="tocS_SseEmitter">SseEmitter</h2>

<a id="schemasseemitter"></a>
<a id="schema_SseEmitter"></a>
<a id="tocSsseemitter"></a>
<a id="tocssseemitter"></a>

```json
{
  "timeout": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|timeout|integer(int64)|false|none|none|

<h2 id="tocS_BrokerDetail">BrokerDetail</h2>

<a id="schemabrokerdetail"></a>
<a id="schema_BrokerDetail"></a>
<a id="tocSbrokerdetail"></a>
<a id="tocsbrokerdetail"></a>

```json
{
  "id": 0,
  "aka": "string",
  "company": "string",
  "symbol": "string",
  "gatewayHoldingSupported": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer(int32)|false|none|none|
|aka|string|false|none|none|
|company|string|false|none|none|
|symbol|string|false|none|none|
|gatewayHoldingSupported|boolean|false|none|none|

<h2 id="tocS_PageUserAdminLookupResponseDto">PageUserAdminLookupResponseDto</h2>

<a id="schemapageuseradminlookupresponsedto"></a>
<a id="schema_PageUserAdminLookupResponseDto"></a>
<a id="tocSpageuseradminlookupresponsedto"></a>
<a id="tocspageuseradminlookupresponsedto"></a>

```json
{
  "totalElements": 0,
  "totalPages": 0,
  "size": 0,
  "content": [
    {
      "id": 0,
      "userId": "string",
      "countryCode": "string",
      "mobileNumber": "string",
      "name": "string",
      "emailId": "string",
      "planType": "TRIAL",
      "creationTime": 0,
      "userPlanExpiryDate": "string",
      "isUserProfilingComplete": true,
      "noOfTrackedCompanies": 0,
      "companyImportMechanism": "string",
      "referredBy": "string",
      "referredSource": "string",
      "companyName": "string",
      "designation": "string",
      "companyProfile": "string",
      "stockTrackingLimit": 0,
      "userPrivileged": true,
      "emailVerified": true
    }
  ],
  "number": 0,
  "sort": {
    "empty": true,
    "sorted": true,
    "unsorted": true
  },
  "pageable": {
    "offset": 0,
    "sort": {
      "empty": true,
      "sorted": true,
      "unsorted": true
    },
    "pageNumber": 0,
    "pageSize": 0,
    "paged": true,
    "unpaged": true
  },
  "numberOfElements": 0,
  "first": true,
  "last": true,
  "empty": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|totalElements|integer(int64)|false|none|none|
|totalPages|integer(int32)|false|none|none|
|size|integer(int32)|false|none|none|
|content|[[UserAdminLookupResponseDto](#schemauseradminlookupresponsedto)]|false|none|none|
|number|integer(int32)|false|none|none|
|sort|[SortObject](#schemasortobject)|false|none|none|
|pageable|[PageableObject](#schemapageableobject)|false|none|none|
|numberOfElements|integer(int32)|false|none|none|
|first|boolean|false|none|none|
|last|boolean|false|none|none|
|empty|boolean|false|none|none|

<h2 id="tocS_UserAdminLookupResponseDto">UserAdminLookupResponseDto</h2>

<a id="schemauseradminlookupresponsedto"></a>
<a id="schema_UserAdminLookupResponseDto"></a>
<a id="tocSuseradminlookupresponsedto"></a>
<a id="tocsuseradminlookupresponsedto"></a>

```json
{
  "id": 0,
  "userId": "string",
  "countryCode": "string",
  "mobileNumber": "string",
  "name": "string",
  "emailId": "string",
  "planType": "TRIAL",
  "creationTime": 0,
  "userPlanExpiryDate": "string",
  "isUserProfilingComplete": true,
  "noOfTrackedCompanies": 0,
  "companyImportMechanism": "string",
  "referredBy": "string",
  "referredSource": "string",
  "companyName": "string",
  "designation": "string",
  "companyProfile": "string",
  "stockTrackingLimit": 0,
  "userPrivileged": true,
  "emailVerified": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer(int64)|false|none|none|
|userId|string|false|none|none|
|countryCode|string|false|none|none|
|mobileNumber|string|false|none|none|
|name|string|false|none|none|
|emailId|string|false|none|none|
|planType|string|false|none|none|
|creationTime|integer(int64)|false|none|none|
|userPlanExpiryDate|string|false|none|none|
|isUserProfilingComplete|boolean|false|none|none|
|noOfTrackedCompanies|integer(int64)|false|none|none|
|companyImportMechanism|string|false|none|none|
|referredBy|string|false|none|none|
|referredSource|string|false|none|none|
|companyName|string|false|none|none|
|designation|string|false|none|none|
|companyProfile|string|false|none|none|
|stockTrackingLimit|integer(int32)|false|none|none|
|userPrivileged|boolean|false|none|none|
|emailVerified|boolean|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|planType|TRIAL|
|planType|TRIAL_EXPIRED|
|planType|PAID_BASIC|
|planType|PAID_PROFESSIONAL|
|planType|PAID_POWER_USER|
|planType|TRIAL_BASIC|
|planType|TRIAL_PROFESSIONAL|
|planType|TRIAL_POWER_USER|
|planType|FREE|

<h2 id="tocS_CumulativeTrackedInstrumentResponseDto">CumulativeTrackedInstrumentResponseDto</h2>

<a id="schemacumulativetrackedinstrumentresponsedto"></a>
<a id="schema_CumulativeTrackedInstrumentResponseDto"></a>
<a id="tocScumulativetrackedinstrumentresponsedto"></a>
<a id="tocscumulativetrackedinstrumentresponsedto"></a>

```json
{
  "totalInstruments": 0,
  "trackedInstruments": [
    {
      "subscriptionId": 0,
      "isin": "string",
      "tickr": "string",
      "name": "string",
      "source": "MANUAL"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|totalInstruments|integer(int32)|false|none|none|
|trackedInstruments|[[TrackedInstrumentsResponseDto](#schematrackedinstrumentsresponsedto)]|false|none|none|

<h2 id="tocS_BrokerSignupRequestDto">BrokerSignupRequestDto</h2>

<a id="schemabrokersignuprequestdto"></a>
<a id="schema_BrokerSignupRequestDto"></a>
<a id="tocSbrokersignuprequestdto"></a>
<a id="tocsbrokersignuprequestdto"></a>

```json
{
  "mobileNo": "string",
  "countryCode": "string",
  "brokerName": "string",
  "source": "string",
  "creationTime": 0,
  "userSignupStatusAtTimeOfRequest": "NEW",
  "stockUploadStatus": "NA",
  "requestStatus": "SUBMITTED",
  "brokerId": "PMSECURITIES",
  "userId": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|mobileNo|string|false|none|none|
|countryCode|string|false|none|none|
|brokerName|string|false|none|none|
|source|string|false|none|none|
|creationTime|integer(int64)|false|none|none|
|userSignupStatusAtTimeOfRequest|string|false|none|none|
|stockUploadStatus|string|false|none|none|
|requestStatus|string|false|none|none|
|brokerId|string|false|none|none|
|userId|integer(int64)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|userSignupStatusAtTimeOfRequest|NEW|
|userSignupStatusAtTimeOfRequest|EXISTING|
|stockUploadStatus|NA|
|stockUploadStatus|PENDING|
|stockUploadStatus|UPLOADED|
|requestStatus|SUBMITTED|
|requestStatus|COMPLETED|
|brokerId|PMSECURITIES|
|brokerId|ABANS_SECURITIES|
|brokerId|AJAY_JAIN|
|brokerId|ALACRITY_SECURITIES|
|brokerId|ALDAN_INVESTMENTS|
|brokerId|ALLWIN_SECURITIES|
|brokerId|AMIT_SAHITA_SEC|
|brokerId|ANANT_INVESTMENTS|
|brokerId|ASHISH_VAID|
|brokerId|ASIAN_BROKING|
|brokerId|AXIOM_BROKING|
|brokerId|BD_SHAH_SECURITIES|
|brokerId|BD_SHROFF_SECURITIES|
|brokerId|BAJAJ_SHARES|
|brokerId|BIGCAPITA_SECURITIES|
|brokerId|CHIMANLAL_MANEKLAL_SECURITIES|
|brokerId|CHURIWALA_SECURITIES|
|brokerId|CROSSEAS_CAPITAL_SERVICES|
|brokerId|DALAL_BROACHA_STOCK_BROKING|
|brokerId|DARASHAW_COMPANY|
|brokerId|DEEP_FINANCIAL_CONSULTANTS|
|brokerId|DHANKI_SECURITIES|
|brokerId|DHARAMSHI_SECURITIES|
|brokerId|DHWAJA_SHARES|
|brokerId|DHYAN_STOCKS|
|brokerId|ELIXIR_EQUITIES|
|brokerId|FIRST_INDIA_SECURITIES|
|brokerId|GNG_INVESTMENTS|
|brokerId|GHANSHYAM_SHARES_STOCK_BROKERS|
|brokerId|HARENDRA_D_MEHTA_SHARE_AND_STOCK_BROKER|
|brokerId|HARJIVANDAS_NEMIDAS_SECURITIES|
|brokerId|HORNIC_INVESTMENT|
|brokerId|INA_STOCK_BROKING|
|brokerId|JAS_ONE_SECURITIES|
|brokerId|JMP_SECURITIES|
|brokerId|RRS_SHARES_STOCK_BROKERS|
|brokerId|KAI_SECURITIES|
|brokerId|KALASH_SHARES|
|brokerId|KANTILAL_CHHAGANLAL_SEC|
|brokerId|KAUSHIK_SHAH_SHARES_SECURITIES|
|brokerId|KAVIRAJ_SECURITIES|
|brokerId|KIMAYA_SECURITIES|
|brokerId|LOTUS_GLOBAL_EQUITIES|
|brokerId|LPC_SECURITIES|
|brokerId|MD_SHUKLA_SHARE_AND_SECURITIES|
|brokerId|MJ_PATEL_SHARE|
|brokerId|VC_MEHTA|
|brokerId|MACY_SECURITIES|
|brokerId|MACY_SHARES_AND_STOCK_BROKERS|
|brokerId|MANUBHAI_MANGALDAS_SEC|
|brokerId|MANYOG_SECURITIES|
|brokerId|MARKETWOLF_SECURITIES|
|brokerId|MAXIMUS_SECURITIES|
|brokerId|MDN_SHARES_AND_STOCK_BROKERS|
|brokerId|MEHTA_VAKIL|
|brokerId|MESH_STOCK_BROKERS|
|brokerId|MUKUL_AMRUTLAL_SONAWALA|
|brokerId|NANGALIA_STOCK_BROKING|
|brokerId|PSURYAKANT_SHARE_STOCK_BROKERS|
|brokerId|PAVAK_SECURITIES|
|brokerId|PRAKASH_K_SHAH_SHARES_SECURITIES|
|brokerId|PRAKASH_SECURITIES|
|brokerId|PRARAMBH_SECURITIES|
|brokerId|PRL_STOCK_AND_SHARE_BROKERS|
|brokerId|RN_PATWA_SHARES_STOCK_BROKERS|
|brokerId|RAMESH_DAMANI|
|brokerId|RASHI_EQUISEARCH|
|brokerId|SHARAD_AGARWAL_BROKING_SERVICES|
|brokerId|SHREE_NAMAN_SECURITIES|
|brokerId|SHREEHARI_SHARES_AND_STOCK_BROKERS|
|brokerId|SURESH_KHANDELWAL|
|brokerId|TRUSTED_SHARES_INVESTMENTS|
|brokerId|UNIQUE_STOCKBRO|
|brokerId|UPMOVE_FINANCIAL_TECHNOLOGIES|
|brokerId|WELATHMILLS_SECURITIES|
|brokerId|YOGEN_BABU_SECURITIES|
|brokerId|CHOICE_BROKING|

<h2 id="tocS_PageBrokerSignupRequestDto">PageBrokerSignupRequestDto</h2>

<a id="schemapagebrokersignuprequestdto"></a>
<a id="schema_PageBrokerSignupRequestDto"></a>
<a id="tocSpagebrokersignuprequestdto"></a>
<a id="tocspagebrokersignuprequestdto"></a>

```json
{
  "totalElements": 0,
  "totalPages": 0,
  "size": 0,
  "content": [
    {
      "mobileNo": "string",
      "countryCode": "string",
      "brokerName": "string",
      "source": "string",
      "creationTime": 0,
      "userSignupStatusAtTimeOfRequest": "NEW",
      "stockUploadStatus": "NA",
      "requestStatus": "SUBMITTED",
      "brokerId": "PMSECURITIES",
      "userId": 0
    }
  ],
  "number": 0,
  "sort": {
    "empty": true,
    "sorted": true,
    "unsorted": true
  },
  "pageable": {
    "offset": 0,
    "sort": {
      "empty": true,
      "sorted": true,
      "unsorted": true
    },
    "pageNumber": 0,
    "pageSize": 0,
    "paged": true,
    "unpaged": true
  },
  "numberOfElements": 0,
  "first": true,
  "last": true,
  "empty": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|totalElements|integer(int64)|false|none|none|
|totalPages|integer(int32)|false|none|none|
|size|integer(int32)|false|none|none|
|content|[[BrokerSignupRequestDto](#schemabrokersignuprequestdto)]|false|none|none|
|number|integer(int32)|false|none|none|
|sort|[SortObject](#schemasortobject)|false|none|none|
|pageable|[PageableObject](#schemapageableobject)|false|none|none|
|numberOfElements|integer(int32)|false|none|none|
|first|boolean|false|none|none|
|last|boolean|false|none|none|
|empty|boolean|false|none|none|

<h2 id="tocS_SentMessage">SentMessage</h2>

<a id="schemasentmessage"></a>
<a id="schema_SentMessage"></a>
<a id="tocSsentmessage"></a>
<a id="tocssentmessage"></a>

```json
{
  "messageSentReceipt": "string",
  "id": "string",
  "creationTime": 0,
  "messageType": "TRIAL_EXPIRY_REMINDER"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|messageSentReceipt|string|false|none|none|
|id|string|false|none|none|
|creationTime|integer(int64)|false|none|none|
|messageType|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|messageType|TRIAL_EXPIRY_REMINDER|
|messageType|TRIAL_EXPIRED|
|messageType|FREE_TRIAL_EXTENSION|
|messageType|FREE_TIER_TRANSITION_COMPLETE|

<h2 id="tocS_UserPaidPlanShiftSurvey">UserPaidPlanShiftSurvey</h2>

<a id="schemauserpaidplanshiftsurvey"></a>
<a id="schema_UserPaidPlanShiftSurvey"></a>
<a id="tocSuserpaidplanshiftsurvey"></a>
<a id="tocsuserpaidplanshiftsurvey"></a>

```json
{
  "uniqueSurveyRequestId": 0,
  "surveyId": "string",
  "userId": 0,
  "userType": "RETAIL_USER",
  "surveyName": "TRIAL_USER_FEEDBACK",
  "countryCode": "string",
  "mobileNumber": 0,
  "expiryDate": "2019-08-24",
  "surveyStatus": "CREATED",
  "noOfTimesTrialExpiryPendingRemindersToBeSent": 0,
  "noOfTimesTrialExpiryPendingRemindersAlreadySent": 0,
  "lastTrialExpiryPendingReminderSentTime": 0,
  "scheduledNextMessageTime": 0,
  "scheduledNextMessageType": "TRIAL_EXPIRY_REMINDER",
  "sentMessageLog": [
    {
      "messageSentReceipt": "string",
      "id": "string",
      "creationTime": 0,
      "messageType": "TRIAL_EXPIRY_REMINDER"
    }
  ],
  "noOfTimesTrialExpiryNotificationToBeSent": 0,
  "noOfTimesTrialExpiryNotificationAlreadySent": 0,
  "lastTrialExpiryNotificationSentTime": 0,
  "trialExpiryFirstResponse": "UPGRADE_NOW",
  "trialExpiryFirstResponseTime": 0,
  "trialExpirySecondResponse": "UPGRADE_NOW",
  "trialExpirySecondResponseTime": 0,
  "noOfTimesFreeTrialIntroToBeSent": 0,
  "noOfTimesFreeTrialIntroAlreadySent": 0,
  "freeTrialIntroLastSentTime": 0,
  "freeTrialSurveyResponse": "AGREE_TO_FREE_TRIAL",
  "freeTrialAckResponseTime": 0,
  "freeTierTransitionCompleteTime": 0,
  "noOfTimesFreeTrialExtensionDoneBeSent": 0,
  "noOfTimesFreeTrialExtensionAlreadySent": 0,
  "freeTrialExtensionLastSentTime": 0,
  "creationTime": 0,
  "userPaidMarkTime": 0,
  "createdByUserId": 0,
  "isFinalReminder": true,
  "scheduledMessageToBeSent": "TRIAL_EXPIRY_REMINDER",
  "surveyTerminated": true,
  "trialExpiredNotificationFirstResponseAlreadyRegistered": true,
  "trialExpiredNotificationSecondResponseAlreadyRegistered": true,
  "freeTrialExtensionResponseFirstResponseAlreadyRegistered": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|uniqueSurveyRequestId|integer(int64)|false|none|none|
|surveyId|string|false|none|none|
|userId|integer(int64)|false|none|none|
|userType|string|false|none|none|
|surveyName|string|false|none|none|
|countryCode|string|false|none|none|
|mobileNumber|integer(int64)|false|none|none|
|expiryDate|string(date)|false|none|none|
|surveyStatus|string|false|none|none|
|noOfTimesTrialExpiryPendingRemindersToBeSent|integer(int32)|false|none|none|
|noOfTimesTrialExpiryPendingRemindersAlreadySent|integer(int32)|false|none|none|
|lastTrialExpiryPendingReminderSentTime|integer(int64)|false|none|none|
|scheduledNextMessageTime|integer(int64)|false|none|none|
|scheduledNextMessageType|string|false|none|none|
|sentMessageLog|[[SentMessage](#schemasentmessage)]|false|none|none|
|noOfTimesTrialExpiryNotificationToBeSent|integer(int32)|false|none|none|
|noOfTimesTrialExpiryNotificationAlreadySent|integer(int32)|false|none|none|
|lastTrialExpiryNotificationSentTime|integer(int64)|false|none|none|
|trialExpiryFirstResponse|string|false|none|none|
|trialExpiryFirstResponseTime|integer(int64)|false|none|none|
|trialExpirySecondResponse|string|false|none|none|
|trialExpirySecondResponseTime|integer(int64)|false|none|none|
|noOfTimesFreeTrialIntroToBeSent|integer(int32)|false|none|none|
|noOfTimesFreeTrialIntroAlreadySent|integer(int32)|false|none|none|
|freeTrialIntroLastSentTime|integer(int64)|false|none|none|
|freeTrialSurveyResponse|string|false|none|none|
|freeTrialAckResponseTime|integer(int64)|false|none|none|
|freeTierTransitionCompleteTime|integer(int64)|false|none|none|
|noOfTimesFreeTrialExtensionDoneBeSent|integer(int32)|false|none|none|
|noOfTimesFreeTrialExtensionAlreadySent|integer(int32)|false|none|none|
|freeTrialExtensionLastSentTime|integer(int64)|false|none|none|
|creationTime|integer(int64)|false|none|none|
|userPaidMarkTime|integer(int64)|false|none|none|
|createdByUserId|integer(int64)|false|none|none|
|isFinalReminder|boolean|false|none|none|
|scheduledMessageToBeSent|string|false|none|none|
|surveyTerminated|boolean|false|none|none|
|trialExpiredNotificationFirstResponseAlreadyRegistered|boolean|false|none|none|
|trialExpiredNotificationSecondResponseAlreadyRegistered|boolean|false|none|none|
|freeTrialExtensionResponseFirstResponseAlreadyRegistered|boolean|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|userType|RETAIL_USER|
|userType|PMS|
|surveyName|TRIAL_USER_FEEDBACK|
|surveyName|CONVERT_TRIAL_TO_PAID_SURVEY_CASUAL|
|surveyName|CONVERT_TRIAL_TO_PAID_SURVEY_CORPORATE|
|surveyName|FLASH_SALE|
|surveyName|FESTIVE_DISCOUNT|
|surveyStatus|CREATED|
|surveyStatus|PENDING_TRIAL_EXPIRY_NOTIFIED|
|surveyStatus|USER_PAID|
|surveyStatus|TRIAL_EXPIRED_NOTIFIED|
|surveyStatus|TRIAL_EXPIRED_ACK|
|surveyStatus|FREE_TRIAL_NOTIFIED|
|surveyStatus|FREE_TRIAL_EXTENSION_ACK|
|surveyStatus|FREE_TIER_TRANSITIONED|
|surveyStatus|USER_UNSUBSCRIBED|
|scheduledNextMessageType|TRIAL_EXPIRY_REMINDER|
|scheduledNextMessageType|TRIAL_EXPIRED|
|scheduledNextMessageType|FREE_TRIAL_EXTENSION|
|scheduledNextMessageType|FREE_TIER_TRANSITION_COMPLETE|
|trialExpiryFirstResponse|UPGRADE_NOW|
|trialExpiryFirstResponse|DONT_WANT_TO_UPGRADE|
|trialExpiryFirstResponse|PAYMENT_ISSUE|
|trialExpiryFirstResponse|PRICING_FEEDBACK|
|trialExpiryFirstResponse|NOT_USEFUL_FEEDBACK|
|trialExpiryFirstResponse|OTHER_FEEDBACK|
|trialExpirySecondResponse|UPGRADE_NOW|
|trialExpirySecondResponse|DONT_WANT_TO_UPGRADE|
|trialExpirySecondResponse|PAYMENT_ISSUE|
|trialExpirySecondResponse|PRICING_FEEDBACK|
|trialExpirySecondResponse|NOT_USEFUL_FEEDBACK|
|trialExpirySecondResponse|OTHER_FEEDBACK|
|freeTrialSurveyResponse|AGREE_TO_FREE_TRIAL|
|freeTrialSurveyResponse|UPGRADE_TO_PAID|
|freeTrialSurveyResponse|STOP_NOTIFICATION|
|scheduledMessageToBeSent|TRIAL_EXPIRY_REMINDER|
|scheduledMessageToBeSent|TRIAL_EXPIRED|
|scheduledMessageToBeSent|FREE_TRIAL_EXTENSION|
|scheduledMessageToBeSent|FREE_TIER_TRANSITION_COMPLETE|

<h2 id="tocS_InstrumentUpdateResponseDto">InstrumentUpdateResponseDto</h2>

<a id="schemainstrumentupdateresponsedto"></a>
<a id="schema_InstrumentUpdateResponseDto"></a>
<a id="tocSinstrumentupdateresponsedto"></a>
<a id="tocsinstrumentupdateresponsedto"></a>

```json
{
  "id": 0,
  "upstreamMessageId": "string",
  "scripCode": "string",
  "scripName": "string",
  "isin": "string",
  "updateTypeRaw": "string",
  "updateSubTypeRaw": "string",
  "updateType": "CORPORATE_ANNOUNCEMENT",
  "sourceRaw": "string",
  "header": "string",
  "title": "string",
  "body": "string",
  "creationTime": 0,
  "noOfUsersToBeBroadcastTo": 0,
  "messageStatus": "UNPROCESSED",
  "failureReason": "string",
  "effectiveLink": "string",
  "intendedAudiences": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer(int64)|false|none|none|
|upstreamMessageId|string|false|none|none|
|scripCode|string|false|none|none|
|scripName|string|false|none|none|
|isin|string|false|none|none|
|updateTypeRaw|string|false|none|none|
|updateSubTypeRaw|string|false|none|none|
|updateType|string|false|none|none|
|sourceRaw|string|false|none|none|
|header|string|false|none|none|
|title|string|false|none|none|
|body|string|false|none|none|
|creationTime|integer(int64)|false|none|none|
|noOfUsersToBeBroadcastTo|integer(int32)|false|none|none|
|messageStatus|string|false|none|none|
|failureReason|string|false|none|none|
|effectiveLink|string|false|none|none|
|intendedAudiences|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|updateType|CORPORATE_ANNOUNCEMENT|
|updateType|TECHNICAL_ANALYSIS|
|updateType|GENERAL_NEWS|
|updateType|TELEGRAM|
|updateType|TWEET|
|updateType|BULLETIN|
|updateType|RSS|
|updateType|CONCALL_HIGHLIGHTS|
|updateType|CONCALL_SUMMARY|
|updateType|FUTURE_OUTLOOK|
|updateType|BULK_BLOCK|
|updateType|SQ_SPVMA_INTRADAY_VOLUME_SPURT|
|updateType|ANALYST_VIEWS|
|messageStatus|UNPROCESSED|
|messageStatus|PROCESSED|
|messageStatus|FAILURE|

<h2 id="tocS_PageInstrumentUpdateResponseDto">PageInstrumentUpdateResponseDto</h2>

<a id="schemapageinstrumentupdateresponsedto"></a>
<a id="schema_PageInstrumentUpdateResponseDto"></a>
<a id="tocSpageinstrumentupdateresponsedto"></a>
<a id="tocspageinstrumentupdateresponsedto"></a>

```json
{
  "totalElements": 0,
  "totalPages": 0,
  "size": 0,
  "content": [
    {
      "id": 0,
      "upstreamMessageId": "string",
      "scripCode": "string",
      "scripName": "string",
      "isin": "string",
      "updateTypeRaw": "string",
      "updateSubTypeRaw": "string",
      "updateType": "CORPORATE_ANNOUNCEMENT",
      "sourceRaw": "string",
      "header": "string",
      "title": "string",
      "body": "string",
      "creationTime": 0,
      "noOfUsersToBeBroadcastTo": 0,
      "messageStatus": "UNPROCESSED",
      "failureReason": "string",
      "effectiveLink": "string",
      "intendedAudiences": "string"
    }
  ],
  "number": 0,
  "sort": {
    "empty": true,
    "sorted": true,
    "unsorted": true
  },
  "pageable": {
    "offset": 0,
    "sort": {
      "empty": true,
      "sorted": true,
      "unsorted": true
    },
    "pageNumber": 0,
    "pageSize": 0,
    "paged": true,
    "unpaged": true
  },
  "numberOfElements": 0,
  "first": true,
  "last": true,
  "empty": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|totalElements|integer(int64)|false|none|none|
|totalPages|integer(int32)|false|none|none|
|size|integer(int32)|false|none|none|
|content|[[InstrumentUpdateResponseDto](#schemainstrumentupdateresponsedto)]|false|none|none|
|number|integer(int32)|false|none|none|
|sort|[SortObject](#schemasortobject)|false|none|none|
|pageable|[PageableObject](#schemapageableobject)|false|none|none|
|numberOfElements|integer(int32)|false|none|none|
|first|boolean|false|none|none|
|last|boolean|false|none|none|
|empty|boolean|false|none|none|

<h2 id="tocS_InstrumentDetailSnapshotResponseDto">InstrumentDetailSnapshotResponseDto</h2>

<a id="schemainstrumentdetailsnapshotresponsedto"></a>
<a id="schema_InstrumentDetailSnapshotResponseDto"></a>
<a id="tocSinstrumentdetailsnapshotresponsedto"></a>
<a id="tocsinstrumentdetailsnapshotresponsedto"></a>

```json
{
  "totalBseInstrumentCount": 0,
  "totalNseInstrumentCount": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|totalBseInstrumentCount|integer(int64)|false|none|none|
|totalNseInstrumentCount|integer(int64)|false|none|none|

<h2 id="tocS_InstrumentFileUploadLogResponseDto">InstrumentFileUploadLogResponseDto</h2>

<a id="schemainstrumentfileuploadlogresponsedto"></a>
<a id="schema_InstrumentFileUploadLogResponseDto"></a>
<a id="tocSinstrumentfileuploadlogresponsedto"></a>
<a id="tocsinstrumentfileuploadlogresponsedto"></a>

```json
{
  "id": 0,
  "fileName": "string",
  "countOfCompaniesBefore": 0,
  "countOfCompaniesAfter": 0,
  "timeTaken": 0,
  "creationTime": 0,
  "scripFileDate": "string",
  "result": "SUCCESS",
  "reason": "string",
  "userId": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer(int64)|false|none|none|
|fileName|string|false|none|none|
|countOfCompaniesBefore|integer(int64)|false|none|none|
|countOfCompaniesAfter|integer(int64)|false|none|none|
|timeTaken|integer(int64)|false|none|none|
|creationTime|integer(int64)|false|none|none|
|scripFileDate|string|false|none|none|
|result|string|false|none|none|
|reason|string|false|none|none|
|userId|integer(int64)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|result|SUCCESS|
|result|FAILURE|

<h2 id="tocS_PageCorporateDomainResponseDto">PageCorporateDomainResponseDto</h2>

<a id="schemapagecorporatedomainresponsedto"></a>
<a id="schema_PageCorporateDomainResponseDto"></a>
<a id="tocSpagecorporatedomainresponsedto"></a>
<a id="tocspagecorporatedomainresponsedto"></a>

```json
{
  "totalElements": 0,
  "totalPages": 0,
  "size": 0,
  "content": [
    {
      "id": "string",
      "domain": "string",
      "website": "string",
      "companyName": "string",
      "industry": "string",
      "creationTime": 0,
      "budgetForFreeUser": 0,
      "status": "PRIVILEGED",
      "companyId": 0,
      "userCount": 0
    }
  ],
  "number": 0,
  "sort": {
    "empty": true,
    "sorted": true,
    "unsorted": true
  },
  "pageable": {
    "offset": 0,
    "sort": {
      "empty": true,
      "sorted": true,
      "unsorted": true
    },
    "pageNumber": 0,
    "pageSize": 0,
    "paged": true,
    "unpaged": true
  },
  "numberOfElements": 0,
  "first": true,
  "last": true,
  "empty": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|totalElements|integer(int64)|false|none|none|
|totalPages|integer(int32)|false|none|none|
|size|integer(int32)|false|none|none|
|content|[[CorporateDomainResponseDto](#schemacorporatedomainresponsedto)]|false|none|none|
|number|integer(int32)|false|none|none|
|sort|[SortObject](#schemasortobject)|false|none|none|
|pageable|[PageableObject](#schemapageableobject)|false|none|none|
|numberOfElements|integer(int32)|false|none|none|
|first|boolean|false|none|none|
|last|boolean|false|none|none|
|empty|boolean|false|none|none|

<h2 id="tocS_BseDataFetchResponseDto">BseDataFetchResponseDto</h2>

<a id="schemabsedatafetchresponsedto"></a>
<a id="schema_BseDataFetchResponseDto"></a>
<a id="tocSbsedatafetchresponsedto"></a>
<a id="tocsbsedatafetchresponsedto"></a>

```json
{
  "Table": [
    {}
  ],
  "Table1": [
    {}
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|Table|[[JsonNode](#schemajsonnode)]|false|none|none|
|Table1|[[JsonNode](#schemajsonnode)]|false|none|none|

<h2 id="tocS_AnalyticsUnitDto">AnalyticsUnitDto</h2>

<a id="schemaanalyticsunitdto"></a>
<a id="schema_AnalyticsUnitDto"></a>
<a id="tocSanalyticsunitdto"></a>
<a id="tocsanalyticsunitdto"></a>

```json
{
  "date": "string",
  "count": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|date|string|false|none|none|
|count|integer(int64)|false|none|none|

<h2 id="tocS_DashboardAnalyticsDto">DashboardAnalyticsDto</h2>

<a id="schemadashboardanalyticsdto"></a>
<a id="schema_DashboardAnalyticsDto"></a>
<a id="tocSdashboardanalyticsdto"></a>
<a id="tocsdashboardanalyticsdto"></a>

```json
{
  "fromDate": "string",
  "totalSignedUpUsers": 0,
  "totalPaidSignedUpUsers": 0,
  "totalActiveMandates": 0,
  "signedUpUsersPerDay": [
    {
      "date": "string",
      "count": 0
    }
  ],
  "signedUpUsersPerMonth": [
    {
      "date": "string",
      "count": 0
    }
  ],
  "noOfUsersToWhomUpdatesSentPerDay": [
    {
      "date": "string",
      "count": 0
    }
  ],
  "messagesSent": [
    {
      "breakdown": [
        {
          "type": "string",
          "source": "string",
          "count": 0
        }
      ],
      "date": "string"
    }
  ],
  "messagesSentByType": [
    {
      "type": "string",
      "breakdown": [
        {
          "date": "string",
          "count": 0
        }
      ]
    }
  ],
  "messagesReceived": [
    {
      "breakdown": [
        {
          "type": "string",
          "source": "string",
          "count": 0
        }
      ],
      "date": "string"
    }
  ],
  "messagesReceivedByType": [
    {
      "type": "string",
      "breakdown": [
        {
          "date": "string",
          "count": 0
        }
      ]
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|fromDate|string|false|none|none|
|totalSignedUpUsers|integer(int64)|false|none|none|
|totalPaidSignedUpUsers|integer(int64)|false|none|none|
|totalActiveMandates|integer(int64)|false|none|none|
|signedUpUsersPerDay|[[AnalyticsUnitDto](#schemaanalyticsunitdto)]|false|none|none|
|signedUpUsersPerMonth|[[AnalyticsUnitDto](#schemaanalyticsunitdto)]|false|none|none|
|noOfUsersToWhomUpdatesSentPerDay|[[AnalyticsUnitDto](#schemaanalyticsunitdto)]|false|none|none|
|messagesSent|[[MessageTypeBreakdownDto](#schemamessagetypebreakdowndto)]|false|none|none|
|messagesSentByType|[[MessageTypeAnalyticsBeta](#schemamessagetypeanalyticsbeta)]|false|none|none|
|messagesReceived|[[MessageTypeBreakdownDto](#schemamessagetypebreakdowndto)]|false|none|none|
|messagesReceivedByType|[[MessageTypeAnalyticsBeta](#schemamessagetypeanalyticsbeta)]|false|none|none|

<h2 id="tocS_IndividualMessageTypeDto">IndividualMessageTypeDto</h2>

<a id="schemaindividualmessagetypedto"></a>
<a id="schema_IndividualMessageTypeDto"></a>
<a id="tocSindividualmessagetypedto"></a>
<a id="tocsindividualmessagetypedto"></a>

```json
{
  "type": "string",
  "source": "string",
  "count": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|false|none|none|
|source|string|false|none|none|
|count|integer(int64)|false|none|none|

<h2 id="tocS_MessageTypeAnalyticsBeta">MessageTypeAnalyticsBeta</h2>

<a id="schemamessagetypeanalyticsbeta"></a>
<a id="schema_MessageTypeAnalyticsBeta"></a>
<a id="tocSmessagetypeanalyticsbeta"></a>
<a id="tocsmessagetypeanalyticsbeta"></a>

```json
{
  "type": "string",
  "breakdown": [
    {
      "date": "string",
      "count": 0
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|false|none|none|
|breakdown|[[AnalyticsUnitDto](#schemaanalyticsunitdto)]|false|none|none|

<h2 id="tocS_MessageTypeBreakdownDto">MessageTypeBreakdownDto</h2>

<a id="schemamessagetypebreakdowndto"></a>
<a id="schema_MessageTypeBreakdownDto"></a>
<a id="tocSmessagetypebreakdowndto"></a>
<a id="tocsmessagetypebreakdowndto"></a>

```json
{
  "breakdown": [
    {
      "type": "string",
      "source": "string",
      "count": 0
    }
  ],
  "date": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|breakdown|[[IndividualMessageTypeDto](#schemaindividualmessagetypedto)]|false|none|none|
|date|string|false|none|none|

