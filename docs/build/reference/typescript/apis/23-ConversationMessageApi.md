---
title: ConversationMessage API | TypeScript SDK
---

# ConversationMessage API

All URIs are relative to `http://localhost:1000`

Method | HTTP request | Description
------------- | ------------- | -------------
[**messageAssociateAnnotation**](ConversationMessageApi#messageassociateannotation) | **POST** /message/\{message\}/annotations/associate/\{annotation\} | /message/\{message\}/annotations/associate/\{annotation\} [POST]
[**messageDisassociateAnnotation**](ConversationMessageApi#messagedisassociateannotation) | **POST** /message/\{message\}/annotations/disassociate/\{annotation\} | /message/\{message\}/annotations/disassociate/\{annotation\} [POST]
[**messageScoresIncrement**](ConversationMessageApi#messagescoresincrement) | **POST** /message/\{message\}/scores/increment | \'/message/\{message\}/scores/increment\' [POST]
[**messageSpecificMessageSnapshot**](ConversationMessageApi#messagespecificmessagesnapshot) | **GET** /message/\{message\} | /message/\{message\} [GET]
[**messageSpecificMessageUpdate**](ConversationMessageApi#messagespecificmessageupdate) | **POST** /message/update | /message/update [GET]
[**messageUpdateValue**](ConversationMessageApi#messageupdatevalue) | **POST** /message/update/value | /message/update/value [POST]


## **messageAssociateAnnotation** {#messageassociateannotation}
> messageAssociateAnnotation()

This will associate a message with an annotation.

### Example {#messageassociateannotation-example}

```typescript
import * as Pieces from '@pieces.app/pieces-os-client'

const configuration = Pieces.Configuration()
const apiInstance = new Pieces.ConversationMessageApi(configuration)

const body: Pieces.MessageAssociateAnnotationRequest = {
// string | This is a specific annotation uuid.
annotation: annotation_example,
// string | This is the uuid of a message.
message: message_example,
};

apiInstance.messageAssociateAnnotation(body).then((data: void (empty response body)) => {
console.log('API called successfully. Returned data: ' + data)
}).catch((error: unknown) => console.error(error))
```

### Parameters {#messageassociateannotation-parameters}


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **annotation** | [**string**] | This is a specific annotation uuid. | defaults to undefined
 **message** | [**string**] | This is the uuid of a message. | defaults to undefined


### Return type {#messageassociateannotation-return-type}

void (empty response body)

### HTTP request headers {#messageassociateannotation-http-request-headers}

- **Content-Type**: Not defined
- **Accept**: text/plain


### HTTP response details {#messageassociateannotation-http-response-details}
| Status code | Description | Response headers
|-------------|-------------|------------------
**204** | No Content |  -  |
**500** | Internal Server Error |  -  |

## **messageDisassociateAnnotation** {#messagedisassociateannotation}
> messageDisassociateAnnotation()

This will enable us to dissassociate a message from an annotation.

### Example {#messagedisassociateannotation-example}

```typescript
import * as Pieces from '@pieces.app/pieces-os-client'

const configuration = Pieces.Configuration()
const apiInstance = new Pieces.ConversationMessageApi(configuration)

const body: Pieces.MessageDisassociateAnnotationRequest = {
// string | This is a specific annotation uuid.
annotation: annotation_example,
// string | This is the uuid of a message.
message: message_example,
};

apiInstance.messageDisassociateAnnotation(body).then((data: void (empty response body)) => {
console.log('API called successfully. Returned data: ' + data)
}).catch((error: unknown) => console.error(error))
```

### Parameters {#messagedisassociateannotation-parameters}


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **annotation** | [**string**] | This is a specific annotation uuid. | defaults to undefined
 **message** | [**string**] | This is the uuid of a message. | defaults to undefined


### Return type {#messagedisassociateannotation-return-type}

void (empty response body)

### HTTP request headers {#messagedisassociateannotation-http-request-headers}

- **Content-Type**: Not defined
- **Accept**: text/plain


### HTTP response details {#messagedisassociateannotation-http-response-details}
| Status code | Description | Response headers
|-------------|-------------|------------------
**204** | No Content |  -  |
**500** | Internal Server Error |  -  |

## **messageScoresIncrement** {#messagescoresincrement}
> messageScoresIncrement()

This will take in a SeededScoreIncrement and will increment the material relative to the incoming body.

### Example {#messagescoresincrement-example}

```typescript
import * as Pieces from '@pieces.app/pieces-os-client'

const configuration = Pieces.Configuration()
const apiInstance = new Pieces.ConversationMessageApi(configuration)

const body: Pieces.MessageScoresIncrementRequest = {
// string | This is the uuid of a message.
message: message_example,
// SeededScoreIncrement (optional)
seededScoreIncrement: ,
};

apiInstance.messageScoresIncrement(body).then((data: void (empty response body)) => {
console.log('API called successfully. Returned data: ' + data)
}).catch((error: unknown) => console.error(error))
```

### Parameters {#messagescoresincrement-parameters}


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **seededScoreIncrement** | **SeededScoreIncrement**|  |
 **message** | [**string**] | This is the uuid of a message. | defaults to undefined


### Return type {#messagescoresincrement-return-type}

void (empty response body)

### HTTP request headers {#messagescoresincrement-http-request-headers}

- **Content-Type**: application/json
- **Accept**: text/plain


### HTTP response details {#messagescoresincrement-http-response-details}
| Status code | Description | Response headers
|-------------|-------------|------------------
**204** | No Content |  -  |
**500** | Internal Server Error |  -  |

## **messageSpecificMessageSnapshot** {#messagespecificmessagesnapshot}
> ConversationMessage messageSpecificMessageSnapshot()

This will get a specific snapshot of a message

### Example {#messagespecificmessagesnapshot-example}

```typescript
import * as Pieces from '@pieces.app/pieces-os-client'

const configuration = Pieces.Configuration()
const apiInstance = new Pieces.ConversationMessageApi(configuration)

const body: Pieces.MessageSpecificMessageSnapshotRequest = {
// string | This is the uuid of a message.
message: message_example,
// boolean | This is a boolean that will decided if we are want to return the transferable data (default) or not(performance enhancement) (optional)
transferables: true,
};

apiInstance.messageSpecificMessageSnapshot(body).then((data: ConversationMessage) => {
console.log('API called successfully. Returned data: ' + data)
}).catch((error: unknown) => console.error(error))
```

### Parameters {#messagespecificmessagesnapshot-parameters}


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **message** | [**string**] | This is the uuid of a message. | defaults to undefined
 **transferables** | [**boolean**] | This is a boolean that will decided if we are want to return the transferable data (default) or not(performance enhancement) | (optional) defaults to undefined


### Return type {#messagespecificmessagesnapshot-return-type}

[**ConversationMessage**](../models/ConversationMessage)

### HTTP request headers {#messagespecificmessagesnapshot-http-request-headers}

- **Content-Type**: Not defined
- **Accept**: application/json, text/plain


### HTTP response details {#messagespecificmessagesnapshot-http-response-details}
| Status code | Description | Response headers
|-------------|-------------|------------------
**200** | OK |  -  |
**410** | Website not found. |  -  |

## **messageSpecificMessageUpdate** {#messagespecificmessageupdate}
> ConversationMessage messageSpecificMessageUpdate()

This will update a conversation message.

### Example {#messagespecificmessageupdate-example}

```typescript
import * as Pieces from '@pieces.app/pieces-os-client'

const configuration = Pieces.Configuration()
const apiInstance = new Pieces.ConversationMessageApi(configuration)

const body: Pieces.MessageSpecificMessageUpdateRequest = {
// boolean | This is a boolean that will decided if we are want to return the transferable data (default) or not(performance enhancement) (optional)
transferables: true,
// ConversationMessage (optional)
conversationMessage: ,
};

apiInstance.messageSpecificMessageUpdate(body).then((data: ConversationMessage) => {
console.log('API called successfully. Returned data: ' + data)
}).catch((error: unknown) => console.error(error))
```

### Parameters {#messagespecificmessageupdate-parameters}


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **conversationMessage** | **ConversationMessage**|  |
 **transferables** | [**boolean**] | This is a boolean that will decided if we are want to return the transferable data (default) or not(performance enhancement) | (optional) defaults to undefined


### Return type {#messagespecificmessageupdate-return-type}

[**ConversationMessage**](../models/ConversationMessage)

### HTTP request headers {#messagespecificmessageupdate-http-request-headers}

- **Content-Type**: application/json
- **Accept**: application/json, text/plain


### HTTP response details {#messagespecificmessageupdate-http-response-details}
| Status code | Description | Response headers
|-------------|-------------|------------------
**200** | OK |  -  |
**500** | Internal Server Error |  -  |

## **messageUpdateValue** {#messageupdatevalue}
> ConversationMessage messageUpdateValue()

This will update the value of a conversation message.

### Example {#messageupdatevalue-example}

```typescript
import * as Pieces from '@pieces.app/pieces-os-client'

const configuration = Pieces.Configuration()
const apiInstance = new Pieces.ConversationMessageApi(configuration)

const body: Pieces.MessageUpdateValueRequest = {
// boolean | This is a boolean that will decided if we are want to return the transferable data (default) or not(performance enhancement) (optional)
transferables: true,
// ConversationMessage (optional)
conversationMessage: ,
};

apiInstance.messageUpdateValue(body).then((data: ConversationMessage) => {
console.log('API called successfully. Returned data: ' + data)
}).catch((error: unknown) => console.error(error))
```

### Parameters {#messageupdatevalue-parameters}


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **conversationMessage** | **ConversationMessage**|  |
 **transferables** | [**boolean**] | This is a boolean that will decided if we are want to return the transferable data (default) or not(performance enhancement) | (optional) defaults to undefined


### Return type {#messageupdatevalue-return-type}

[**ConversationMessage**](../models/ConversationMessage)

### HTTP request headers {#messageupdatevalue-http-request-headers}

- **Content-Type**: application/json
- **Accept**: application/json, text/plain


### HTTP response details {#messageupdatevalue-http-response-details}
| Status code | Description | Response headers
|-------------|-------------|------------------
**200** | OK |  -  |
**500** | Internal Server Error |  -  |


