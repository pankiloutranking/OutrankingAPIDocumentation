# Outranking App Rest API

For all api, need to put apiKey in header like `{ apiKey : xxxxxxxxxxxxx }`

Rest Api URL : https://apps.outranking.io/api

## Get user details
Connect to your account and get your user details. 
### Request

`GET /user/`

    curl -i -H 'Accept: application/json' -H "Content-Type: application/json" -H "apiKey: xxxxx" https://apps.outranking.io/api/user/

### Response

    HTTP/1.1 200 OK

```json
{
    "status": "OK",
    "code": 200,
    "message": "success",
    "data": {
        "version": 1131,
        "createdOn": "2021-05-10T21:25:45.483+0000",
        "createdBy": null,
        "updatedOn": "2021-12-07T23:18:32.958+0000",
        "updatedBy": null,
        "active": "Yes",
        "userId": 10826,
        "email": "admin@vaadin.com",
        "passwordHash": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
        "firstName": "Göran",
        "lastName": "Rich",
        "role": "admin",
        "authProvider": "LOCAL",
        "locked": false,
        "parentId": null,
        "lastLogin": "2021-12-07T23:18:32.949+0000",
        "noOfLogin": 1128,
        "domain": "userpilot.com",
        "registered": true,
        "fullName": "Göran Rich",
        "comboName": "Göran Rich (admin@vaadin.com)"
    }
}
```
## 1. Get Documents 
Gets the list of documents in your account
### Request

`GET /documents/`

    curl -i -H 'Accept: application/json' -H "Content-Type: application/json" -H "apiKey: xxxxx" https://apps.outranking.io/api/documents?searchQuery=xxx&page=0&size=10
    
- searchQuery : keyword for searching document
- page : current page number  
- size : document number in one page

### Response

    HTTP/1.1 200 OK
    
```json
{
    "status": "OK",
    "code": 200,
    "message": "success",
    "data": [{
        "documentId": 110501,
        "documentName": "roadmap tools",
        "keyword": "roadmap tools",
        "location": "United States",
        "language": "English",
        "createdOn": "2021-11-29T05:00:49.354+0000",
        "score": ""
    }, {
        "documentId": 110336,
        "documentName": "definition of data structure",
        "keyword": "definition of data structure",
        "location": "United States",
        "language": "English",
        "createdOn": "2021-11-24T15:52:23.920+0000",
        "score": ""
    }, {
        "documentId": 110163,
        "documentName": "product roadmap visualization",
        "keyword": "product roadmap visualization",
        "location": "United States",
        "language": "English",
        "createdOn": "2021-11-22T17:56:49.811+0000",
        "score": ""
    }, {
        "documentId": 110107,
        "documentName": "roadmap visualization",
        "keyword": "roadmap visualization",
        "location": "United States",
        "language": "English",
        "createdOn": "2021-11-22T17:52:20.422+0000",
        "score": ""
    }, {
        "documentId": 110103,
        "documentName": "software roadmaps",
        "keyword": "software roadmaps",
        "location": "United States",
        "language": "English",
        "createdOn": "2021-11-22T17:52:10.361+0000",
        "score": ""
    }, {
        "documentId": 101360,
        "documentName": "tooltips in html",
        "keyword": "tooltips in html",
        "location": "United States",
        "language": "English",
        "createdOn": "2021-11-04T03:40:39.641+0000",
        "score": ""
    }, {
        "documentId": 101048,
        "documentName": "best roadmap",
        "keyword": "best roadmap",
        "location": "United States",
        "language": "English",
        "createdOn": "2021-11-03T22:32:18.414+0000",
        "score": ""
    }, {
        "documentId": 98486,
        "documentName": "big data databases",
        "keyword": "big data databases",
        "location": "United States",
        "language": "English",
        "createdOn": "2021-11-03T01:31:40.599+0000",
        "score": ""
    }, {
        "documentId": 90567,
        "documentName": "Samsun fold smartphone",
        "keyword": "Samsun fold smartphone",
        "location": "United States",
        "language": "English",
        "createdOn": "2021-10-27T17:40:10.193+0000",
        "score": ""
    }, {
        "documentId": 90495,
        "documentName": "query javascript",
        "keyword": "query javascript",
        "location": "United States",
        "language": "English",
        "createdOn": "2021-10-27T16:13:42.598+0000",
        "score": ""
    }],
    "page": 0,
    "size": 10,
    "totalPage": 12,
    "totalElement": 118
}
```

## Get document detail by id

### Request

`GET /document/{id}`

    curl -i -H 'Accept: application/json' -H "Content-Type: application/json" -H "apiKey: xxxxx" https://apps.outranking.io/api/document/90495
    
### Response

    HTTP/1.1 200 OK
    
```json
{
    "status": "OK",
    "code": 200,
    "message": "success",
    "data": {
        "version": 0,
        "createdOn": "2021-10-27T16:13:42.598+0000",
        "createdBy": null,
        "updatedOn": "2021-10-27T16:13:42.598+0000",
        "updatedBy": null,
        "active": "Yes",
        "documentId": 90495,
        "userId": 10826,
        "keyword": "query javascript",
        "location": "2840",
        "name": "query javascript",
        "content": "&lt;DOC_URL&gt;https://docs.mongodb.com/manual/reference/operator/query/where/&lt;/DOC_URL&gt;<br></br>&lt;META_TITLE&gt;$where — MongoDB Manual&lt;/META_TITLE&gt;",
        "status": "PUBLISHED",
        "tag": null,
        "contentDepth": "LOW",
        "keywordSuggestions": null,
        "outlineJsonData": null,
        "language": "en"
    }
}
```

## Update document by Id

### Request

`POST /document/{id}`

    curl -i -X POST -H 'Accept: application/json' -H "Content-Type: application/json" -H "apiKey: xxxxx" -d '{"status":"DRAFT"}' https://apps.outranking.io/api/document/90495
    
### Response

    HTTP/1.1 200 OK
    
```json
{
    "status": "OK",
    "code": 200,
    "message": "success",
    "data": {
        "version": 0,
        "createdOn": "2021-10-27T16:13:42.598+0000",
        "createdBy": null,
        "updatedOn": "2021-10-27T16:13:42.598+0000",
        "updatedBy": null,
        "active": "Yes",
        "documentId": 90495,
        "userId": 10826,
        "keyword": "query javascript",
        "location": "2840",
        "name": "query javascript",
        "content": "&lt;DOC_URL&gt;https://docs.mongodb.com/manual/reference/operator/query/where/&lt;/DOC_URL&gt;<br></br>&lt;META_TITLE&gt;$where — MongoDB Manual&lt;/META_TITLE&gt;",
        "status": "DRAFT",
        "tag": null,
        "contentDepth": "LOW",
        "keywordSuggestions": null,
        "outlineJsonData": null,
        "language": "en"
    }
}
```

## Update document content by Id

### Request

`POST /document/content/{id}`

    curl -i -X POST -H 'Accept: application/json' -H "Content-Type: application/json" -H "apiKey: xxxxx" -d '{"content":"xxxx"}' https://apps.outranking.io/api/document/content/90495
    
### Response

    HTTP/1.1 200 OK
    
```json
{
    "status": "OK",
    "code": 200,
    "message": "success",
    "data": 10
}
```
Data is score of content.

## 	Create document

### Request

`POST /document`

    curl -i -X POST -H 'Accept: application/json' -H "Content-Type: application/json" -H "apiKey: xxxxx" https://apps.outranking.io/api/document?keyword=query javascript&location=2840&language=en

- keyword : keyword for document. this will be document name
- location : location code for searching keyword. refer to location api  
- language : language code for searching keyword. refer to language api

### Response

    HTTP/1.1 200 OK
    
```json
{
    "status": "OK",
    "code": 200,
    "message": "success",
    "data": {
        "version": 0,
        "createdOn": "2021-10-27T16:13:42.598+0000",
        "createdBy": null,
        "updatedOn": "2021-10-27T16:13:42.598+0000",
        "updatedBy": null,
        "active": "Yes",
        "documentId": 90495,
        "userId": 10826,
        "keyword": "query javascript",
        "location": "2840",
        "name": "query javascript",
        "content": "&lt;DOC_URL&gt;https://docs.mongodb.com/manual/reference/operator/query/where/&lt;/DOC_URL&gt;<br></br>&lt;META_TITLE&gt;$where — MongoDB Manual&lt;/META_TITLE&gt;",
        "status": "DRAFT",
        "tag": null,
        "contentDepth": "LOW",
        "keywordSuggestions": null,
        "outlineJsonData": null,
        "language": "en"
    }
}
```

## 	Create document share link

### Request

`POST /documentShare/`

    curl -i -X POST -H 'Accept: application/json' -H "Content-Type: application/json" -H "apiKey: xxxxx" https://apps.outranking.io/api/documentshare?documentId=90495&isEditable=false

- documentId : document id to share
- isEditable : permission flag.  if it is true, document will be editable. if false, viewable only.  

    
### Response

    HTTP/1.1 200 OK
    
```json
{
    "status": "OK",
    "code": 200,
    "message": "success",
    "data": {
        "version": 0,
        "createdOn": "2021-12-08T15:50:49.241+0000",
        "createdBy": null,
        "updatedOn": "2021-12-08T15:50:49.241+0000",
        "updatedBy": null,
        "active": "Yes",
        "documentShareId": 110902,
        "documentId": 90495,
        "emailId": null,
        "description": "mytesting",
        "shareLink": "https://apps.outranking.io/document/seo/content/share/c9073448-efb0-4bbf-a2e6-62fc8c98c8ad",
        "shareCode": "c9073448-efb0-4bbf-a2e6-62fc8c98c8ad",
        "emailAddress": null,
        "editable": false,
        "viewable": true
    }
}
```


## 	Get all languages

### Request

`GET /languages/`

    curl -i -H 'Accept: application/json' -H "Content-Type: application/json" -H "apiKey: xxxxx" https://apps.outranking.io/api/languages
    
### Response

    HTTP/1.1 200 OK
    
```json
{
    "status": "OK",
    "code": 200,
    "message": "success",
    "data": [{
        "id": 1,
        "languageCode": "ar",
        "languageName": "Arabic"
    }, {
        "id": 2,
        "languageCode": "da",
        "languageName": "Danish"
    }, {
        "id": 3,
        "languageCode": "nl",
        "languageName": "Dutch"
    }, {
        "id": 4,
        "languageCode": "en",
        "languageName": "English"
    }, {
        "id": 5,
        "languageCode": "fi",
        "languageName": "Finnish"
    }, {
        "id": 6,
        "languageCode": "fr",
        "languageName": "French"
    }, {
        "id": 7,
        "languageCode": "de",
        "languageName": "German"
    }, {
        "id": 8,
        "languageCode": "el",
        "languageName": "Greek"
    }, {
        "id": 9,
        "languageCode": "it",
        "languageName": "Italian"
    }, {
        "id": 10,
        "languageCode": "pl",
        "languageName": "Polish"
    }, {
        "id": 11,
        "languageCode": "pt",
        "languageName": "Portuguese"
    }, {
        "id": 12,
        "languageCode": "ru",
        "languageName": "Russian"
    }, {
        "id": 13,
        "languageCode": "es",
        "languageName": "Spanish"
    }]
}
```

## 	Search locations by keyword

### Request

`GET /locations/`

    curl -i -H 'Accept: application/json' -H "Content-Type: application/json" -H "apiKey: xxxxx" https://apps.outranking.io/api/locations?searchQuery=united

- searchQuery : search keyword for locaiton. this can be used for auto-suggestion input box.    

### Response

    HTTP/1.1 200 OK
    
```json
{
    "status": "OK",
    "code": 200,
    "message": "success",
    "data": [{
        "locationCode": "2581",
        "locationName": "United States Minor Outlying Islands",
        "locationCodeParent": null,
        "locationType": "Country"
    }, {
        "locationCode": "2784",
        "locationName": "United Arab Emirates",
        "locationCodeParent": null,
        "locationType": "Country"
    }, {
        "locationCode": "2826",
        "locationName": "United Kingdom",
        "locationCodeParent": null,
        "locationType": "Country"
    }, {
        "locationCode": "2840",
        "locationName": "United States",
        "locationCodeParent": null,
        "locationType": "Country"
    }]
}
```
