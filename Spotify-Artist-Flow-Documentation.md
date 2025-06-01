# Spotify Web API – Artist Lookup & Discovery Flow

## Overview

This guide demonstrates how to authenticate with the Spotify Web API and retrieve artist data, including albums and top tracks. It uses the Client Credentials Flow and the following endpoints:

- Search Artist
- Get Artist Albums
- Get Artist Top Tracks

---

## Authentication

Spotify requires a valid access token for all API calls.

To obtain a token using the **Client Credentials Flow**, send a `POST` request to:

`https://accounts.spotify.com/api/token` 

**Headers (Basic Auth):**
  - Username: your Client ID
  - Password: your Client Secret

**Body (x-www-form-urlencoded):** 

| Key | Value |
| --- | --- |
|grant_type | client_credentials |

**Response**

```json
{
    "access_token": "BQD...yourtoken..",
    "token_type": "Bearer",
    "expires_in": 3600
}
```

---

## Endpoint (Search)

GET  `https://api.spotify.com/v1/search?q=queen&type=artist`

| Key | Value | 
| --- | --- |
|Authorization | Bearer YOUR_ACCESS_TOKEN |

**Example Response (trimmed):**

```json
{
  "artists": {
    "items": [
      {
        "name": "Queen",
        "id": "1dfeR4HaWDbWqFHLkxsg1d",
        "genres": ["rock", "classic rock"],
        "popularity": 86
      }
    ]
  }
}
``` 
---

## Endpoint (Albums)

GET `https://api.spotify.com/v1/artists/1dfeR4HaWDbWqFHLkxsg1d/albums?include_groups=album&limit=5&market=US`

**Response:**

```json
{
  "items": [
    {
      "name": "A Night at the Opera",
      "release_date": "1975-11-21",
      "type": "album"
    },
    ...
  ]
}
```

---

## Endpoint (Top Tracks)

GET `https://api.spotify.com/v1/artists/1dfeR4HaWDbWqFHLkxsg1d/top-tracks?market=US`

**Response**

```json
{
  "tracks": [
    {
      "name": "Bohemian Rhapsody",
      "popularity": 87,
      "album": {
        "name": "A Night at the Opera"
      }
    }
  ]
}
```
---

**Notes**

 - You must include a `market` parameter when using /top-tracks.
 - Artists IDs are retrieved from the Search endpoint and reused across others.
 - Bearer tokens expire in ~1 hour-refresh as needed.

---

**Error Handling**

| Status Code | Meaning             | Possible Fixes                      |
| ----------- | ------------------- | ----------------------------------- |
| 400         | Bad Request         | Check query params and formatting   |
| 401         | Unauthorized        | Token missing or invalid            |
| 403         | Forbidden           | App permissions insufficient        |
| 429         | Rate limit exceeded | Wait or use lower request frequency |

