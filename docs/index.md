# Music Assistant

![MA Banner](assets/MA_banner.png)

Music Assistant is a music library manager for your offline and online music sources which can easily stream your favourite music to a wide range of supported players and be combined with the power of Home Assistant!

## Features

- Supports multiple music sources through a provider implementation.
- Many popular streaming services are supported, as well as local files.
- Automatically matches music on different providers (track linking).
- Fetches metadata for extended artist information.
- Keeps track of the entire music library in a compact database
- Gapless, crossfade and volume normalization support for all players.
- Playback synchronisation is possibie for supported players
- Truly hassle free streaming of your favourite music to players, no advanced knowledge required.
- Rich User interface (Progressive Web App) powered by VueJS 3.

![Warning](assets/beta_warning.png)

## Architecture

Music Assistant consists of multiple building blocks:

- Music Assistant Server ([Installation Instructions](installation.md))
- Music Assistant Integration for Home Assistant ([Installation Instructions](integration/installation.md))

## Music Assistant Server

The Music Assistant server is a free, opensource Media library manager that connects to your streaming services and a wide range of connected speakers. The server is the beating heart, the core of Music Assistant and it keeps track of your music sources. It must run on an always-on device like a Raspberry Pi, a NAS or an Intel NUC or alike. The server can access multiple music providers and stream to multiple player types.

## Music Assistant Integration

Connects Home Assistant to your Music Assistant Server to allow control from your HA instance, allow you to automate your music and allow voice control!

## Preview

![Preview image](assets/screenshots/screen1.png){width=800 } 

??? note "Click to show more screenshots"

    ![Preview image](assets/screenshots/screen3.png){width=800 } 

    ![Preview image](assets/screenshots/screen2.png){width=800 } 


## The Team

![Marcel](assets/team/marcel.png){ width=100 }
![Jozef](assets/team/jozef.png){ width=100 }
![Jonathan](assets/team/jonathan.png){ width=100 }
![Gavin](assets/team/gavin.png){ width=100 }
![Marvin](assets/team/marvin.png){ width=100 }
![Santiago](assets/team/santiago.png){ width=100 }
![khers](assets/team/khers.png){ width=100 }
![Lokiberra](assets/team/lokiberra.png){ width=100 }

[repository-badge]: https://img.shields.io/badge/Add%20repository%20to%20my-Home%20Assistant-41BDF5?logo=home-assistant&style=for-the-badge
[repository-url]: https://my.home-assistant.io/redirect/supervisor_add_addon_repository/?repository_url=https%3A%2F%2Fgithub.com%2Fmusic-assistant%2Fhome-assistant-addon
