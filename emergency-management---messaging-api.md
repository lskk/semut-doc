# Messaging API

Exchange: `amq.topic`

Routing Key: `emergency`

1. `pointTime`: Timestamp dalam [format ISO 8601](https://en.wikipedia.org/wiki/ISO_8601), dalam timezone UTC, contoh `2016-12-15T10:04:41Z`
2. `timeZone`: Time zone, contoh `Asia/Jakarta`
3. `interval`: Dalam milliseconds, contoh: 25 milliseconds artinya buffering input data 40 sample/detik. Dapat digunakan untuk mengirim 1 message berisi 40 sample 1 detik, atau berisi 200 sampel dalam 5 detik, dst.
4. Durasi data capture idealnya configurable di sensor, misal per durasi 1 detik, 2 detik, 10 detik, dsb.

Contoh message:

```json
{
    "pointTime": "2016-12-15T10:04:41Z",
    "timeZone": "Asia/Jakarta",
    "interval": 25,
    "geometry": {
    "type": "Point",
    "coordinates": [107.6102443, -6.8918592]
    },
    "accelerations": [
        {
            "x": -0.1243,
            "y": 14.6464725,
            "z": -12.5433
        }
    ]
}
```



