<a name="top" id="top"></a>
# Reqres API Documentation

## About This Documentation

This document provides reference and example usage for the [Reqres](https://reqres.in) mock API, a public REST API designed for practicing and testing front-end and back-end HTTP requests.

The documentation was created for educational purposes to demonstrate API structure, endpoint behavior, request/response formatting, and technical writing best practices.

All endpoints have been tested using Postman, with example requests and JSON responses included. This document was authored in Markdown and structured to follow industry-standard patterns for API reference guides, including:

- HTTP method and endpoint descriptions  
- Parameter tables  
- Request/response examples  
- Notes and expected behavior for edge cases

The project serves as part of a growing technical writing portfolio, showcasing skills in API documentation, JSON formatting, and Markdown structuring.


---

## Base URL

https://reqres.in/api

---

## Endpoints
[GET /users](#get-users)
[GET /users/:id](#get-usersid)
[POST /users](#post-users)
[PUT /users/:id](#patch-usersid)
[PATCH /users/:id](#patch-usersid)
[DELETE /users/:id](#delete-usersid)




---

## GET /users

Retrieves a paginated list of users.

### Request

```http
GET https://reqres.in/api/users?page=2
```

Query Parameters:

| Parameters | Type | Description |
| --- | --- | --- |
| page | int | Page number of users to retrieve |

**Response**

Status code: `200 OK`

```json
{
  "page": 2,
  "per_page": 6,
  "total": 12,
  "total_pages": 2,
  "data": [
    {
      "id": 7,
      "email": "michael.lawson@reqres.in",
      "first_name": "Michael",
      "last_name": "Lawson",
      "avatar": "https://reqres.in/img/faces/7-image.jpg"
    },
    {
      "id": 8,
      "email": "lindsay.ferguson@reqres.in",
      "first_name": "Lindsay",
      "last_name": "Ferguson",
      "avatar": "https://reqres.in/img/faces/8-image.jpg"
    }
    // ...more users
  ]
}
```
**Notes**

- Use this endpoint to retrieve a paginated list of users.
- Ideal for displaying multiple users across pages.
- Use the `page` parameter to navigate user sets.


<p style="text-align:left;"><a href="#top">🔝 Back to top</a></p>

---

## GET /users/:id

Retrieves a single user by their ID.

### Request

```http
GET https://reqres.in/api/users/2
```

Path Parameters:

| Parameters | Type | Description |
| --- | --- | --- |
| id | int | Unique ID of the user to retrieve |

**Response**

Status code: `404 Not Found` response is returned if no user exists for the ID.

```json
{
  "data": {
    "id": 2,
    "email": "janet.weaver@reqres.in",
    "first_name": "Janet",
    "last_name": "Weaver",
    "avatar": "https://reqres.in/img/faces/2-image.jpg"
  }
}
```
**Notes**

 - Use this endpoint to retrieve details about a specific user.
 - Data includes user ID, name, email, and avatar image URL.
 - If the ID is invalid or does not exist, a `404 Not Found` response is returned.


<p style="text-align:left;"><a href="#top">🔝 Back to top</a></p>

---

### POST /users

Creates a new user in the system.

### Request

```http
POST https://reqres.in/api/users
Content-Type: application/json
```

**Body Parameters** 
| Parameters | Type | Required | Description |
| --- | --- | --- | --- | 
| `name` | string | Yes | Name of the new user |
| `job` | string | Yes | Job title of the new user |

Example Request Body:

```json
{
  "name": "Don Johnson",
  "job": "Miami Detective"
}
```

**Response** 
Status Code: `201 Created`

```json
{
  "name": "S. Holmes",
  "job": "Detective",
  "id": "928",
  "createdAt": "2025-05-17T18:24:36.815Z"
}
```

**Notes**

  - A unique `id` is generated automatically.
  - The `createdAt` field returns a timestamp of creation.
  - This endpoint simulates user creation-no persistent data is stored.

<p style="text-align:left;"><a href="#top">🔝 Back to top</a></p>

---

## PUT /users/:id

Replaces an entire user object with new values.

### Request 

```http
PUT https://reqres.in/api/users/2
Content-Type: application/json
```

**Body Parameters**
| Parameter | Type | Required | Description | 
| --- | --- | --- | --- |
| `name` | string | Yes | Full name of the user |
| `job` | string | yes | New or updated job title |

**Example Request Body**

```json
{
  "name": "Jessica Fletcher",
  "job": "Sleuth"
}
```

**Response**

Status Code: `200 OK`

```json
{
  "name": "David Addison",
  "job": "Private Investigator",
  "updatedAt": "2025-05-17T21:48:00.000Z"
}
```
**Notes**
  - `PUT` requires all fields to be passed-even if they are unchanged.
  - The server overwrites the entire existing resource with the new object.
  - Returns the updated object with a new `updatedAt` timestamp.

<p style="text-align:left;"><a href="#top">🔝 Back to top</a></p>

---

## PATCH /users/:id

Updates part of an existing user's information.

### Request

```http
PATCH https://reqres.in/api/users/2
Content-Type: application/json
```

**Body Parameters**

| Parameter | Type | Required | Description |
| --- | --- | --- | --- |
| `name` | string | No | Only include if updating the name |
| `job` | string | No | Only include if updating the job |

**Example Request Body**

```json
{
    "job": "Vault Storage Specialist"
}
```

**Response**
Status Code: `200 OK`

```json
{
    "job": "Vault Storage Specialist",
    "updatedAt": "2025-05-17T23:51:00.00Z"
}
```
**Notes**

  - Use `PATCH` when only some fields need to be changed.
  - The server will keep all other existing values intact.
  - Returns only the updated fields and a new `updatedAt` timestamp.
  - Unlike `PUT`, this does not replace the full object.

<p style="text-align:left;"><a href="#top">🔝 Back to top</a></p>

---

## DELETE /users/:id

Deletes a user from the system by their unique ID.

### Request 

```http 
DELETE: https://reqres.in/api/users/2
```

**Response**

Status Code: `204 No Content`

Response Body:

(none)

**Notes**

  - This method removes the specified user from the system.
  - The server responds with `204 No Content` to indicate the operation succeeded.
  - No response body is returned - just silence 
  - If the user does not exist, the server may return a `404 Not Found`. 

### DELETE Summary:

| Feature | Behavior |
| --- | --- | 
| Requires ID? | Yes (`/users/:id`) |
| Response Body? | None (`204 No Content`) | 
| Reversible? | No (unless your API stores archives) |
| Use case | Permanent removal of a record | 

---

<p style="text-align:left;"><a href="#top">🔝 Back to top</a></p>
