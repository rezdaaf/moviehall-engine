# moviehall-engine

This project was made to complete assignment at the end of the training session for internship at tiket.com

Author: Rezda Abdullah Fachrezzi (Backend Engineer Intern)

## Description

This service holds data for Movie Hall. The data are stored in MovieHall and Seat entity.

## Setup

What you need to have and set up before running this service

1. Java 11
2. MongoDB
3. Your favorite IDE

Update below fields in the `application.properties`

```
spring.data.mongodb.uri= // mongodb connection string
spring.data.mongodb.database= // database name
```

## Run

You can run the service from the main application

## API

### `GET` /api/movie_hall
Find all movie halls

#### Request Query
1. name `string` : to search all movie halls containing the name

#### Response Example
```JSON
[
    {
        "id": "fdsfst43gfd",
        "name": "GI XXI",
        "active": false
    }
]
```

### `GET` /api/movie_hall/active
Find all active movie halls

#### Response Example
```JSON
[
    {
        "id": "2324sdfsdg",
        "name": "Gading XXI",
        "active": true
    }
]
```

### `GET` /api/movie_hall/{id}
Find movie hall by id

#### Request Params
1. id `string` : movie hall id

#### Response Example
```JSON
{
    "id": "2324sdfsdg",
    "name": "Gading XXI",
    "active": true
}
```

### `POST` /api/movie_hall
Create new movie hall

#### Request Body
1. name `string` : movie hall name
2. active `boolean` : is the hall active

#### Response Example
```JSON
{
    "id": "2324sdfsdg",
    "name": "Gading XXI",
    "active": true
}
```

### `PUT` /api/movie_hall/{id}
Update movie hall by id

#### Request Params
1. id `int` : movie hall id

#### Request Body
1. name `string` `optional` : movie hall name
2. active `boolean` `optional` : is the hall active

#### Response Example
```JSON
{
    "id": "2324sdfsdg",
    "name": "Gading XXI",
    "active": true
}
```

### `DELETE` /api/movie_hall/{id}
Delete movie hall by id

#### Request Params
1. id `string` : movie hall id

#### Response Example
```JSON
```

### `GET` /api/movie_hall/{id}/seat
Get all movie hall seats

#### Request Params
1. id `string` : movie hall id

#### Response Example
```JSON
[ 
    {
        "id": "fdsfsfsdf",
        "row": 1,
        "number": 1,
        "hallId": "2324sdfsdg",
        "active": true
    }
]
```

### `GET` /api/movie_hall/{id}/seat
Get all active movie hall seats

#### Request Params
1. id `string` : movie hall id

#### Response Example
```JSON
[ 
    {
        "id": "fdsfsfsdf",
        "row": 1,
        "number": 1,
        "hallId": "2324sdfsdg",
        "active": true
    }
]
```

### `GET` /api/seat
Find all seats

#### Request Query
1. row `int` : seat row
2. number `int` : seat number

#### Response Example
```JSON
[
    {
        "id": "fdsfsfsdf",
        "row": 1,
        "number": 1,
        "hallId": "2324sdfsdg",
        "active": true
    }
]
```

### `GET` /api/seat/active
Find all active seats

#### Response Example
```JSON
[
    {
        "id": "fdsfsfsdf",
        "row": 1,
        "number": 1,
        "hallId": "2324sdfsdg",
        "active": true
    }
]
```

### `GET` /api/seat/{id}
Find seat by id

#### Request Params
1. id `string` : seat id

#### Response Example
```JSON
{
    "id": "fdsfsfsdf",
    "row": 1,
    "number": 1,
    "hallId": "2324sdfsdg",
    "active": true
}
```

### `POST` /api/seat
Create new seat

#### Request Body
1. hallId `string` : associated movie hall id
2. row `int` : seat row
3. number `int` : seat number
4. active `boolean` : is seat active

#### Response Example
```JSON
{
    "id": "fdsfsfsdf",
    "row": 1,
    "number": 1,
    "hallId": "2324sdfsdg",
    "active": true
}
```

### `PUT` /api/seat/{id}
Update seat by id

#### Request Params
1. id `int` : seat id

#### Request Body
1. hallId `string` `optional` : associated movie hall id
2. row `int` `optional` : seat row
3. number `int` `optional` : seat number
4. active `boolean` `optional` : is seat active

#### Response Example
```JSON
{
    "id": "fdsfsfsdf",
    "row": 1,
    "number": 1,
    "hallId": "2324sdfsdg",
    "active": true
}
```

### `DELETE` /api/seat/{id}
Delete seat by id

#### Request Params
1. id `string` : seat id

#### Response Example
```JSON
```

### `GET` /api/seat/detail
Find seat by row, number, and hallId

#### Request Query
1. row `int` : seat row
2. number `int` : seat number
3. hallId `string` : associated hall id

#### Response Example
```JSON
{
    "id": "fdsfsfsdf",
    "row": 1,
    "number": 1,
    "hallId": "2324sdfsdg",
    "active": true
}
```
