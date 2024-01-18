## Installing the Server

Music Assistant can be operated as a complete standalone product but it is actually tailored to use side by side with Home Assistant, it is meant with automation in mind, hence our recommended installation method is to run the server as Home assistant Add-on which will be automatically installed when you add the Home Assistant Integration.

MA requires a 64bit Operating System and a minimum of 2GB of RAM on the physical device or the container (physical devices are recommended to have 4GB+ if they are running anything else)

### Primary installation method: Home Assistant Integration Installation

Go to the [Home Assistant Integration](https://music-assistant.github.io/integration/) page and follow the instructions there which will install the integration and the server.

### Secondary installation method: Home Assistant Add-on Manual Installation

If you dont need the HA Integration but want to run the Music Assistant Server then install the Music Assistant Add-on manually:

1. Add the Music Assistant repository to your Home Assistant instance.
2. Install the Music Assistant add-on.

[![Open your Home Assistant instance and show the add add-on repository dialog with a specific repository URL pre-filled.](https://my.home-assistant.io/badges/supervisor_add_addon_repository.svg)](https://my.home-assistant.io/redirect/supervisor_add_addon_repository/?repository_url=https%3A%2F%2Fgithub.com%2Fmusic-assistant%2Fhome-assistant-addon)


### Tertiary installation method: Docker image

An alternative way to run the Music Assistant server is by running the docker image:

```
docker run --network host --privileged -v <dir>:/data ghcr.io/music-assistant/server
```

You must run the docker container with host network mode. The data volume is `/data` - replace `<dir>` with a writable directory to ensure the data volume persists between updates.
If you want access to your local music files from within MA, make sure to also mount that, e.g. /media.
Note that accessing remote (SMB) shares can be done from within MA itself using the SMB File provider (but requires the privileged flag).

____________

### Server Notes

- Because the server heavily relies on multicast techniques like mDNS and uPnP to discover players in your network it MUST be run in the same Layer 2 network as your player devices.

- The server itself hosts a very simple webserver to stream audio to devices. This webinterface must be accessible via HTTP (no HTTPS) by IP-address from local players. See the server's logging at startup to see if the server has correctly auto-detected the local IP.

- The server itself hosts a websocket API and a JSON RPC API which is more or less compatible with LMS. The Music Assistant fronted communicates with the server using the websockets API.

- The webinterface of the server can be reached on tcp port 8095 if enabled in the settings. By default on HAOS based installations the webserver is internal only and not exposed to the outside world. It is protected by HA authentication using the Ingress feature of Home Assistant (hence you also get the sidepanel for free)
  
- You can access the frontend over https by following these steps:
  (1) Expose the webserver via MA settings --> Core --> webserver
  (2) To access the frontend behind a reverse proxy you will have to configure the reverse proxy to point at the 8095 port and expose it to whatever is desired (and add an ssl certificate). How that works differs for each implemention. 

!!! tip You can also keep the server more secure by NOT exposing the webserver and let the addon talk directly to the webserver on the internal docker network. In that case address the internal dns name of the addon, e.g. <http://d5369777-music-assistant-beta:8095>

## Usage and Notes

- If you are running Music Assistant in docker, you need to access the webinterface at http://youripaddress:8095. When running the Home Assistant add-on, you can access the webinterface from the add-on (a shortcut can be added to the sidebar) which is more secure than via the port.
- Music from your music sources will be automatically loaded into the Music Assistant library. If you have multiple sources, they will be merged as one library.
- In this first implementation there's only support for "Library items", so your favourited artists, albums and playlists. In a later release we'll provide options to browse the recommendations of the various streaming providers.
- Items on disk are not favourited by default. You can see all items if you deselect the "in library" filter (the heart) and decide for yourself what you want in your favourites.
- Note that at the first startup it can take a while before data is available (first sync), the Music Assistant UI will notify you about tasks that are in progress.
- Music sources are synced at addon (re)start and every 3 hours.
- If a song is available on multiple providers (e.g. Spotify and a flac file on disk), the file/stream with the highest quality is always preferred when starting a stream.
- Music Assistant uses a custom stream port (TCP 8096 by default) to stream audio to players. Players must be able to reach the Home Assistant instance and this port. If you're running one of the recommended Home Assistant installation methods, this is all handled for you, otherwise you will have to make sure you're running HA in HOST network mode. Note: If the default port 8096 is occupied, the next port will be tried, and so on.
- See the [GitHub discussion](https://github.com/orgs/music-assistant/discussions/710#discussioncomment-7987528) for more detailed information

## Support and Documentation

Because this project originated out of a Home Assistant integration, we maintain all our documentatation and enduser support in a separate reposity. Raise issues and discuss ideas here:
https://github.com/music-assistant/hass-music-assistant

You can also seek help on [Discord](https://discord.gg/kaVm8hGpne)


[repository-badge]: https://img.shields.io/badge/Add%20repository%20to%20my-Home%20Assistant-41BDF5?logo=home-assistant&style=for-the-badge
[repository-url]: https://my.home-assistant.io/redirect/supervisor_add_addon_repository/?repository_url=https%3A%2F%2Fgithub.com%2Fmusic-assistant%2Fhome-assistant-addon
