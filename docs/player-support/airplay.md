# Airplay ![Preview image](../assets/icons/airplay-logo.png){ width=70 align=right }

Music Assistant has support for Airplay based devices. This includes Apple devices such as the Homepod but also a very wide range of 3rd party devices such as receivers and smart speakers. Due to the fact that Airplay uses lossless, timestamped streaming it is a very interesting protocol for lossless multi room playback.

## Features

- Airplay devices are auto detected in Music Assistant, plug and play
- Airplay devices will play in sync
- Audio quality is lossless 44.1/16bits PCM and optionally compressed as (lossless) ALAC
- Any physical control buttons on the device should be  supported as long as flow mode is not enabled
- The player settings include some basic equaliser settings
- The player settings allow configuration of stereo pairs of speakers

## Known Issues / Notes

- Music Assistant implements RAOP (airplay 1) only, Airplay 2 devices should be backwards compatible by default
- Whilst it is believed to have been fixed, issues have been reported when using Shairport and Airplay V2. If problems are encountered they try disabling Airplay V2
- To enable playback to a Macbook, you need to enable access to "everyone on the same network" in the Airplay settings of the Macbook
- Because Apple TV's require authentication, they are not supported yet (but will be in the future if there's any demand)
- Samsung seems to have implemented AirPlay 2 in a way that it isn't fully backwards compatible. Everything seems to work, changing volume, song info is shown, and you can control the Samsung device as expected, however there is no sound. Users of similar applications such as Roon and anything based on slimproto have the same problem. 
- Some devices (such as Kodi or some 3rd party airplay receivers) require encryption. You can enable encryption in the advanced player settings if there is no sound
- Also try compression on and off in the advanced player settimgs if there is no sound
- A device password can be set for those devices which require it in the advanced settimgs
- If you find your player is going unavailable when still powered on then it may not be sending its keep alive message. A timeout can be configured for each player. Some users have reported they have needed to set it as long as one hour
