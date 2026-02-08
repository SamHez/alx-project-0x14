# CineSeek - Movie Discovery App

## API Overview
The MoviesDatabase API is a comprehensive database providing access to vast information about movies, TV shows, and celebrities. It allows for advanced filtering by year, genre, and type, making it ideal for discovery applications.

## Version
The API is current as of the latest documentation available on RapidAPI (2024/2025 version).

## Available Endpoints
- `/titles`: Fetch a list of movie titles with various filters (year, genre, list type).
- `/titles/{id}`: Get detailed information about a specific title by its ID.
- `/titles/utils/genres`: List all available movie genres.
- `/titles/utils/lists`: List available title types (e.g., movie, tvSeries).

## Request and Response Format
### Request
A typical request to the titles endpoint:
`GET https://moviesdatabase.p.rapidapi.com/titles?year=2024&genre=Comedy&limit=10`

### Response
```json
{
  "page": 1,
  "next": "/titles?page=2",
  "entries": 10,
  "results": [
    {
      "id": "tt1234567",
      "primaryImage": {
        "url": "https://example.com/poster.jpg",
        "width": 1000,
        "height": 1500
      },
      "titleText": {
        "text": "Movie Title"
      },
      "releaseYear": {
        "year": 2024
      }
    }
  ]
}
```

## Authentication
Authentication is required via RapidAPI headers:
- `x-rapidapi-host`: `moviesdatabase.p.rapidapi.com`
- `x-rapidapi-key`: `YOUR_RAPIDAPI_KEY`

## Error Handling
Common error responses include:
- `401 Unauthorized`: Missing or invalid API key.
- `403 Forbidden`: API key does not have access to the endpoint.
- `404 Not Found`: Resource not found.
- `429 Too Many Requests`: Rate limit exceeded.

## Usage Limits and Best Practices
- **Rate Limits**: The API has specific rate limits based on your subscription plan.
- **Caching**: Implement client-side or server-side caching for frequently accessed data to minimize API calls.
- **Pagination**: Use the `limit` and `page` parameters to manage large result sets efficiently.
- **Error Boundaries**: Handle potential API failures gracefully in the UI.
