Database yang digunakan adalah MySQL.

Untuk memudahkan integrasi saat deployment, database Semut juga digunakan oleh ACT, Semut Parking, Opang, dan Emergency Management.

Struktur database ACT, Semut Parking, Opang, dan Emergency Management, dideskripsikan di bagian masing-masing.

## tb\_ads

## tb\_ads\_category

## tb\_ads\_company

## tb\_ads\_subscription

## tb\_ads\_type

## tb\_ambulance

## tb\_angkot

## tb\_angkot\_type

## tb\_api\_log

## tb\_avatar

## tb\_cctv

## tb\_checkin

## tb\_city

## tb\_country

## tb\_emergency

## tb\_emergency\_type

## tb\_keys

## tb\_location

## tb\_lskk\_parking

## tb\_lskk\_parking\_history

## tb\_node

## tb\_parking

## tb\_parking\_cctv

## tb\_parking\_history

## tb\_place

## tb\_place\_type

## tb\_police

## tb\_post

## tb\_post\_subtype

## tb\_post\_type

## tb\_province

## tb\_pushnotif

## tb\_relation

## tb\_request\_taxi

## tb\_session

## tb\_taxi

## tb\_taxi\_company

## tb\_taxi\_location

## tb\_taxi\_order

## tb\_taxi\_reservation

## tb\_taxi\_session

## tb\_tracker

## tb\_user

| Name | Type | Description | Note for next version |
| :--- | :--- | :--- | :--- |
| ID |  |  |  |
| Name |  |  |  |
| Email |  |  |  |
| CountryCode |  |  |  |
| PhoneNumber |  |  |  |
| Gender |  |  |  |
| Birthday |  |  |  |
| Password |  |  |  |
| Joindate |  |  |  |
| Poin |  |  |  |
| PoinLevel |  |  |  |
| AvatarID |  |  |  |
| facebookID |  |  |  |
| Verified | int\(11\) |  |  |
| VerifiedNumber | varchar\(50\) |  |  |
| Visibility | int\(11\) |  |  |
| Reputation | int\(11\) |  |  |
| flag | int\(11\) |  |  |
| Barcode | varchar\(25\) |  |  |
| deposit | float\(255,0\) |  | Type: numeric\(32,8\) |
| ID\_role | int\(255\) |  |  |
| Plat\_motor | varchar\(255\) |  |  |
| ID\_ktp | int\(255\) |  |  |
| foto | text |  |  |
| PushID | varchar\(255\) |  |  |
| Status\_online | int\(255\) |  |  |
| Path\_foto | varchar\(255\) |  |  |
| Nama\_foto | varchar\(50\) |  |  |
| Path\_ktp | varchar\(255\) |  |  |
| Nama\_ktp | varchar\(50\) |  |  |

## tb\_user\_admin

## tb\_vehicle\_type

## tb\_way

## tb\_way\_node

## tb\_way\_type



