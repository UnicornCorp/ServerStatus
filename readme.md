# Server Status
Scans a list of servers checking checking which are currently online.
This bot will send a chat notification when the status of a server changes (goes on or offline).

- **TCP** - should work with all servers
- **UDP** - [Source RCON Protocol](https://developer.valvesoftware.com/wiki/Source_RCON_Protocol) is supported

## Configuration
- Download the latest release [here](https://github.com/mgerb/ServerStatus/releases)
- Add your bot token as well as other configurations to config.json
- Execute the OS specific binary!

### Mentioning Roles/Users
- you must first get your role/user id (see below of obtaining ID's)
- for user `<@userid>`
- for role `<@&roleid>`

### Polling Interval
The polling interval is how often the bot will try to ping the servers.
A good interval is 10 seconds, but this may need some adjustment if
it happens to be spamming notifications.

- time in seconds
- configurable in `config.json`

## With Docker

```
docker run -it -v /path/to/your/config.json:/server-status/config.json:ro mgerb/server-status
```

### Docker Compose

```
version: "2"

services:
  server-status:
    image: mgerb/server-status:latest
    volumes:
    - /path/to/your/config.json:/server-status/config.json
```

## Usage
To get the current status of your servers simply type `!ServerStatus` in chat.

![Server Status](https://i.imgur.com/ZzQSBJp.png)

## Compiling from source
- Make sure Go and Make are installed
- make all

### How to get the bot token
https://github.com/reactiflux/discord-irc/wiki/Creating-a-discord-bot-&-getting-a-token

### How to get your room ID
To get IDs, turn on Developer Mode in the Discord client (User Settings -> Appearance) and then right-click your name/icon anywhere in the client and select Copy ID.

<img src="https://camo.githubusercontent.com/9f759ec8b45a6e9dd2242bc64c82897c74f84a25/687474703a2f2f692e696d6775722e636f6d2f47684b70424d512e676966"/>

