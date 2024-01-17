# Airplay
 
Available since version: 2.0.0b1

Music Assistant has support for Airplay based devices. This includes Apple devices such as the Homepod but also a very wide range of 3rd party devices such as receivers and smart speakers. Due to the fact that Airplay uses lossless, timestamped streaming it is a very interesting protocol for lossless multi room streaming.

The Airplay provider within Music Assistant is based around the [fantastic work of Philippe44](https://github.com/philippe44/LMS-Raop), who created a bridge between slimproto and Airplay. Due to that fact, using Airplay in Music Assistant also requires the slimproto provider. Added benefit is that you can combine slimproto based devices (such as squeezelite, picoreplayer and original squeezebox hardware) with Airplay devices and play audio in sync.

## Features

- Airplay devices are auto detected in Music Assistant, plug and play.
- Airplay devices will play in sync.
- It is possible to sync Airplay devices with slimproto based devices too.
- Audio quality is lossless 44.1/16bits PCM and optionally compressed as (lossless) ALAC
- Any physical control buttons on the device should be  supported as long as flow mode is not enabled. 

## Known issues / notes

- Music Assistant implements RAOP (airplay 1) only, Airplay 2 devices should be backwards compatible by default.
- If you are using Shairport then ensure you have disabled Airplay V2.
- To enable playback to a Macbook, you need to enable access to "everyone on the same network" in the Airplay settings of the Macbook.
- Because Apple TV's require authentication, they are not supported yet (but will be in the future if there's any demand).

## Troubleshooting/tips

- Some devices (such as Kodi or some 3rd party airplay receivers) require encryption. You can enable encryption in the player settings.
- In settings you can disable any devices you do not use.
- If you find your player is going unavailable when still powered on then it may not be sending its keep alive message. A timeout can be configured for each player. Some users have reported they have needed to set it as long as one hour.