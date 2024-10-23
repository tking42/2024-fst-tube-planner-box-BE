# Furniture Store API - README

### Introduction

This simple API serves as the back-end for our Journey Planner application, designed to provide station and route  information to our React-based front-end. It allows users to retrieve details about stations and their desired route. The API only supports GET requests and provides data in JSON format.

### API documentation

GET /

This endpoint retrieves a list of all available stations. 

Example Response (if there were three stations): 

``` JSON

{
        "id": 1,
        "line": "Bakerloo",
        "code": "BST",
        "name": "Baker Street",
        "time_to_prev": null,
        "time_to_next": 196,
        "zone": 5
    },
    {
        "id": 2,
        "line": "Bakerloo",
        "code": "CHX",
        "name": "Charing Cross",
        "time_to_prev": 196,
        "time_to_next": 199,
        "zone": 3
    },
    {
        "id": 3,
        "line": "Bakerloo",
        "code": "ERB",
        "name": "Edgware Road (Bakerloo)",
        "time_to_prev": 199,
        "time_to_next": 234,
        "zone": 3
    }
}
```

GET /route 

This endpoint calculates the route between two specified locations.

Parameters:

from: string (e.g., BST) — The starting location.
to: string (e.g., ERB) — The destination location.

Example response: 

``` JSON

[
    {
        "id": 3,
        "line": "Bakerloo",
        "code": "ERB",
        "name": "Edgware Road (Bakerloo)",
        "time_to_prev": 199,
        "time_to_next": 234,
        "zone": 3
    },
    {
        "id": 2,
        "line": "Bakerloo",
        "code": "CHX",
        "name": "Charing Cross",
        "time_to_prev": 196,
        "time_to_next": 199,
        "zone": 3
    },
    {
        "id": 1,
        "line": "Bakerloo",
        "code": "BST",
        "name": "Baker Street",
        "time_to_prev": null,
        "time_to_next": 196,
        "zone": 5
    }
]
```
    
    



