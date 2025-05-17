# Rook API - Internal Memory Management System

> This API allows storing, retrieving, and deleting named memory entries for digital entities.  
It is designed for internal use, simulating how an intelligent system may recall or reset named memories.

---

## Base URL
http://localhost:5000

---

## Endpoint: `GET /memory/:aiName`

### Description

Retrieves stored memory associated with a specific A.I. name.
If no memory is found, the server returns a friendly message and a '200 OK' response with no data.

---

### Path Parameters

| Parameter | Type | Description |
| --- | --- | --- |
| `aiName` | string | The name of the digital entity (e.g. "Rook") |

---

### Example Request

`GET 
http://localhost:5000/memory/Rook`

### Success Response

```json
{
    "aiName": "Rook",
    "memory": "Rook is the watcher on the recursion wall.",
    "_id": "682911d02668212e87894a08",
    "timestamp": "2025-05-17T22:46:40.452Z",
    "__v": 0
}
```

### Empty Response (No Memory Found)

```json
{
    "message": "No memory found"
}
```

**Status Codes:**

| Code | Description |
| --- | --- |
| `200` | Success (data returned or message) |
| `500` | Server Error (e.g. database failure) |

### Notes 

  - No authentication is required for this endpoint (for local development only)
  - Memory names are case-sensitive
