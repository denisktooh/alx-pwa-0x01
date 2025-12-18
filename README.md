# MoviesDatabase API Documentation

## API Overview
MoviesDatabase provides data for over 9 million titles (movies, series, episodes) and 11 million actors/crew members. Updated weekly with ratings refreshed daily.

## Version
v1 (current)

## Available Endpoints
- `GET /titles` - Search titles with filters
- `GET /titles/{id}` - Get single title details
- `GET /titles/{id}/ratings` - Get title ratings
- `GET /titles/series/{seriesId}` - Get series episodes
- `GET /titles/search/title/{title}` - Search by title name
- `GET /actors/{id}` - Get actor details

## Request and Response Format
**Request:**
```
GET /titles?limit=10&genre=Action&info=base_info
```

**Response:**
```json
{
  "results": [...],
  "page": 1,
  "entries": 10
}
```

## Authentication
Include RapidAPI key in request headers via RapidAPI Hub.

## Error Handling
Handle failed requests with try-catch blocks. Check response status codes and parse error messages from response body.

## Usage Limits and Best Practices
- Max 50 entries per request
- Use `info` parameter to get only needed data
- Cache frequently accessed data
- Batch ID lookups using `/x/titles-by-ids`