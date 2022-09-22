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
          "phone_number": "string"
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
  "phone_number": "string" //eg : 08778868543
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
  "phone_number": "string" //optional
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
  "is_urgent": "integer", //eg : 0
  "seat_name": "array of string"
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
    "seat": [
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
  "description": "text", //eg : Lorem Ipsum
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
  "rider_id": "integer", //optional
  "date_dep": "date", //optional
  "description": "text", //optional
  "is_urgent": "integer" //optional
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
