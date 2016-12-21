# Emergency Management API

API untuk Emergency Management terdiri dari 2 jenis:

1. **REST API: **dikembangkan sendiri menggunakan Spring Boot.
2. [**Messaging API**](/emergency-management---messaging-api.md): server yang digunakan adalah RabbitMQ. Protocol yang digunakan bisa AMQP, HTTP, maupun MQTT.

**API Tambahan - Geospatial API?**

Sedang dipertimbangkan untuk menggunakan GeoServer, namun sepertinya belum perlu. GeoServer sepertinya bagus karena menjadi [reference implementation](https://en.wikipedia.org/wiki/Reference_implementation) of the [Open Geospatial Consortium](https://en.wikipedia.org/wiki/Open_Geospatial_Consortium) [Web Feature Service](https://en.wikipedia.org/wiki/Web_Feature_Service) standard, and also implements the [Web Map Service](https://en.wikipedia.org/wiki/Web_Map_Service), [Web Coverage Service](https://en.wikipedia.org/wiki/Web_Coverage_Service) and [Web Processing Service](https://en.wikipedia.org/wiki/Web_Processing_Service) specifications. Pertimbangan lainnya, lihat [http://gis.stackexchange.com/a/6614/20611](http://gis.stackexchange.com/a/6614/20611).



