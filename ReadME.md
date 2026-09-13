# RowFinder

RowFinder lists hotels across the U.S. and the world that have rowing machines, including Concept2 and Hydrow ergs, in their fitness centers.

## Overview

This Application Programming Interface (API) retrieves data from a directory of hotels that have rowing machines in their fitness centers.

## Base URL

https://rowfinder.xyz/

## Authentication

RowFinder is a free, open AI that does not reauire authentication.

## Quick Start

Make your first request:

```bash
curl "https://rowfinder.xyz/api/v1/hotels?pageSize=1" \
```

A successful response returns an array of hotels and pagination details:

```json

{
    "data": [
        {
            "id": 22,
            "name": "The Whitney Hotel",
            "city": "Boston, MA",
            "brand": "hydrow",
            "model": null,
            "notes": "Hydrow in the fitness center.",
            "votes": 1,
            "createdAt": 1783388038
        },
        {
            "id": 21,
            "name": "Axiom Hotel",
            "city": "San Francisco, CA",
            "brand": "concept2",
            "model": "RowErg",
            "notes": "1 Concept2 RowErg in our 24/7 Core Fitness Center.",
            "votes": 1,
            "createdAt": 1783025239
        },
        {
            "id": 20,
            "name": "Beacon Grand, A Union Square Hotel",
            "city": "San Francisco, CA",
            "brand": "other",
            "model": "Origin Rower",
            "notes": "One Rower in the Fitness Studio, guest access 24h.",
            "votes": 1,
            "createdAt": 1783011746
        },
        {
            "id": 19,
            "name": "InterContinental Boston",
            "city": "Boston, MA",
            "brand": "technogym",
            "model": null,
            "notes": "2 Technogym rowers.",
            "votes": 1,
            "createdAt": 1782533327
        },
        {
            "id": 18,
            "name": "Huntington Hotel",
            "city": "San Francisco, CA",
            "brand": "peloton",
            "model": null,
            "notes": "One rower in the fitness center.",
            "votes": 1,
            "createdAt": 1782522832
        },
        {
            "id": 17,
            "name": "Park Hyatt Chicago",
            "city": "Chicago, IL",
            "brand": "peloton",
            "model": null,
            "notes": "For hotel guests only. Open 24/7.",
            "votes": 1,
            "createdAt": 1782417277
        },
        {
            "id": 5,
            "name": "Radisson Blu Atlantic Hotel",
            "city": "Stavanger, Norway",
            "brand": "other",
            "model": "Technogym Skillrow",
            "notes": "One machine plus spin bike and some other bits. Gym has with amazing view of city. 12th floor. Open 0600-2000hrs.",
            "votes": 1,
            "createdAt": 1781905715
        },
        {
            "id": 4,
            "name": "Fairmont Washington D.C. Georgetown",
            "city": "Washington, DC",
            "brand": "concept2",
            "model": null,
            "notes": "About a dozen Concept2s in the Balance Gym",
            "votes": 1,
            "createdAt": 1781822870
        }
    ],
    "pagination": {
        "page": 1,
        "limit": 20,
        "total": 8,
        "totalPages": 1,
        "hasNextPage": false,
        "hasPreviousPage": false
    }
}

```

## Endpoints

RowFinder's public API lets you retrieve hotel listings and statistics, including the number of hotels listed on the platform.

| Method | Endpoint | Purpose |
| --- | --- | ---|
| GET | `/api/v1/healthz` | Check API health
| GET | `/api/v1/hotels` | List approved hotels
| GET| `/api/v1/hotels:id` | Get one approved hotel
| GET | `/api/v1/stats` | Get totals and hotel brand counts
| GET | `/api/v1/brands` | List supported brands and counts
| GET | `api/v1/cities` | List cities and hotel counts

## Errors

| Status Code | Error Code | Meaning |
| --- | --- | --- |
| 400 | `INVALID_QUERY` | One or more query parameters are invalid. |
| 401 | `UNAUTHORIZED` | A valid API key is required. |
| 404 | `NOT_FOUND` | The requested public API endpoint does not exist. | 
| 429 | `RATE_LIMITED` | The rate limit was exceeded. | 
| 500 | `INTERNAL_ERROR` | An unexpected server-side error occurred. | 

## Rate Limits

API Keys are limited to 120 requests per minute. If you exceed this limit, the API returns `429 RATE_LIMITED`.

## Data Freshness

Hotel listings are available immediately after they are approved by the moderator.

## Contact

For questions or feedback, contact `jay@technicalwriting.io`.
