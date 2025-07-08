# OneField API Reference (v1.0)

Welcome to the OneField API! This RESTful API allows developers to integrate drone fleet management, mission planning, and real-time control into their own applications.

Base URL: https://api.onefield.io/v1

🔐 Authentication
All requests must include an API key in the header:

```json
Authorization: Bearer YOUR_API_KEY
```

🚁 Drones
GET /drones
Retrieve a list of all connected drones.

Response:

```json
[
  {
    "id": "drone_001",
    "model": "DJI Mavic 3",
    "status": "idle",
    "battery": 87,
    "location": {
      "lat": 47.6101,
      "lng": -122.2015
    }
  }
]
````

POST /drones
Register a new drone to your fleet.

Body:
```json
{
  "serial_number": "DJI123456789",
  "nickname": "Field Scout 1"
}
```

🗺️ Missions
POST /missions
Create a new flight mission.

Body:

```json
{
  "name": "Crop Survey July",
  "drone_id": "drone_001",
  "waypoints": [
    {"lat": 47.6101, "lng": -122.2015, "alt": 50},
    {"lat": 47.6110, "lng": -122.2020, "alt": 50}
  ],
  "actions": ["take_photo", "record_video"]
}
````

GET /missions/:id
Get details of a specific mission.

📡 Live Control
POST /control/override
Take manual control of a drone.

Body:

```json
{
  "drone_id": "drone_001",
  "command": "return_to_home"
}
```

🔄 OTA Updates
POST /drones/:id/update
Push a firmware update to a drone.

Body:

```json
{
  "version": "v2.3.1",
  "force_restart": true
}

```

📊 Telemetry
GET /drones/:id/telemetry
Retrieve real-time telemetry data.

Response:

```json
{
  "altitude": 52.3,
  "speed": 12.5,
  "battery": 76,
  "gps": {
    "lat": 47.6105,
    "lng": -122.2021
  }
}
``` 
