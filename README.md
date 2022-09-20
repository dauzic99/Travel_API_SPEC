<!-- # Travel API Spec -->

# Authentication

All API must use this authentication

Request :

- Header :
  - Authorization : Bearer {$token}

# Travel Posting Customer

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
