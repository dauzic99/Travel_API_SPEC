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
