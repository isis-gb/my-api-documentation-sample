# API Reference and Endpoints

The Ma Radio Groove API provides access to three core resources:

* DJs
* Mixes
* Genres

These resources can be retrieved and integrated into third-party apps. 


!!! note
    In the following requests: all endpoint paths are appended to the base URL `https://api.maradiogroove.com/v1`, and all mentions of `YOUR_API_KEY` need to be replaced with the API key you generated.



### Request DJs Metadata
#### Get DJs

Use the following GET endpoint to retrieve the list of available DJs:


```bash
GET /djs
```

The API request needs to include the API key in the `Authorization` header:


```bash
curl -H "Authorization: Bearer YOUR_API_KEY" https://api.maradiogroove.com/v1/djs
```
 
A successful request returns the following JSON response:

```json
{
  "data": [
    {
      "id": "dj_001",
      "name": "DJ Groove",
      "style": "House"
    },
    {
      "id": "dj_002",
      "name": "DJ Sunset",
      "style": "RnB"
    }
  ]
}
```

### Request Mixes Metadata
#### Get Mixes for a Selected DJ

Use the following GET endpoint to retrieve mixes for a specific DJ:


```bash
GET /djs/{dj_id}/mixes
```


The API request needs to include the API key in the `Authorization` header:


```bash
curl -H "Authorization: Bearer YOUR_API_KEY" https://api.maradiogroove.com/v1/djs/dj_001/mixes
```

 
A successful request returns the following JSON response:


```json
{
  "data": [
    { "id": "mix_101", "title": "Afro House Sunset", "duration": 3600 },
    { "id": "mix_103", "title": "Evening Chill", "duration": 3000 }
  ]
}
```

#### Get Mix Details

Use the following GET endpoint to retrieve detailed information about a specific mix:


```bash
GET /mixes/{mix_id}
```


The API request needs to include the API key in the `Authorization` header:


```bash
curl -H "Authorization: Bearer YOUR_API_KEY" https://api.maradiogroove.com/v1/mixes/mix_101
```

 
A successful request returns the following JSON response:


```json
{
  "id": "mix_101",
  "title": "Afro House Sunset",
  "dj": { "id": "dj_001", "name": "DJ Groove" },
  "duration": 3600,
  "genre": "House",
  "description": "A smooth afro house mix perfect for evening private parties."
}
```

### Request Genres Metadata
#### Get Genres

Use the following GET endpoint to retrieve the list of available music genres for mixes:


```bash
GET /genres
```


The API request needs to include your API key in the `Authorization` header:


```bash
curl -H "Authorization: Bearer YOUR_API_KEY" https://api.maradiogroove.com/v1/genres
```

 
A successful request returns the following JSON response:


```json
{
  "data": [
    { "id": "genre_01", "name": "House" },
    { "id": "genre_02", "name": "Afro House" },
    { "id": "genre_03", "name": "Chill" }
  ]
}
```

