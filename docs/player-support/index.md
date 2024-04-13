# Player Providers

For specific player provider information refer to the relevant section in this document. Most players are enabled by default and will be automatically discovered by Music Assistant.

If a device supports multiple protocols then multiple players for the device will be seen. In the player provider settings you can disable or hide any players you do not use.

![Preview image](../assets/screenshots/player-disable.png){ width = 600 } 

## Audio Quality

Audio quality is the principal reason why native MA players are developed. These players provide the highest quality playback experience. HA players will work and may work well but they may also have been written with a basic objective such as enabling text to speech. Therefore, if there is a MA player available and a HA integration then you should always choose the MA player. 

96kHz / 24 bits and above is considered High Resolution (Hi Res)

- Airplay supports lossless (44.1kHz / 16 bits which is cd quality) but not Hi Res.
- Sonos supports lossless (44.1kHz / 16 bits which is cd quality) on series 1 models and 48KHz / 24 bits on series 2.
- Chromecast supports Hi Res up to 96KHz / 24 bits (except the video dongles which do 48KHz / 24 bits)
- Slimproto supports Hi Res up to 384kHz / 24 bits
- DLNA supports Hi Res up to 192kHz / 24 bits
- Snapcast supports up to 48kHz / 16 bits
