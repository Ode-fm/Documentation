# API Documentation

This API provides access to events, categories, locations, tags, and organizers data. Below is a detailed overview of available endpoints and their usage.

---

## Base URL
```
https://ode.fm/api/v1/
```

---

## Authentication
All requests to the API require an API key for authentication. The API key must be included as a query parameter in the request URL:
```
?key=[your_api_key]
```

For example:
```
https://ode.fm/api/v1/events/all/?key=your_api_key
```
If an invalid or missing API key is provided, the API will return a '601 Unauthorized' response.

---

## Endpoints

### 1. Events

#### GET /events/all
- **Description**: Retrieves all events.
- **Example Request**:
```
curl https://ode.fm/api/v1/events/all?key=your_api_key
```
- **Response**:
```
{
  "events": [
    {
      "eventid": 1,
      "regionid": "1",
      "categoryid": "2",
      "tags": "music,festival",
      "organizerid": "3",
      "locationid": "4",
      "urlscheme": "event-name",
      "collectionid": "1",
      "eventname": "Sample Event",
      "startdatetime": "2024-12-18 19:00:00",
      "eventdescription": "A description of the event.",
      "pricerange": "$20-$50",
      "ticketlink": "http://tickets.example.com",
      "artwork": "http://example.com/artwork.jpg"
    }
  ]
}
```

#### GET /events/region/[regionid]
- **Description**: Retrieves events filtered by region ID.
- **Example Request**:
```
curl https://ode.fm/api/v1/events/region/1/?key=your_api_key
```
- **Response**:
```
{
  "events": [
    { ... }
  ]
}
```

#### GET /events/organizer/[organizerid]
- **Description**: Retrieves events filtered by organizer ID.
- **Example Request**:
```
curl https://ode.fm/api/v1/events/organizer/3/?key=your_api_key
```
- **Response**:
```
{
  "events": [
    { ... }
  ]
}
```

#### GET /events/category/[categoryid]
- **Description**: Retrieves events filtered by category ID.
- **Example Request**:
```
curl https://ode.fm/api/v1/events/category/2/?key=your_api_key
```
- **Response**:
```
{
  "events": [
    { ... }
  ]
}
```

#### GET /events/detail/[eventid]
- **Description**: Retrieves detailed information for a specific event by ID.
- **Example Request**:
```
curl https://ode.fm/api/v1/events/detail/1/?key=your_api_key
```
- **Response**:
```
{
  "event": {
    "eventid": 1,
    "regionid": "1",
    "categoryid": "2",
    "tags": "music,festival",
    "organizerid": "3",
    "locationid": "4",
    "urlscheme": "event-name",
    "collectionid": "1",
    "eventname": "Sample Event",
    "startdatetime": "2024-12-18 19:00:00",
    "eventdescription": "A detailed description of the event.",
    "pricerange": "$20-$50",
    "ticketlink": "http://tickets.example.com",
    "artwork": "http://example.com/artwork.jpg"
  }
}
```

### 2. Categories

#### GET /categories/all
- **Description**: Retrieves all categories.
- **Example Request**:
```
curl https://ode.fm/api/v1/categories/all/?key=your_api_key
```
- **Response**:
```
{
  "categories": [
    {
      "categoryid": 1,
      "label": "Music"
    },
    {
      "categoryid": 2,
      "label": "Art"
    }
  ]
}
```

#### GET /categories/[categoryid]
- **Description**: Retrieves a single category by ID.
- **Example Request**:
```
curl https://ode.fm/api/v1/categories/1/?key=your_api_key
```
- **Response**:
```
{
  "category": {
    "categoryid": 1,
    "label": "Music"
  }
}
```

### 3. Locations

#### GET /locations/all
- **Description**: Retrieves all locations.
- **Example Request**:
```
curl https://ode.fm/api/v1/locations/all/?key=your_api_key
```
- **Response**:
```
{
  "locations": [
    {
      "locationid": 1,
      "regionid": "1",
      "label": "Downtown Venue",
      "description": "A popular downtown venue.",
      "address": "123 Main St, City, Country",
      "embed": "<iframe>Map embed code</iframe>"
    }
  ]
}
```

#### GET /locations/[locationid]
- **Description**: Retrieves a single location by ID.
- **Example Request**:
```
curl https://ode.fm/api/v1/locations/1/?key=your_api_key
```
- **Response**:
```
{
  "location": {
    "locationid": 1,
    "regionid": "1",
    "label": "Downtown Venue",
    "description": "A popular downtown venue.",
    "address": "123 Main St, City, Country",
    "embed": "<iframe>Map embed code</iframe>"
  }
}
```

### 4. Tags

#### GET /tags/all
- **Description**: Retrieves all tags.
- **Example Request**:
```
curl https://ode.fm/api/v1/tags/all/?key=your_api_key
```
- **Response**:
```
{
  "tags": [
    {
      "tagid": 1,
      "tagname": "Music"
    },
    {
      "tagid": 2,
      "tagname": "Festival"
    }
  ]
}
```

#### GET /tags/[tagidnumber]
- **Description**: Retrieves a single tag by ID.
- **Example Request**:
```
curl https://ode.fm/api/v1/tags/1/?key=your_api_key
```
- **Response**:
```
{
  "tag": {
    "tagid": 1,
    "tagname": "Music"
  }
}
```

### 5. Organizers

#### GET /organizers/all
- **Description**: Retrieves all organizers.
- **Example Request**:
```
curl https://ode.fm/api/v1/organizers/all/?key=your_api_key
```
- **Response**:
```
{
  "organizers": [
    {
      "organizerid": 102,
      "label": "Seattle Bach Festival",
      "regionid": "1",
      "website": "https://seattlebachfestival.org",
      "instagram": "seattlebachfestival",
      "profilepic": "https://r2-obj-storage.ode.fm/pfpimg/450782001_1203926190762888_6489491746113726907_n.jpg",
      "description": "Founded in 2024 by renowned baroque violinist Tekla Cunningham, The Seattle Bach Festival serves the Seattle area with great performances of the masterworks of JS Bach and pearls of the Baroque. From large scale works like Oratorios, Cantatas and Passions to the chamber music and solo works, we offer you a portal into a world of beauty, passion, joy, learning and community.\n\nOur mission is to inspire with performances of masterworks of Bach and pearls of the Baroque that move and uplift the spirits, nourish hearts, open minds and convene community.\n\nThe Seattle Bach Festival values a culture that invites you to feel welcomed, seen and heard. We welcome new listeners to our community through outreach events, dedication to our high-quality digital offerings, and educational programs that engage and inspire.
  }
  ]
}
```

#### GET /organizers/[organizerid]
- **Description**: Retrieves a single organizer by ID.
- **Example Request**:
```
curl https://ode.fm/api/v1/organizers/102/?key=your_api_key
```
- **Response**:
```
{
  "organizer": {
    "organizerid": 102,
    "label": "Seattle Bach Festival",
    "regionid": "1",
    "website": "https://seattlebachfestival.org",
    "instagram": "seattlebachfestival",
    "profilepic": "https://r2-obj-storage.ode.fm/pfpimg/450782001_1203926190762888_6489491746113726907_n.jpg",
    "description": "Founded in 2024 by renowned baroque violinist Tekla Cunningham, The Seattle Bach Festival serves the Seattle area with great performances of the masterworks of JS Bach and pearls of the Baroque. From large scale works like Oratorios, Cantatas and Passions to the chamber music and solo works, we offer you a portal into a world of beauty, passion, joy, learning and community.\n\nOur mission is to inspire with performances of masterworks of Bach and pearls of the Baroque that move and uplift the spirits, nourish hearts, open minds and convene community.\n\nThe Seattle Bach Festival values a culture that invites you to feel welcomed, seen and heard. We welcome new listeners to our community through outreach events, dedication to our high-quality digital offerings, and educational programs that engage and inspire.
  }
}
