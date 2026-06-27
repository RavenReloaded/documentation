# Raven Backend Server

Backend server for Minecraft mod Raven Reloaded, providing API for synchronizing waypoints between players.

## Features

- **Waypoint synchronization** - Real-time sharing of waypoints between players
- **REST API** - Simple HTTP endpoints for waypoint management
- **Automatic cleanup** - Waypoints are automatically deleted after 5 minutes of inactivity
- **Rate limiting** - Limit of 100 requests per minute per IP address
- **Caching** - 1 second cache for GET requests
- **Monitoring** - Server status and statistics tracking

## Requirements

- Node.js (version 14 or higher)
- npm (Node Package Manager)

## Installation

1. Clone this repository
2. Navigate to the `backend-server` folder
3. Install dependencies:
```bash
npm install
```

## Running the Server

### Development environment
```bash
npm run dev
```

### Production environment
```bash
npm start
```

The server runs on port 3003. You can change the port by setting the `PORT` environment variable.

## Configuration in Minecraft mod

### Setting in config.json
1. Launch Minecraft with the Raven mod installed
2. In the `keystrokes/config.json` file, set your backend server URL:
```json
{
  "backendUrl": "http://localhost:3003"
}
```

### Setting via in-game command
You can also set the backend URL directly in the game using the command:
```
.backendurl <url>
```

## API Endpoints

### GET /waypoints
Retrieves a list of all waypoints

**Response:**
```json
[
  {
    "id": "playerName",
    "playerName": "string",
    "x": number,
    "y": number,
    "z": number,
    "dimension": "string",
    "name": "string",
    "timestamp": number
  }
]
```

### POST /waypoints
Creates a new waypoint or updates an existing one

**Request body:**
```json
{
  "playerName": "string",
  "x": number,
  "y": number,
  "z": number,
  "dimension": "string",
  "name": "string"
}
```

### DELETE /waypoints/:playerName
Deletes a specific player's waypoint

### GET /health
Checks server status

**Response:**
```json
{
  "status": "ok",
  "uptime": number,
  "waypointsCount": number,
  "connectedClients": number,
  "memoryUsage": object
}
```

## Sharing with friends using ngrok

To share the server with friends, you can use ngrok, which creates a public tunnel to your local server.

### Installing ngrok

1. Download ngrok from [ngrok.com](https://ngrok.com)
2. Register and get an authtoken
3. Set the authtoken:
```bash
ngrok config add-authtoken YOUR_AUTHTOKEN
```

### Starting ngrok tunnel

1. Start the backend server:
```bash
npm start
```

2. In a new terminal, start the ngrok tunnel:
```bash
ngrok http 3003
```

3. Ngrok will display a public URL (e.g., `https://abc123.ngrok.io`)

### Configuration for friends

Friends must set in the `keystrokes/config.json` file:
```json
{
  "backendUrl": "https://abc123.ngrok.io"
}
```

### Security notes

- Ngrok URL changes with each restart (in free version)
- For permanent sharing, consider paid ngrok version or your own server
- Public tunnel is accessible to anyone with the URL

## Monitoring and logs

The server automatically logs:
- New client connections
- Waypoint creation/updates
- Waypoint deletions
- Automatic cleanup of expired waypoints
- Errors and rate limit events

## Production deployment

1. Set `NODE_ENV=production`
2. Use reverse proxy (nginx) for SSL termination
3. Configure firewall to restrict access
4. Monitor logs to detect issues

## Troubleshooting

### Server won't start
- Check if port 3003 is free
- Verify you have the correct Node.js version

### Waypoints not synchronizing
- Check URL in config.json
- Verify server is running and accessible
- Check server logs

### Rate limit errors
- Wait 1 minute before next request
- Consider increasing the limit in server code

## Support
For issues and questions, you can contact moderators on Discord: https://discord.com/invite/UH7HQpWrGf

