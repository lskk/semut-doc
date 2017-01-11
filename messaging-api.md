# Messaging API

Server Source Code : [https://github.com/pptik/semut-mq-service](https://github.com/pptik/semut-mq-service)

Virtual Host : `/semut`

Exchange Name : `semut.service`

Type : `topic`

Menggunakan protokol `RPC` , Setiap request mengembalikan callback berupa JSON yang sesuai dengan kebutuhan permintaan, karenanya tiap consumer/pengguna wajib membuat antrian dengan format berikut :

`semut.user.<id user>` sehingga mendapatkan callback yang berbeda untuk tiap pengguna \(kecuali pada saat proses login\).

* ### Login

Routing Key : `semut.service.app.login`

Queue : `<generated>`

Reply To :  `<generated>`

Request : `{email: "<email pengguna>", password: "<sandi pengguna>"}`

Response :

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

Contoh Client Request \(Menggunakan node js\) : [https://github.com/pptik/semut-mq-service/blob/master/amqp/tests/test_login.js](https://github.com/pptik/semut-mq-service/blob/master/amqp/tests/test_login.js)

