# REST API

### Get Places

```
GET /api/places
Accept: application/json
Authorization: Bearer {{token}}
```

**URL parameters**

| Name | Description |
| :--- | :--- |
| page | Page number, starts from 0. |
| size | Page size \(default: 20\). |
| sort | Order by property. e.g. "name,asc" or "name,desc". Multiple sort parameters are supported. |

Sample response:

```json
{
  "_embedded": {
    "places": [
      {
        "typeId": 1,
        "name": "Terazza",
        "description": null,
        "address": "",
        "longitude": 107.5811614,
        "latitude": -6.8869435,
        "createdBy": 0,
        "photo": null,
        "_links": {
          "self": {
            "href": "http://localhost:8080/api/places/1"
          },
          "place": {
            "href": "http://localhost:8080/api/places/1"
          },
          "type": {
            "href": "http://localhost:8080/api/places/1/type"
          }
        }
      },
      ...
    ]
  },
  "_links": {
    "first": {
      "href": "http://localhost:8080/api/places?page=0&size=20"
    },
    "self": {
      "href": "http://localhost:8080/api/places"
    },
    "next": {
      "href": "http://localhost:8080/api/places?page=1&size=20"
    },
    "last": {
      "href": "http://localhost:8080/api/places?page=20&size=20"
    },
    "profile": {
      "href": "http://localhost:8080/api/profile/places"
    },
    "search": {
      "href": "http://localhost:8080/api/places/search"
    }
  },
  "page": {
    "size": 20,
    "totalElements": 403,
    "totalPages": 21,
    "number": 0
  }
}
```

### Search Places by Category

```
GET /api/placeService/places            
Accept: application/json    
Authorization: Bearer {{token}}
```

**URL parameters**

| Name | Description |
| :--- | :--- |
| category | List of place categories, multiple parameters are supported. \(see below for recognized categories\) |
| page | Page number, starts from 0. |
| size | Page size \(default: 20\). |
| sort | Order by property. e.g. "name,asc" or "name,desc". Multiple sort parameters are supported. |

Place categories use OpenStreetMap tags, separated by "\_". Used keys are: [**amenity**](https://wiki.openstreetmap.org/wiki/Key:amenity), [**shop**](https://wiki.openstreetmap.org/wiki/Key:shop), [**tourism**](https://wiki.openstreetmap.org/wiki/Key:tourism). Most used categories include:

| Category | Description |
| :--- | :--- |
| amenity\_cafe, amenity\_fast\_food, amenity\_food\_court, amenity\_restaurant | Food & Drink |
| tourism\_hotel | Hotel |
| amenity\_hospital | Hospital |
| amenity\_fuel | Gas Station |
| shop\_fashion | Fashion |
| amenity\_college, amenity\_university | University |

Sample request:

```
GET /api/placeService/places?category=amenity_hospital
```

Sample response:

```json
{
  "_embedded": {
    "places": [
      {
        "id": 153,
        "typeId": 7,
        "name": "Puskesmas Karang Setra",
        "description": null,
        "address": "",
        "longitude": 107.5911377,
        "latitude": -6.8773969,
        "createdBy": 0,
        "photo": null
      },
      {
        "id": 154,
        "typeId": 7,
        "name": "Puskesmas Sukajadi",
        "description": null,
        "address": "",
        "longitude": 107.5944038,
        "latitude": -6.8922013,
        "createdBy": 0,
        "photo": null
      },
      ...
    ]
  },
  "page": {
    "size": 10,
    "totalElements": 41,
    "totalPages": 5,
    "number": 0
  }
}
```





