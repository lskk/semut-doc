# Emergency Management API

API untuk Emergency Management terdiri dari 3 jenis:

1. **Geospatial API: **menggunakan GeoServer. GeoServer dipilih karena menjadi [reference implementation](https://en.wikipedia.org/wiki/Reference_implementation) of the [Open Geospatial Consortium](https://en.wikipedia.org/wiki/Open_Geospatial_Consortium) [Web Feature Service](https://en.wikipedia.org/wiki/Web_Feature_Service) standard, and also implements the [Web Map Service](https://en.wikipedia.org/wiki/Web_Map_Service), [Web Coverage Service](https://en.wikipedia.org/wiki/Web_Coverage_Service) and [Web Processing Service](https://en.wikipedia.org/wiki/Web_Processing_Service) specifications. Pertimbangan lainnya, lihat [http://gis.stackexchange.com/a/6614/20611](http://gis.stackexchange.com/a/6614/20611).
2. **REST API: **dikembangkan sendiri menggunakan Spring Boot.
3. **Messaging API**: server yang digunakan adalah RabbitMQ. Protocol yang digunakan bisa AMQP, HTTP, maupun MQTT.

## Geospatial API

...

## REST API

### Get Places

`GET /places    
Authorization: Bearer {{token}}`

**URL parameters**

| Name | Description |
| :--- | :--- |
| categories | comma-separated list of place categories. \(see below for recognized categories\) |
| page | Page number, starts from 0. |
| size | Page size. |
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

Response:

`{  
    "_embedded": {  
        "places": [  
            {  
            }  
        ]  
    }  
}`

## Messaging API

...

