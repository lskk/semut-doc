# Emergency Management API

API untuk Emergency Management terdiri dari 3 jenis:

1. **Geospatial API: **menggunakan GeoServer. GeoServer dipilih karena menjadi [reference implementation](https://en.wikipedia.org/wiki/Reference_implementation) of the [Open Geospatial Consortium](https://en.wikipedia.org/wiki/Open_Geospatial_Consortium) [Web Feature Service](https://en.wikipedia.org/wiki/Web_Feature_Service) standard, and also implements the [Web Map Service](https://en.wikipedia.org/wiki/Web_Map_Service), [Web Coverage Service](https://en.wikipedia.org/wiki/Web_Coverage_Service) and [Web Processing Service](https://en.wikipedia.org/wiki/Web_Processing_Service) specifications. Pertimbangan lainnya, lihat [http://gis.stackexchange.com/a/6614/20611](http://gis.stackexchange.com/a/6614/20611).
2. **REST API: **dikembangkan sendiri menggunakan Spring Boot.
3. [**Messaging API**](/emergency-management---messaging-api.md): server yang digunakan adalah RabbitMQ. Protocol yang digunakan bisa AMQP, HTTP, maupun MQTT.

## Geospatial API

...

## REST API

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

```
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

```
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

## 



