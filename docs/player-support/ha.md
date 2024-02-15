# Home Assistant ![Preview image](../assets/icons/ha-logo.png){ width=70 align=right }

Music Assistant has support for playing to media player entities in Home Assistant.

## Features

- All media player entities that are available in HA, for which there is no dedicated MA provider, will be available in MA

## Known Issues / Notes

- This player provider is not enabled by default and must be added via MA settings however before it is available you must setup the Home Assistant Plug-in Provider
- In the provider settings, select which players you want to use
- You can only use players that support "play_media", other players will be filtered out
- MA players will be filtered out
- Synchronisation between this player type and any others is not possible
