# DLNA/UPnP ![Preview image](../assets/icons/dlna-icon.svg){ width=70 align=right }

Music Assistant has support for uPnP/DLNA based devices. This is a (somewhat) universal standard for streaming audio to supported devices. Due to the very inconsistent implementation of this protocol by manufacturers, some players will work great and others will simply not work at all or need workarounds. Other than that, if you have a device that works, you can enjoy fast local control, lossless audio support and in many cases metadata of your playing media.

## Features

- DLNA devices are auto detected in Music Assistant

## Known Issues / Notes

- Some devices need special workarounds to enable playback. If playback is not working, look at the Music Assistant logs for clues and report an issue with these logs provided. 
- If your device is not found then try turning on the option "allow network scan for discovery"
- DLNA speakers do not support crossfading of audio. If you want crossfade and/or full gapless support, enable [flow mode](../faq/normalization.md/#track-queueing) in the player's advanced settings. Enabling flow mode may solve playback issues however it might come with the side effect of disabling actual physical buttons and/or display of metadata on the device itself.
- It is not possible to group/sync DLNA players together.
- Although Sonos devices are strictly also based on DLNA, they created their own extra layer on top of that such as crossfade support and many other goodies. It is therefore advised to use the Sonos Player provider with Music Assistant instead of the DLNA provider. MA disables any discovered Sonos DLNA devices by default.
