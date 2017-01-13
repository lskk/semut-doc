# Messaging API

Server Source Code : [https://github.com/pptik/semut-mq-service](https://github.com/pptik/semut-mq-service)

Virtual Host : `/semut`

Exchange Name : `semut.service`

Type : `topic`

Menggunakan protokol `RPC` , Setiap request mengembalikan callback berupa JSON yang sesuai dengan kebutuhan permintaan, karenanya tiap consumer/pengguna wajib membuat antrian dengan format berikut :

`semut.user.<id user>` sehingga mendapatkan callback yang berbeda untuk tiap pengguna \(kecuali pada saat proses login dan register\).

* ### Login

Routing Key : `semut.service.app.login`

Queue : `<generated>`

Reply To :  `<generated>`

**Request** : `{email: "<email pengguna>", password: "<sandi pengguna>"}`

**Response** :

```json
{

    "response": {

        "success": true,

        "message": "Berhasil Login!",

        "Profile": {

            "Name": "hafiyyan",

            "Email": "hafiyyan.jtk10@gmail.com",

            "CountryCode": 62,

            "PhoneNumber": null,

            "Gender": 1,

            "Birthday": null,

            "Joindate": "2015-09-02T05:27:16.000Z",

            "Poin": 1100,

            "Poinlevel": 100,

            "Visibility": 0,

            "Verified": 0,

            "AvatarID": 1

        },

        "sessionID": 2193

    }

}
```

Contoh Client Request \(Menggunakan node js\) : [https://github.com/pptik/semut-mq-service/blob/master/amqp/tests/test\_login.js](https://github.com/pptik/semut-mq-service/blob/master/amqp/tests/test_login.js)

* ### Register {#register}

Routing Key : `semut.service.app.register`

Queue : `<generated>`

Reply To :  `<generated>`

**Request** :

```json
{
    "email": "5@test.com",
    "phonenumber": "081311415274",
    "gender": 1,
    "birthday": "1991-09-20",
    "password": "qwerty",
    "name": "test"
}
```

`email` : Email pengguna

`phonenumber` : Nomor Pengguna

`gender` : 1 = Pria, 2 = Wanita

`birthday` : Tanggal lahir pengguna, format : `YYYY-MM-DD`

`password` : Kata sandi pengguna.

`name` : Nama Pengguna.

**Response** :

```json
{

    "response": {

        "success": true,

        "message": "Sukses Membuat Akun, silahkan login!"

    }

}
```

Contoh Client Request \(Menggunakan node js\) : [https://github.com/pptik/semut-mq-service/blob/master/amqp/tests/test\_register.js](https://github.com/pptik/semut-mq-service/blob/master/amqp/tests/test_register.js)

* ### Get Profile {#register}

Routing Key : `semut.service.app.getprofile`

Queue : `semut.user.<id pengguna>`

Reply To :  `semut.user.<id pengguna>`

`<id pengguna>`  bisa didapat setelah berhasil melakukan proses login.

**Request** : `{sessionID: <session id pengguna>}`

`sessionID` : adalah kode session yang didapat dari proses login.

**Response** :

```json
{
    "response": {
        "success": true,
        "message": "Sukses memuat permintaan",
        "Profile": {
            "ID": 418,
            "Name": "hafiyyan",
            "Email": "hafiyyan.jtk10@gmail.com",
            "CountryCode": 62,
            "PhoneNumber": null,
            "Gender": 1,
            "Birthday": null,
            "Joindate": "2015-09-02T05:27:16.000Z",
            "Poin": 1100,
            "PoinLevel": 100,
            "AvatarID": 1,
            "Verified": 0,
            "Visibility": 0,
            "Reputation": 2,
            "deposit": 1000000
        }
    }
}
```

Contoh Client Request \(Menggunakan node js\) : [https://github.com/pptik/semut-mq-service/blob/master/amqp/tests/test\_getprofile.js](https://github.com/pptik/semut-mq-service/blob/master/amqp/tests/test_getprofile.js)

