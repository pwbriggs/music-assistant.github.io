# DLNA/UPnP ![Preview image](../assets/icons/dlna-icon.svg){ width=70 align=right }

Music Assistant has support for uPNP/DLNA based devices. This is a (somewhat) universal standard for streaming audio to supported devices. Due to the very inconsistent implementation of this protocol by manufacturers, some players will work great and others will simply not work at all or need workarounds. Other than that, if you have a device that works, you can enjoy fast local control, lossless audio support and in many cases metadata of your playing media.

## Features

- DLNA devices are auto detected in Music Assistant
- In settings you can disable any devices you do not use.
- DLNA speakers do not support crossfading of audio. If you want crossfades and/or full gapless support, enable the "flow mode" in the player's advanced settings.
- Enabling flow mode comes at the cost of loosing metadata on the player itself, unless your player supports "icy metadata".
- It is not possible to group/sync DLNA players together.
- Although Sonos devices are strictly also based on DLNA, they created their own extra layer on top of that such as corssfade support or many other goodies. It is therefore advised to use the Sonos Player provider with Music Assistant instead of the DLNA provider. We disable any discovered Sonos devices by default in the DLNA provider.

## Troubleshooting/tips

Some devices need special workarounds to enable playback. If playback is not working, look at the Music Assistant logs for clues and report an issue with these logs provided. 

Enabling flow mode may solve issues relating to the playback stopping randomly 

If you device is not found then try turning on the option "allow network scan for discovery" 
