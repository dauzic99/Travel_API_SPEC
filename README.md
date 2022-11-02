<!-- # Travel API Spec -->

# Authentication

All API must use this authentication

Request :

- Header :
  - Authorization : Bearer {$token}

# Travel Posting Customer

API untuk Travel Posting yang dilakukan oleh Customer

## Create

Request :

- Method : POST
- Endpoint : `/travelpostingcustomer/create`
- Header :
  - Content-Type: application/json
  - Accept: application/json
- Body :

```json
{
  "user_id": "integer", //diambil dari id customer
  "city_origin": "string", //eg : Kota Samarinda
  "city_destination": "string", //eg : Kota Balikpapan
  "address_origin": "text", //eg : Jalan Mawar no 15
  "address_destination": "text", //eg : Jalan Melati no 17
  "date_dep": "date", //eg : 2022-08-15. Tanggal Keberangkatan
  "passenger_count": "integer", //eg : 2. Jumlah Penumpang
  "status": "integer", //eg : 1. status disamakan dengan nebeng nitip [1,2,3,4]
  "description": "text" //deskripsi perjalanan
}
```

Response :

```json
{
  "success": "boolean",
  "data": {
    "id": "integer",
    "user_id": "integer",
    "city_origin": "string",
    "city_destination": "string",
    "address_origin": "text",
    "address_destination": "text",
    "date_dep": "date",
    "passenger_count": "integer",
    "status": "integer",
    "description": "text",
    "createdAt": "date",
    "updatedAt": "date"
  }
}
```

## List

Request :

- Method : GET
- Endpoint : `/travelpostingcustomer/list`
- Header :
  - Content-Type: application/json
  - Accept: application/json

Response :

```json
{
  "success": "boolean",
  "data": [
    {
      "id": "integer",
      "user_id": "integer",
      "city_origin": "string",
      "city_destination": "string",
      "address_origin": "text",
      "address_destination": "text",
      "date_dep": "date",
      "passenger_count": "integer",
      "status": "integer",
      "description": "text",
      "createdAt": "date",
      "updatedAt": "date",
      "isDeleted": "integer",
      "passenger": [
        {
          "id": "integer",
          "name": "string",
          "relation": "string",
          "phone_number": "string",
          "address_origin": "text",
          "address_destination": "text"
        }
      ],
      "user": {
        "id": "integer",
        "username": "string",
        "email": "string",
        "password": "string",
        "nik": "string",
        "ktp_pict": "string",
        "image": "string",
        "gender": "string",
        "birth": "date",
        "address": "string",
        "phone": "string",
        "status": "integer",
        "lat": "string",
        "lang": "string",
        "city": "string",
        "role": "string",
        "fcm": "string",
        "otp": "string",
        "blockedAt": "date",
        "createdAt": "date",
        "updatedAt": "date",
        "isDeleted": "integer"
      }
    }
  ]
}
```

## List Status Open By Region

AP Digunakan pada aplikasi driver untuk menampilkan list posting travel dari customer sesuai dengan region driver.

Request :

- Method : POST
- Endpoint : `/travelpostingcustomer/liststatusopenbyregion`
- Header :

  - Content-Type: application/json
  - Accept: application/json

- Body :

```json
{
  "city": "string" //Kota Samarinda
}
```

Response :

```json
{
  "success": "boolean",
  "data": [
    {
      "id": "integer",
      "user_id": "integer",
      "city_origin": "string",
      "city_destination": "string",
      "address_origin": "text",
      "address_destination": "text",
      "date_dep": "date",
      "passenger_count": "integer",
      "status": "integer",
      "description": "text",
      "createdAt": "date",
      "updatedAt": "date",
      "isDeleted": "integer",
      "passenger": [
        {
          "id": "integer",
          "travel_posting_customer_id": "integer",
          "name": "string",
          "relation": "string",
          "phone_number": "string",
          "address_origin": "text",
          "address_destination": "text",
          "createdAt": "date",
          "updatedAt": "date",
          "isDeleted": "integer"
        }
      ],
      "user": {
        "id": "integer",
        "username": "string",
        "email": "string",
        "password": "string",
        "nik": "string",
        "ktp_pict": "string",
        "image": "string",
        "gender": "string",
        "birth": "date",
        "address": "string",
        "phone": "string",
        "status": "integer",
        "lat": "string",
        "lang": "string",
        "city": "string",
        "role": "string",
        "fcm": "string",
        "otp": "string",
        "blockedAt": "date",
        "createdAt": "date",
        "updatedAt": "date",
        "isDeleted": "integer"
      }
    }
  ]
}
```

## Find By ID

Request :

- Method : GET
- Endpoint : `/travelpostingcustomer/{id}`
- Header :
  - Content-Type: application/json
  - Accept: application/json

Response :

```json
{
  "success": "boolean",
  "data": {
    "travelPostingCustomer": {
      "id": "integer",
      "user_id": "integer",
      "city_origin": "string",
      "city_destination": "string",
      "address_origin": "text",
      "address_destination": "text",
      "date_dep": "date",
      "passenger_count": "integer",
      "status": "integer",
      "description": "text",
      "createdAt": "date",
      "updatedAt": "date",
      "isDeleted": "integer"
    },
    "passenger": [
      {
        "id": "integer",
        "name": "string",
        "relation": "string",
        "phone_number": "string",
        "address_origin": "text",
        "address_destination": "text"
      }
    ],
    "user": {
      "id": "integer",
      "username": "string",
      "email": "string",
      "password": "string",
      "nik": "string",
      "ktp_pict": "string",
      "image": "string",
      "gender": "string",
      "birth": "date",
      "address": "string",
      "phone": "string",
      "status": "integer",
      "lat": "string",
      "lang": "string",
      "city": "string",
      "role": "string",
      "fcm": "string",
      "otp": "string",
      "blockedAt": "date",
      "createdAt": "date",
      "updatedAt": "date",
      "isDeleted": "integer"
    }
  }
}
```

## Update

Request :

- Method : POST
- Endpoint : `/travelpostingcustomer/update/{id}`
- Header :
  - Content-Type: application/json
  - Accept: application/json
- Body :

```json
{
  "city_origin": "string", //optional
  "city_destination": "string", //optional
  "address_origin": "text", //optional
  "address_destination": "text", //optional
  "date_dep": "date", //optional
  "passenger_count": "integer", //optional
  "status": "integer", //optional
  "description": "text" //optional
}
```

Response :

```json
{
  "success": "boolean",
  "data": {
    "travelPostingCustomer": {
      "id": "integer",
      "user_id": "integer",
      "city_origin": "string",
      "city_destination": "string",
      "address_origin": "text",
      "address_destination": "text",
      "date_dep": "date",
      "passenger_count": "integer",
      "status": "integer",
      "description": "text",
      "createdAt": "date",
      "updatedAt": "date",
      "isDeleted": "integer"
    },
    "passenger": [
      {
        "id": "integer",
        "name": "string",
        "relation": "string",
        "phone_number": "string",
        "address_origin": "text",
        "address_destination": "text",
        "createdAt": "date",
        "updatedAt": "date",
        "isDeleted": "integer"
      }
    ],
    "user": {
      "id": "integer",
      "username": "string",
      "email": "string",
      "password": "string",
      "nik": "string",
      "ktp_pict": "string",
      "image": "string",
      "gender": "string",
      "birth": "date",
      "address": "string",
      "phone": "string",
      "status": "integer",
      "lat": "string",
      "lang": "string",
      "city": "string",
      "role": "string",
      "fcm": "string",
      "otp": "string",
      "blockedAt": "date",
      "createdAt": "date",
      "updatedAt": "date",
      "isDeleted": "integer"
    }
  }
}
```

## Delete

Request :

- Method : GET
- Endpoint : `/travelpostingcustomer/delete/{id}`
- Header :
  - Content-Type: application/json
  - Accept: application/json

Response :

```json
{
  "success": "boolean",
  "data": "Travel Post Customer has been deleted successfully"
}
```

# Travel Additional Passenger

API untuk data penumpang tambahan pada Travel Posting Customer

Digunakan untuk penumpang kedua dan selebihnya

## Create

Request :

- Method : POST
- Endpoint : `/traveladdscustomer/create`
- Header :
  - Content-Type: application/json
  - Accept: application/json
- Body :

```json
{
  "travel_posting_customer_id": "integer", //diambil dari id travel posting customer
  "name": "string", //eg : Bunga
  "relation": "string", //eg : Step Sister
  "phone_number": "string", //eg : 08778868543
  "address_origin": "text", //eg : Jalan Mawar no 15
  "address_destination": "text" //eg : Jalan Melati no 17
}
```

Response :

```json
{
  "success": "boolean",
  "data": {
    "id": "integer",
    "travel_posting_customer_id": "integer",
    "name": "string",
    "relation": "string",
    "phone_number": "string",
    "address_origin": "text",
    "address_destination": "text",
    "createdAt": "date",
    "updatedAt": "date"
  }
}
```

## List

Request :

- Method : GET
- Endpoint : `/traveladdscustomer/list`
- Header :
  - Content-Type: application/json
  - Accept: application/json

Response :

```json
{
  "success": "boolean",
  "data": [
    {
      "id": "integer",
      "travel_posting_customer_id": "integer",
      "name": "string",
      "relation": "string",
      "phone_number": "string",
      "address_origin": "text",
      "address_destination": "text",
      "createdAt": "date",
      "updatedAt": "date",
      "isDeleted": "integer"
    }
  ]
}
```

## Find By ID

Request :

- Method : GET
- Endpoint : `/traveladdscustomer/{id}`
- Header :
  - Content-Type: application/json
  - Accept: application/json

Response :

```json
{
  "success": "boolean",
  "data": {
    "id": "integer",
    "travel_posting_customer_id": "integer",
    "name": "string",
    "relation": "string",
    "phone_number": "string",
    "address_origin": "text",
    "address_destination": "text",
    "createdAt": "date",
    "updatedAt": "date",
    "isDeleted": "integer"
  }
}
```

## Update

Request :

- Method : POST
- Endpoint : `/traveladdscustomer/update/{id}`
- Header :
  - Content-Type: application/json
  - Accept: application/json
- Body :

```json
{
  "name": "string", //optional
  "relation": "string", //optional
  "phone_number": "string", //optional
  "address_origin": "text", //optional
  "address_destination": "text" //optional
}
```

Response :

```json
{
  "success": "boolean",
  "data": {
    "id": "integer",
    "travel_posting_customer_id": "integer",
    "name": "string",
    "relation": "string",
    "phone_number": "string",
    "address_origin": "text",
    "address_destination": "text",
    "createdAt": "date",
    "updatedAt": "date",
    "isDeleted": "integer"
  }
}
```

## Delete

Request :

- Method : GET
- Endpoint : `/traveladdscustomer/delete/{id}`
- Header :
  - Content-Type: application/json
  - Accept: application/json

Response :

```json
{
  "success": "boolean",
  "data": "Travel Additional Passenger has been deleted successfully"
}
```

# Travel Transactions

Digunakan untuk "parent" yang menampung order customer pada driver

## Create

API digunakan pada saat driver ingin membuat penawaran. di backend cek apakah sudah ada data di table travel transaction dengan date_dep yang sama. jika belum ada maka create. jika sudah ada maka kembalikan data tersebut. available seat adalah seat yg is_takennya 0.
Lalu untuk create travel transactions di backend, sekaligus create travel seat, dengan 5 row data. nama seat nya sebagai berikut : "Kursi depan","Kursi Tengah Kiri", "Kursi Tengah Kanan","Kursi Belakang Kiri","Kursi Belakang Kanan".
Saat pertama kali dibuat, status = 1

Request :

- Method : POST
- Endpoint : `/traveltrx/create`
- Header :
  - Content-Type: application/json
  - Accept: application/json
- Body :

```json
{
  "rider_id": "integer",
  "date_dep": "date", //diambil dari posting customer pertama yang mau diambil
  "is_urgent": "integer" //eg : 0
}
```

Response :

```json
{
  "success": "boolean",
  "data": {
    "travelTransaction": {
      "id": "integer",
      "rider_id": "integer",
      "dateTimeStart": "date",
      "dateTimeFinish": "date",
      "status": "integer",
      "date_dep": "date",
      "is_urgent": "integer",
      "createdAt": "date",
      "updatedAt": "date"
    },
    "available_seat": [
      {
        "id": "integer",
        "seat_name": "string",
        "is_taken": "integer",
        "createdAt": "date",
        "updatedAt": "date"
      }
    ]
  }
}
```

## List

Request :

- Method : GET
- Endpoint : `/traveltrx/list`
- Header :
  - Content-Type: application/json
  - Accept: application/json

Response :

```json
{
  "success": "boolean",
  "data": [
    {
      "id": "integer",
      "rider_id": "integer",
      "dateTimeStart": "date",
      "dateTimeFinish": "date",
      "status": "integer",
      "date_dep": "date",
      "is_urgent": "integer",
      "createdAt": "date",
      "updatedAt": "date",
      "isDeleted": "integer",
      "seat": [
        {
          "id": "integer",
          "seat_name": "string",
          "is_taken": "integer",
          "createdAt": "date",
          "updatedAt": "date",
          "isDeleted": "integer"
        }
      ],
      "main_rider": {
        "id": "integer",
        "name": "string",
        "email": "string",
        "nik": "string",
        "ktp_pict": "string",
        "image": "string",
        "gender": "female",
        "birth": "date",
        "address": "string",
        "phone": "string",
        "password": "string",
        "status": "integer",
        "account_approve": "date",
        "cityLocation": "string",
        "role": "string",
        "fcm": "string",
        "otp": "string",
        "account_regis": "date",
        "createdAt": "date",
        "updatedAt": "date",
        "isDeleted": "integer"
      },
      "nebeng_rider": {
        "id": "integer",
        "rider_id": "integer",
        "statusNebeng": "integer",
        "sim": "string",
        "simPict": "string",
        "simExp": "date",
        "stnkPict": "string",
        "account_approved": "string",
        "lat": "string",
        "lang": "string",
        "rating": "integer",
        "approvedBy": "integer",
        "vehicle_variant": "string",
        "plat_number": "string",
        "vehicle_color": "string",
        "account_regis": "date",
        "createdAt": "date",
        "updatedAt": "date",
        "isDeleted": "integer"
      }
    }
  ]
}
```

## List By Rider ID

Request :

- Method : POST
- Endpoint : `/traveltrx/listbyrider`
- Header :
  - Content-Type: application/json
  - Accept: application/json
- Body :

```json
{
  "rider_id": "integer"
}
```

Response :

```json
{
  "success": "boolean",
  "data": [
    {
      "id": "integer",
      "rider_id": "integer",
      "dateTimeStart": "date",
      "dateTimeFinish": "date",
      "status": "integer",
      "date_dep": "date",
      "is_urgent": "integer",
      "createdAt": "date",
      "updatedAt": "date",
      "isDeleted": "integer",
      "seat": [
        {
          "id": "integer",
          "seat_name": "string",
          "is_taken": "integer",
          "createdAt": "date",
          "updatedAt": "date",
          "isDeleted": "integer"
        }
      ],
      "travel_order": [
        {
          "id": "integer",
          "travel_transaction_id": "integer",
          "travel_posting_customer_id": "integer",
          "time_dep": "string",
          "description": "text",
          "status": "integer",
          "note": "text",
          "payment_type": "integer",
          "total_price": "integer",
          "createdAt": "date",
          "updatedAt": "date",
          "seat_offer": [
            {
              "id": "integer",
              "travel_order_id": "integer",
              "travel_seat_id": "integer",
              "price": "integer",
              "is_accepted": "integer",
              "createdAt": "date",
              "updatedAt": "date"
            }
          ]
        }
      ],
      "main_rider": {
        "id": "integer",
        "name": "string",
        "email": "string",
        "nik": "string",
        "ktp_pict": "string",
        "image": "string",
        "gender": "female",
        "birth": "date",
        "address": "string",
        "phone": "string",
        "password": "string",
        "status": "integer",
        "account_approve": "date",
        "cityLocation": "string",
        "role": "string",
        "fcm": "string",
        "otp": "string",
        "account_regis": "date",
        "createdAt": "date",
        "updatedAt": "date",
        "isDeleted": "integer"
      },
      "nebeng_rider": {
        "id": "integer",
        "rider_id": "integer",
        "statusNebeng": "integer",
        "sim": "string",
        "simPict": "string",
        "simExp": "date",
        "stnkPict": "string",
        "account_approved": "string",
        "lat": "string",
        "lang": "string",
        "rating": "integer",
        "approvedBy": "integer",
        "vehicle_variant": "string",
        "plat_number": "string",
        "vehicle_color": "string",
        "account_regis": "date",
        "createdAt": "date",
        "updatedAt": "date",
        "isDeleted": "integer"
      }
    }
  ]
}
```

## Find By ID

Request :

- Method : GET
- Endpoint : `/traveltrx/{id}`
- Header :
  - Content-Type: application/json
  - Accept: application/json

Response :

```json
{
  "success": "boolean",
  "data": {
    "travelTrx": {
      "id": "integer",
      "rider_id": "integer",
      "dateTimeStart": "date",
      "dateTimeFinish": "date",
      "status": "integer",
      "date_dep": "date",
      "is_urgent": "integer",
      "createdAt": "date",
      "updatedAt": "date",
      "isDeleted": "integer"
    },
    "seat": [
      {
        "id": "integer",
        "seat_name": "string",
        "is_taken": "integer",
        "createdAt": "date",
        "updatedAt": "date",
        "isDeleted": "integer"
      }
    ],
    "main_rider": {
      "id": "integer",
      "name": "string",
      "email": "string",
      "nik": "string",
      "ktp_pict": "string",
      "image": "string",
      "gender": "female",
      "birth": "date",
      "address": "string",
      "phone": "string",
      "password": "string",
      "status": "integer",
      "account_approve": "date",
      "cityLocation": "string",
      "role": "string",
      "fcm": "string",
      "otp": "string",
      "account_regis": "date",
      "createdAt": "date",
      "updatedAt": "date",
      "isDeleted": "integer"
    },
    "nebeng_rider": {
      "id": "integer",
      "rider_id": "integer",
      "statusNebeng": "integer",
      "sim": "string",
      "simPict": "string",
      "simExp": "date",
      "stnkPict": "string",
      "account_approved": "string",
      "lat": "string",
      "lang": "string",
      "rating": "integer",
      "approvedBy": "integer",
      "vehicle_variant": "string",
      "plat_number": "string",
      "vehicle_color": "string",
      "account_regis": "date",
      "createdAt": "date",
      "updatedAt": "date",
      "isDeleted": "integer"
    }
  }
}
```

## Update

Request :

- Method : POST
- Endpoint : `/traveltrx/update/{id}`
- Header :
  - Content-Type: application/json
  - Accept: application/json
- Body :

```json
{
  "rider_id": "integer", //optional
  "date_dep": "date", //optional
  "is_urgent": "integer", //optional
  "status": "integer", //optional
  "dateTimeStart": "string", //optional
  "dateTimeFinish": "string" //optional
}
```

Response :

```json
{
  "success": "boolean",
  "data": {
    "id": "integer",
    "rider_id": "integer",
    "dateTimeStart": "date",
    "dateTimeFinish": "date",
    "status": "integer",
    "date_dep": "date",
    "is_urgent": "integer",
    "createdAt": "date",
    "updatedAt": "date",
    "isDeleted": "integer",
    "seat": [
      {
        "id": "integer",
        "seat_name": "string",
        "is_taken": "integer",
        "createdAt": "date",
        "updatedAt": "date",
        "isDeleted": "integer"
      }
    ]
  }
}
```

## Delete

Request :

- Method : GET
- Endpoint : `/traveltrx/delete/{id}`
- Header :
  - Content-Type: application/json
  - Accept: application/json

Response :

```json
{
  "success": "boolean",
  "data": "Travel Transaction has been deleted successfully"
}
```

## Start Pick Up

Ubah Status Travel Transaction menjadi 2

Ubah status semua travel_order dari array travel_order_id menjadi 3

kasih notif ke penumpang berdasarkan order id tersebut. order->posting_customer->user.

title : Penjnemputan dimulai

Message : Driver sedang dalam perjalanan menjemput anda. Mohon ditunggu di alamat penjemputan

Request :

- Method : POST
- Endpoint : `/traveltrx/startPickUp`
- Header :
  - Content-Type: application/json
  - Accept: application/json
- Body :

```json
{
  "travel_transaction_id": "integer", //optional
  "travel_order_id": ["integer"] //optional
}
```

Response :

```json
{
  "success": "boolean",
  "data": {
    "travel_transaction": {
      "id": "integer",
      "rider_id": "integer",
      "dateTimeStart": "date",
      "dateTimeFinish": "date",
      "status": "integer",
      "date_dep": "date",
      "is_urgent": "integer",
      "createdAt": "date",
      "updatedAt": "date",
      "isDeleted": "integer",
      "seat": [
        {
          "id": "integer",
          "seat_name": "string",
          "is_taken": "integer",
          "createdAt": "date",
          "updatedAt": "date",
          "isDeleted": "integer"
        }
      ]
    },
    "travel_order":[
      {
        "id": "integer",
        "travel_transaction_id": "integer",
        "travel_posting_customer_id": "integer",
        "time_dep": "string",
        "description": "text",
        "status": "integer",
        "note": "text",
        "payment_type": "integer",
        "total_price": "integer",
        "createdAt": "date",
        "updatedAt": "date",
        "seat_offer": [
          {
            "id": "integer",
            "travel_order_id": "integer",
            "travel_seat_id": "integer",
            "price": "integer",
            "is_accepted": "integer",
            "createdAt": "date",
            "updatedAt": "date"
          }
        ]
      }
    ]
  }
```

## Start Travel

Ubah Status Travel Transaction menjadi 3

Ubah status semua travel_order dari array travel_order_id menjadi 4

kasih notif ke penumpang berdasarkan order id tersebut. order->posting_customer->user.

title : Perjalanan Travel Dimulai

Message : Anda sedang dalam perjalanan menuju kota tujuan

Request :

- Method : POST
- Endpoint : `/traveltrx/startTravelTrx`
- Header :
  - Content-Type: application/json
  - Accept: application/json
- Body :

```json
{
  "travel_transaction_id": "integer", //optional
  "travel_order_id": ["integer"] //optional
}
```

Response :

```json
{
  "success": "boolean",
  "data": {
    "travel_transaction": {
      "id": "integer",
      "rider_id": "integer",
      "dateTimeStart": "date",
      "dateTimeFinish": "date",
      "status": "integer",
      "date_dep": "date",
      "is_urgent": "integer",
      "createdAt": "date",
      "updatedAt": "date",
      "isDeleted": "integer",
      "seat": [
        {
          "id": "integer",
          "seat_name": "string",
          "is_taken": "integer",
          "createdAt": "date",
          "updatedAt": "date",
          "isDeleted": "integer"
        }
      ]
    },
    "travel_order":[
      {
        "id": "integer",
        "travel_transaction_id": "integer",
        "travel_posting_customer_id": "integer",
        "time_dep": "string",
        "description": "text",
        "status": "integer",
        "note": "text",
        "payment_type": "integer",
        "total_price": "integer",
        "createdAt": "date",
        "updatedAt": "date",
        "seat_offer": [
          {
            "id": "integer",
            "travel_order_id": "integer",
            "travel_seat_id": "integer",
            "price": "integer",
            "is_accepted": "integer",
            "createdAt": "date",
            "updatedAt": "date"
          }
        ]
      }
    ]
  }
```

## Finish Travel

Ubah Status Travel Transaction menjadi 4

Ubah status semua travel_order dari array travel_order_id menjadi 5

kasih notif ke penumpang berdasarkan order id tersebut. order->posting_customer->user.

title : Perjalanan Travel Selesai

Message : Anda sudah sampai di kota tujuan.

Request :

- Method : POST
- Endpoint : `/traveltrx/finishTravelTrx`
- Header :
  - Content-Type: application/json
  - Accept: application/json
- Body :

```json
{
  "travel_transaction_id": "integer", //optional
  "travel_order_id": ["integer"] //optional
}
```

Response :

```json
{
  "success": "boolean",
  "data": {
    "travel_transaction": {
      "id": "integer",
      "rider_id": "integer",
      "dateTimeStart": "date",
      "dateTimeFinish": "date",
      "status": "integer",
      "date_dep": "date",
      "is_urgent": "integer",
      "createdAt": "date",
      "updatedAt": "date",
      "isDeleted": "integer",
      "seat": [
        {
          "id": "integer",
          "seat_name": "string",
          "is_taken": "integer",
          "createdAt": "date",
          "updatedAt": "date",
          "isDeleted": "integer"
        }
      ]
    },
    "travel_order":[
      {
        "id": "integer",
        "travel_transaction_id": "integer",
        "travel_posting_customer_id": "integer",
        "time_dep": "string",
        "description": "text",
        "status": "integer",
        "note": "text",
        "payment_type": "integer",
        "total_price": "integer",
        "createdAt": "date",
        "updatedAt": "date",
        "seat_offer": [
          {
            "id": "integer",
            "travel_order_id": "integer",
            "travel_seat_id": "integer",
            "price": "integer",
            "is_accepted": "integer",
            "createdAt": "date",
            "updatedAt": "date"
          }
        ]
      }
    ]
  }
```

# Travel Order

Digunakan untuk order dan request driver pada customer

## Create

Request :

- Method : POST
- Endpoint : `/travelorder/create`
- Header :
  - Content-Type: application/json
  - Accept: application/json
- Body :

```json
{
  "travel_transaction_id": "integer",
  "travel_posting_customer_id": "integer",
  "time_dep": "string", //waktu keberangkatan driver
  "description": "text", //eg : Lorem Ipsum //optional
  "seat_offer": [
    {
      "travel_seat_id": "integer",
      "price": "integer"
    }
  ]
}
```

Response :

```json
{
  "success": "boolean",
  "data": {
    "id": "integer",
    "travel_transaction_id": "integer",
    "travel_posting_customer_id": "integer",
    "time_dep": "string",
    "description": "text",
    "status": "integer",
    "note": "text",
    "payment_type": "integer",
    "total_price": "integer",
    "createdAt": "date",
    "updatedAt": "date",
    "seat_offer": [
      {
        "id": "integer",
        "travel_order_id": "integer",
        "travel_seat_id": "integer",
        "price": "integer",
        "is_accepted": "integer",
        "createdAt": "date",
        "updatedAt": "date"
      }
    ]
  }
}
```

## List

Request :

- Method : GET
- Endpoint : `/travelorder/list`
- Header :
  - Content-Type: application/json
  - Accept: application/json

Response :

```json
{
  "success": "boolean",
  "data": [
    {
      "id": "integer",
      "travel_transaction_id": "integer",
      "travel_posting_customer_id": "integer",
      "time_dep": "string",
      "description": "text",
      "status": "integer",
      "note": "text",
      "payment_type": "integer",
      "total_price": "integer",
      "createdAt": "date",
      "updatedAt": "date",
      "isDeleted": "integer",
      "seat_offer": [
        {
          "id": "integer",
          "travel_order_id": "integer",
          "travel_seat_id": "integer",
          "price": "integer",
          "is_accepted": "integer",
          "createdAt": "date",
          "updatedAt": "date",
          "isDeleted": "integer",
          "travel_seat": {
            "id": "integer",
            "travel_transaction_id": "integer",
            "seat_name": "string",
            "is_taken": "integer",
            "createdAt": "date",
            "updatedAt": "date",
            "isDeleted": "integer"
          }
        }
      ],
      "travel_posting_customer": {
        "id": "integer",
        "user_id": "integer",
        "city_origin": "string",
        "city_destination": "string",
        "address_origin": "text",
        "address_destination": "text",
        "date_dep": "date",
        "passenger_count": "integer",
        "status": "integer",
        "description": "text",
        "createdAt": "date",
        "updatedAt": "date",
        "isDeleted": "integer",
        "passenger": [
          {
            "id": "integer",
            "name": "string",
            "relation": "string",
            "phone_number": "string"
          }
        ]
      },
      "travel_transaction": {
        "id": "integer",
        "rider_id": "integer",
        "dateTimeStart": "date",
        "dateTimeFinish": "date",
        "status": "integer",
        "date_dep": "date",
        "is_urgent": "integer",
        "createdAt": "date",
        "updatedAt": "date",
        "isDeleted": "integer"
      },
      "travel_chat_room": {
        "id": "integer",
        "travel_order_id": "integer",
        "createdAt": "date",
        "updatedAt": "date",
        "isDeleted": "integer"
      }
    }
  ]
}
```

## List Offer By Travel Transaction

API ini digunakan untuk melihat offer yang masuk kepada customer berdasarkan Posting Customer ID. Kondisinya adalah travel order yang statusnya = 1.

Request :

- Method : POST
- Endpoint : `/travelorder/listOfferByTravelTrx`
- Header :
  - Content-Type: application/json
  - Accept: application/json
- Body :

```json
{
  "travel_transaction_id": "integer"
}
```

Response :

```json
{
  "success": "boolean",
  "data": [
    {
      "id": "integer",
      "travel_transaction_id": "integer",
      "travel_posting_customer_id": "integer",
      "time_dep": "string",
      "description": "text",
      "status": "integer",
      "note": "text",
      "payment_type": "integer",
      "total_price": "integer",
      "createdAt": "date",
      "updatedAt": "date",
      "isDeleted": "integer",
      "seat_offer": [
        {
          "id": "integer",
          "travel_order_id": "integer",
          "travel_seat_id": "integer",
          "price": "integer",
          "is_accepted": "integer",
          "createdAt": "date",
          "updatedAt": "date",
          "isDeleted": "integer",
          "travel_seat": {
            "id": "integer",
            "travel_transaction_id": "integer",
            "seat_name": "string",
            "is_taken": "integer",
            "createdAt": "date",
            "updatedAt": "date",
            "isDeleted": "integer"
          }
        }
      ],
      "travel_posting_customer": {
        "id": "integer",
        "user_id": "integer",
        "city_origin": "string",
        "city_destination": "string",
        "address_origin": "text",
        "address_destination": "text",
        "date_dep": "date",
        "passenger_count": "integer",
        "status": "integer",
        "description": "text",
        "createdAt": "date",
        "updatedAt": "date",
        "isDeleted": "integer",
        "passenger": [
          {
            "id": "integer",
            "name": "string",
            "relation": "string",
            "phone_number": "string"
          }
        ]
      },
      "travel_chat_room": {
        "id": "integer",
        "travel_order_id": "integer",
        "createdAt": "date",
        "updatedAt": "date",
        "isDeleted": "integer"
      }
    }
  ]
}
```

## List Accepted By Travel Transaction

API ini digunakan untuk melihat offer yang diterima customer berdasarkan Posting Customer ID. Kondisinya adalah travel order yang statusnya = [2,3,4,5].

Request :

- Method : POST
- Endpoint : `/travelorder/listAcceptedByTravelTrx`
- Header :
  - Content-Type: application/json
  - Accept: application/json
- Body :

```json
{
  "travel_transaction_id": "integer"
}
```

Response :

```json
{
  "success": "boolean",
  "data": [
    {
      "id": "integer",
      "travel_transaction_id": "integer",
      "travel_posting_customer_id": "integer",
      "time_dep": "string",
      "description": "text",
      "status": "integer",
      "note": "text",
      "payment_type": "integer",
      "total_price": "integer",
      "createdAt": "date",
      "updatedAt": "date",
      "isDeleted": "integer",
      "seat_offer": [
        {
          "id": "integer",
          "travel_order_id": "integer",
          "travel_seat_id": "integer",
          "price": "integer",
          "is_accepted": "integer",
          "createdAt": "date",
          "updatedAt": "date",
          "isDeleted": "integer",
          "travel_seat": {
            "id": "integer",
            "travel_transaction_id": "integer",
            "seat_name": "string",
            "is_taken": "integer",
            "createdAt": "date",
            "updatedAt": "date",
            "isDeleted": "integer"
          }
        }
      ],
      "travel_posting_customer": {
        "id": "integer",
        "user_id": "integer",
        "city_origin": "string",
        "city_destination": "string",
        "address_origin": "text",
        "address_destination": "text",
        "date_dep": "date",
        "passenger_count": "integer",
        "status": "integer",
        "description": "text",
        "createdAt": "date",
        "updatedAt": "date",
        "isDeleted": "integer",
        "passenger": [
          {
            "id": "integer",
            "name": "string",
            "relation": "string",
            "phone_number": "string"
          }
        ]
      },
      "travel_chat_room": {
        "id": "integer",
        "travel_order_id": "integer",
        "createdAt": "date",
        "updatedAt": "date",
        "isDeleted": "integer"
      },
      "user": {
        "username": "string",
        "image": "string",
        "phone": "string"
      }
    }
  ]
}
```

## List Offer By Customer Posting

API ini digunakan untuk melihat offer yang masuk kepada customer berdasarkan Posting Customer ID. Kondisinya adalah travel order yang statusnya = 1.

Request :

- Method : POST
- Endpoint : `/travelorder/listOfferByCustomerPosting`
- Header :
  - Content-Type: application/json
  - Accept: application/json
- Body :

```json
{
  "travel_posting_customer_id": "integer"
}
```

Response :

```json
{
  "success": "boolean",
  "data": [
    {
      "id": "integer",
      "travel_transaction_id": "integer",
      "travel_posting_customer_id": "integer",
      "time_dep": "string",
      "description": "text",
      "status": "integer",
      "note": "text",
      "payment_type": "integer",
      "total_price": "integer",
      "createdAt": "date",
      "updatedAt": "date",
      "isDeleted": "integer",
      "seat_offer": [
        {
          "id": "integer",
          "travel_order_id": "integer",
          "travel_seat_id": "integer",
          "price": "integer",
          "is_accepted": "integer",
          "createdAt": "date",
          "updatedAt": "date",
          "isDeleted": "integer",
          "travel_seat": {
            "id": "integer",
            "travel_transaction_id": "integer",
            "seat_name": "string",
            "is_taken": "integer",
            "createdAt": "date",
            "updatedAt": "date",
            "isDeleted": "integer"
          }
        }
      ],
      "travel_posting_customer": {
        "id": "integer",
        "user_id": "integer",
        "city_origin": "string",
        "city_destination": "string",
        "address_origin": "text",
        "address_destination": "text",
        "date_dep": "date",
        "passenger_count": "integer",
        "status": "integer",
        "description": "text",
        "createdAt": "date",
        "updatedAt": "date",
        "isDeleted": "integer",
        "passenger": [
          {
            "id": "integer",
            "name": "string",
            "relation": "string",
            "phone_number": "string"
          }
        ]
      },
      "travel_transaction": {
        "id": "integer",
        "rider_id": "integer",
        "dateTimeStart": "date",
        "dateTimeFinish": "date",
        "status": "integer",
        "date_dep": "date",
        "is_urgent": "integer",
        "createdAt": "date",
        "updatedAt": "date",
        "isDeleted": "integer"
      },
      "travel_chat_room": {
        "id": "integer",
        "travel_order_id": "integer",
        "createdAt": "date",
        "updatedAt": "date",
        "isDeleted": "integer"
      }
    }
  ]
}
```

## Find By ID

Request :

- Method : GET
- Endpoint : `/travelorder/{id}`
- Header :
  - Content-Type: application/json
  - Accept: application/json

Response :

```json
{
  "success": "boolean",
  "data": [
    {
      "id": "integer",
      "travel_transaction_id": "integer",
      "travel_posting_customer_id": "integer",
      "time_dep": "string",
      "description": "text",
      "status": "integer",
      "note": "text",
      "payment_type": "integer",
      "total_price": "integer",
      "createdAt": "date",
      "updatedAt": "date",
      "isDeleted": "integer",
      "seat_offer": [
        {
          "id": "integer",
          "travel_order_id": "integer",
          "travel_seat_id": "integer",
          "price": "integer",
          "is_accepted": "integer",
          "createdAt": "date",
          "updatedAt": "date",
          "isDeleted": "integer",
          "travel_seat": {
            "id": "integer",
            "travel_transaction_id": "integer",
            "seat_name": "string",
            "is_taken": "integer",
            "createdAt": "date",
            "updatedAt": "date",
            "isDeleted": "integer"
          }
        }
      ],
      "travel_posting_customer": {
        "id": "integer",
        "user_id": "integer",
        "city_origin": "string",
        "city_destination": "string",
        "address_origin": "text",
        "address_destination": "text",
        "date_dep": "date",
        "passenger_count": "integer",
        "status": "integer",
        "description": "text",
        "createdAt": "date",
        "updatedAt": "date",
        "isDeleted": "integer",
        "passenger": [
          {
            "id": "integer",
            "name": "string",
            "relation": "string",
            "phone_number": "string"
          }
        ]
      },
      "travel_transaction": {
        "id": "integer",
        "rider_id": "integer",
        "dateTimeStart": "date",
        "dateTimeFinish": "date",
        "status": "integer",
        "date_dep": "date",
        "is_urgent": "integer",
        "createdAt": "date",
        "updatedAt": "date",
        "isDeleted": "integer"
      },
      "travel_chat_room": {
        "id": "integer",
        "travel_order_id": "integer",
        "createdAt": "date",
        "updatedAt": "date",
        "isDeleted": "integer"
      }
    }
  ]
}
```

## Update

Request :

- Method : POST
- Endpoint : `/travelorder/update/{id}`
- Header :
  - Content-Type: application/json
  - Accept: application/json
- Body :

```json
{
  "time_dep": "date", //optional
  "status": "integer", //optional
  "description": "text", //optional
  "note": "text", //optional
  "payment_type": "integer", //optional
  "total_price": "integer" //optional
}
```

Response :

```json
{
  "success": "boolean",
  "data": {
    "id": "integer",
    "travel_transaction_id": "integer",
    "travel_posting_customer_id": "integer",
    "time_dep": "string",
    "description": "text",
    "status": "integer",
    "note": "text",
    "payment_type": "integer",
    "total_price": "integer",
    "createdAt": "date",
    "updatedAt": "date",
    "isDeleted": "integer",
    "seat_offer": [
      {
        "id": "integer",
        "travel_order_id": "integer",
        "travel_seat_id": "integer",
        "price": "integer",
        "is_accepted": "integer",
        "createdAt": "date",
        "updatedAt": "date",
        "isDeleted": "integer",
        "travel_seat": {
          "id": "integer",
          "travel_transaction_id": "integer",
          "seat_name": "string",
          "is_taken": "integer",
          "createdAt": "date",
          "updatedAt": "date",
          "isDeleted": "integer"
        }
      }
    ],
    "travel_posting_customer": {
      "id": "integer",
      "user_id": "integer",
      "city_origin": "string",
      "city_destination": "string",
      "address_origin": "text",
      "address_destination": "text",
      "date_dep": "date",
      "passenger_count": "integer",
      "status": "integer",
      "description": "text",
      "createdAt": "date",
      "updatedAt": "date",
      "isDeleted": "integer",
      "passenger": [
        {
          "id": "integer",
          "name": "string",
          "relation": "string",
          "phone_number": "string"
        }
      ]
    },
    "travel_transaction": {
      "id": "integer",
      "rider_id": "integer",
      "dateTimeStart": "date",
      "dateTimeFinish": "date",
      "status": "integer",
      "date_dep": "date",
      "is_urgent": "integer",
      "createdAt": "date",
      "updatedAt": "date",
      "isDeleted": "integer"
    },
    "travel_chat_room": {
      "id": "integer",
      "travel_order_id": "integer",
      "createdAt": "date",
      "updatedAt": "date",
      "isDeleted": "integer"
    }
  }
}
```

## Delete

Request :

- Method : GET
- Endpoint : `/travelorder/delete/{id}`
- Header :
  - Content-Type: application/json
  - Accept: application/json

Response :

```json
{
  "success": "boolean",
  "data": "Travel Order has been deleted successfully"
}
```

## Accept Offer

API ini digunakan untuk menerima offer/order berdasarkan ID order dan ubah status menjadi 2. dan mengubah semua order pada customer posting tersebut selain dari pada ID order ini statusnya menjadi 13. dan note = "Customer menerima Penawaran dari driver lain"

Kemudian berdasarkan payload "accepted_seat_id", ubah field "is_accepted" pada table seat_offer yang sesuai dengan id tersebut menjadi 1. kemudian cek table parent nya (travel_seat), ubah field "is_taken" menjadi 1

If "payment_type" == 2, maka create "user_transactions" dengan detail :

```json
{
  "user_id": "body.user_id",
  "order_id": "body.travel_order_id",
  "trx_type": 2,
  "datetime_saldo": "timestamp",
  "amount": "body.total_price",
  "note": "Pembayaran cashless travel order",
  "order_type": "travel_order"
}
```

terus update user balance, balance = balance-total_price

Request :

- Method : POST
- Endpoint : `/travelorder/acceptOffer`
- Header :
  - Content-Type: application/json
  - Accept: application/json
- Body :

```json
{
  "travel_order_id": "integer",
  "payment_type": "integer",
  "total_price": "integer",
  "user_id": "integer",
  "accepted_seat_id": []
}
```

Response :

```json
{
  "success": "boolean",
  "data": {
    "id": "integer",
    "travel_transaction_id": "integer",
    "travel_posting_customer_id": "integer",
    "time_dep": "string",
    "description": "text",
    "status": "integer",
    "note": "text",
    "payment_type": "integer",
    "total_price": "integer",
    "createdAt": "date",
    "updatedAt": "date",
    "isDeleted": "integer",
    "accepted_seat_offer": [
      {
        "id": "integer",
        "travel_order_id": "integer",
        "travel_seat_id": "integer",
        "price": "integer",
        "is_accepted": "integer",
        "createdAt": "date",
        "updatedAt": "date",
        "isDeleted": "integer",
        "travel_seat": {
          "id": "integer",
          "travel_transaction_id": "integer",
          "seat_name": "string",
          "is_taken": "integer",
          "createdAt": "date",
          "updatedAt": "date",
          "isDeleted": "integer"
        }
      }
    ]
  }
}
```

## Refuse All Offer By Customer Posting ID

API ini digunakan untuk menolak semua offer/order yang diajukan driver terhadap posting si customer. Jadi berdasarkan id posting customer, cari semua order yg memakai id tersebut, dan ubah status menjadi 13. dan update Note di data travel_order tersebut menjadi "Customer merubah detail Pesanan Travel."

Request :

- Method : POST
- Endpoint : `/travelorder/refuseAllByPostingCustomer`
- Header :
  - Content-Type: application/json
  - Accept: application/json
- Body :

```json
{
  "travel_posting_customer_id": "integer"
}
```

Response :

```json
{
  "success": "boolean",
  "data": [
    {
      "id": "integer",
      "travel_transaction_id": "integer",
      "travel_posting_customer_id": "integer",
      "time_dep": "string",
      "description": "text",
      "status": "integer",
      "note": "text",
      "payment_type": "integer",
      "total_price": "integer",
      "createdAt": "date",
      "updatedAt": "date",
      "isDeleted": "integer",
      "seat_offer": [
        {
          "id": "integer",
          "travel_order_id": "integer",
          "travel_seat_id": "integer",
          "price": "integer",
          "is_accepted": "integer",
          "createdAt": "date",
          "updatedAt": "date",
          "isDeleted": "integer",
          "travel_seat": {
            "id": "integer",
            "travel_transaction_id": "integer",
            "seat_name": "string",
            "is_taken": "integer",
            "createdAt": "date",
            "updatedAt": "date",
            "isDeleted": "integer"
          }
        }
      ]
    }
  ]
}
```

## Refuse Offer

API ini digunakan untuk menolak offer/order berdasarkan ID order dan ubah status menjadi 13. dan update alasannya (note).

Request :

- Method : POST
- Endpoint : `/travelorder/refuseOffer`
- Header :
  - Content-Type: application/json
  - Accept: application/json
- Body :

```json
{
  "travel_order_id": "integer",
  "note": "text"
}
```

Response :

```json
{
  "success": "boolean",
  "data": {
    "id": "integer",
    "travel_transaction_id": "integer",
    "travel_posting_customer_id": "integer",
    "time_dep": "string",
    "description": "text",
    "status": "integer",
    "note": "text",
    "payment_type": "integer",
    "total_price": "integer",
    "createdAt": "date",
    "updatedAt": "date",
    "isDeleted": "integer",
    "seat_offer": [
      {
        "id": "integer",
        "travel_order_id": "integer",
        "travel_seat_id": "integer",
        "price": "integer",
        "is_accepted": "integer",
        "createdAt": "date",
        "updatedAt": "date",
        "isDeleted": "integer",
        "travel_seat": {
          "id": "integer",
          "travel_transaction_id": "integer",
          "seat_name": "string",
          "is_taken": "integer",
          "createdAt": "date",
          "updatedAt": "date",
          "isDeleted": "integer"
        }
      }
    ]
  }
}
```

## Cancel Offer

API ini digunakan untuk membatalkan offer/order dari pihak driver berdasarkan ID order dan ubah status menjadi 12. dan update alasannya (note).

Request :

- Method : POST
- Endpoint : `/travelorder/cancelOffer`
- Header :
  - Content-Type: application/json
  - Accept: application/json
- Body :

```json
{
  "travel_order_id": "integer",
  "note": "text"
}
```

Response :

```json
{
  "success": "boolean",
  "data": {
    "id": "integer",
    "travel_transaction_id": "integer",
    "travel_posting_customer_id": "integer",
    "time_dep": "string",
    "description": "text",
    "status": "integer",
    "note": "text",
    "payment_type": "integer",
    "total_price": "integer",
    "createdAt": "date",
    "updatedAt": "date",
    "isDeleted": "integer",
    "seat_offer": [
      {
        "id": "integer",
        "travel_order_id": "integer",
        "travel_seat_id": "integer",
        "price": "integer",
        "is_accepted": "integer",
        "createdAt": "date",
        "updatedAt": "date",
        "isDeleted": "integer",
        "travel_seat": {
          "id": "integer",
          "travel_transaction_id": "integer",
          "seat_name": "string",
          "is_taken": "integer",
          "createdAt": "date",
          "updatedAt": "date",
          "isDeleted": "integer"
        }
      }
    ]
  }
}
```

# Travel Chat Message

API untuk menampung chat antara driver dan penumpang berdasarkan order yang telah terbuat

## Create

Request :

- Method : POST
- Endpoint : `/travelchatmsg/create`
- Header :
  - Content-Type: application/json
  - Accept: application/json
- Body :

```json
{
  "room_id": "integer", //diambil dari id travel chat room
  "message": "text", //eg : Lorem Ipsum
  "type": "integer" //eg : 1.  1 = driver, 2 = customer
}
```

Response :

```json
{
  "success": "boolean",
  "data": {
    "id": "integer",
    "room_id": "integer",
    "message": "string",
    "type": "string",
    "createdAt": "date",
    "updatedAt": "date"
  }
}
```

## List by Room Chat

Request :

- Method : POST
- Endpoint : `/travelchatmsg/listbyroomchat`
- Header :
  - Content-Type: application/json
  - Accept: application/json
- Body :

```json
{
  "room_id": "integer" //diambil dari id travel chat room
}
```

Response :

```json
{
  "success": "boolean",
  "data": {
    "room_id": "integer",
    "messages": [
      {
        "id": "integer",
        "room_id": "integer",
        "message": "string",
        "type": "string",
        "createdAt": "date",
        "updatedAt": "date",
        "isDeleted": "date"
      }
    ]
  }
}
```

# Activity Driver

API ini untuk halaman activity pada driver app

## List Active By Rider ID

List sebagai berikut :
Data Nebeng Posting dengan Status = [1,2]

Data Nitip Posting dengan Status = [1,2]

Data Travel Transaction dengan Status = [1,2]

Request :

- Method : POST
- Endpoint : `/activity_driver/listActiveByRiderId`
- Header :
  - Content-Type: application/json
  - Accept: application/json
- Body :

```json
{
  "rider_id": "integer" //diambil dari id driver
}
```

Response :

```json
{
  "success": "boolean",
  "data": {
    "nebeng_posting": [
      {
        "id": "integer",
        "rider_id": "integer",
        "dateTimeStart": "date",
        "dateTimeFinish": "date",
        "city_origin": "string",
        "city_destination": "string",
        "dateDep": "date",
        "dateArr": "date",
        "timeDep": "time",
        "timeArr": "time",
        "seatAvail": "integer",
        "price": "integer",
        "status": "integer",
        "status_update": "integer",
        "note": "string",
        "desc": "string",
        "is_urgent": "integer",
        "createdAt": "date",
        "updatedAt": "date",
        "isDeleted": "integer"
      }
    ],
    "nitip_posting": [
      {
        "id": "integer",
        "rider_id": "integer",
        "dateTimeStart": "date",
        "dateTimeFinish": "date",
        "city_origin": "string",
        "city_destination": "string",
        "dateDep": "date",
        "dateArr": "date",
        "timeDep": "time",
        "timeArr": "time",
        "status": "integer",
        "desc": "string",
        "note": "string",
        "is_open": "integer",
        "is_urgent": "integer",
        "is_update": "integer",
        "createdAt": "date",
        "updatedAt": "date",
        "isDeleted": "integer"
      }
    ],
    "travel_transaction": [
      {
        "id": "integer",
        "rider_id": "integer",
        "dateTimeStart": "date",
        "dateTimeFinish": "date",
        "status": "integer",
        "dateDep": "date",
        "desc": "string",
        "note": "string",
        "is_urgent": "integer",
        "createdAt": "date",
        "updatedAt": "date",
        "isDeleted": "integer"
      }
    ]
  }
}
```

## List Done By Rider ID

List sebagai berikut :
Data Nebeng Posting dengan Status = [3,4]

Data Nitip Posting dengan Status = [3,4]

Data Travel Transaction dengan Status = [3,4]

Urutkan berdasarkan Created At Descending

Request :

- Method : POST
- Endpoint : `/activity_driver/listDoneByRiderId`
- Header :
  - Content-Type: application/json
  - Accept: application/json
- Body :

```json
{
  "rider_id": "integer" //diambil dari id driver
}
```

Response :

```json
{
  "success": "boolean",
  "data": {
    "nebeng_posting": [
      {
        "id": "integer",
        "rider_id": "integer",
        "dateTimeStart": "date",
        "dateTimeFinish": "date",
        "city_origin": "string",
        "city_destination": "string",
        "dateDep": "date",
        "dateArr": "date",
        "timeDep": "time",
        "timeArr": "time",
        "seatAvail": "integer",
        "price": "integer",
        "status": "integer",
        "status_update": "integer",
        "note": "string",
        "desc": "string",
        "is_urgent": "integer",
        "createdAt": "date",
        "updatedAt": "date",
        "isDeleted": "integer"
      }
    ],
    "nitip_posting": [
      {
        "id": "integer",
        "rider_id": "integer",
        "dateTimeStart": "date",
        "dateTimeFinish": "date",
        "city_origin": "string",
        "city_destination": "string",
        "dateDep": "date",
        "dateArr": "date",
        "timeDep": "time",
        "timeArr": "time",
        "status": "integer",
        "desc": "string",
        "note": "string",
        "is_open": "integer",
        "is_urgent": "integer",
        "is_update": "integer",
        "createdAt": "date",
        "updatedAt": "date",
        "isDeleted": "integer"
      }
    ],
    "travel_transaction": [
      {
        "id": "integer",
        "rider_id": "integer",
        "dateTimeStart": "date",
        "dateTimeFinish": "date",
        "status": "integer",
        "dateDep": "date",
        "desc": "string",
        "note": "string",
        "is_urgent": "integer",
        "createdAt": "date",
        "updatedAt": "date",
        "isDeleted": "integer"
      }
    ]
  }
}
```
