# Database Schema for Semut

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

## tb\_node

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
| ID | int\(11\) |  |  |
| Name | varchar\(100\) |  |  |
| Email | varchar\(100\) |  |  |
| CountryCode | int\(11\) |  | change type to varchar\(255\) |
| PhoneNumber | varchar\(20\) |  |  |
| Gender | int\(11\) |  | change type to varchar\(255\) |
| Birthday | date |  |  |
| Password | text | MD5 unsalted hash | Use bcrypt |
| Joindate | datetime |  |  |
| Poin | int\(11\) |  |  |
| PoinLevel | int\(11\) |  |  |
| AvatarID | int\(11\) |  |  |
| facebookID | varchar\(64\) |  |  |
| Verified | int\(11\) |  | change type to varchar\(255\) |
| VerifiedNumber | varchar\(50\) |  |  |
| Visibility | int\(11\) |  | change type to varchar\(255\) |
| Reputation | int\(11\) |  | change type to varchar\(255\) |
| flag | int\(11\) |  | change type to varchar\(255\) |
| Barcode | varchar\(25\) |  |  |
| deposit | float\(255,0\) |  | Type: numeric\(32,8\) |
| ID\_role | int\(255\) |  |  |
| Plat\_motor | varchar\(255\) |  |  |
| ID\_ktp | int\(255\) |  |  |
| foto | text |  |  |
| PushID | varchar\(255\) |  |  |
| Status\_online | int\(255\) |  | change type to varchar\(255\) |
| Path\_foto | varchar\(255\) |  |  |
| Nama\_foto | varchar\(50\) |  |  |
| Path\_ktp | varchar\(255\) |  |  |
| Nama\_ktp | varchar\(50\) |  |  |

## tb\_user\_admin

| Name | Type | Description | Note for next version |
| :--- | :--- | :--- | :--- |
| ID | int\(11\) |  |  |
| Username | varchar\(255\) |  |  |
| Password | text | Unsalted MD5 hash | Use bcrypt; change type to varchar\(255\) |
| Email | varchar\(255\) |  |  |
| Realname | varchar\(255\) |  |  |
| Type | int\(11\) |  | change type to varchar\(255\) |
| Status | int\(11\) |  | change type to varchar\(255\) |

## tb\_vehicle\_type

## tb\_way

## tb\_way\_node

## tb\_way\_type



