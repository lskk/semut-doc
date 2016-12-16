## 

## tb\_parking

Status lot terakhir, diupdate tiap 5 menit sekali.

| Name | Type | Description | Note for next version |
| :--- | :--- | :--- | :--- |
| lot\_id | varchar\(255\) | ID |  |
| lot\_stat | int\(11\) | 0 = tidak ada mobil saat ini; 1 = ada mobil saat ini |  |
| start\_time | timestamp | mobil terakhir masuk lot |  |
| end\_time | timestamp | mobil terakhir keluar lot |  |
| duration | int\(11\) | durasi mobil \(detik\) |  |
| lot\_pay | varchar\(20\) | Pembayaran parkir terakhir |  |
| book | int\(11\) | 0 = belum ada yang book. 1 = sudah ada yang book, meski kelihatan kosong |  |
| user\_id | varchar\(50\) | Foreign key ke tabel **tb\_user** |  |

## tb\_parking\_cctv

Lokasi CCTV untuk ditampilkan di peta.

| Name | Type | Description | Note for next version |
| :--- | :--- | :--- | :--- |
| ID | int\(11\) |  |  |
| ItemID | int\(11\) | Foreign key ke** tabel tb\_place\_type** |  |
| Name |  | Nama |  |
| Latitude |  |  |  |
| Longitude |  |  |  |
| CodeName |  | Nama unik |  |

## tb\_parking\_history

Histori tiap lot. Misalnya lot1 diisi oleh user tertentu dalam rentang waktu tertentu dan bayar berapa.

| Name | Type | Description | Note for next version |
| :--- | :--- | :--- | :--- |
|  |  | ID |  |

## Notes

tb\_lskk\_parking & tb\_lskk\_parking\_history are same as tb\_parking and tb\_parking\_history.

