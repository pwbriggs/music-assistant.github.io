# Google Cast

Music Assistant has full support for Google Cast based devices. This includes Google's own hardware like the Google Nest speakers but also a wide range of other brands have "Chromecast builtin" support, like Harman Kardon, JBL, Canton and many others. 

## Features

- Cast speakers are auto detected in Music Assistant
- In settings you can disable any cast speakers you do not use.
- After re-enabling a disabled speaker, it can take a while before the speaker is rediscovered, speed up the process by restarting Music Assistant.
- Cast speakers support Hi res audio, up to 96khz, 24 bits
- Cast speakers do not support crossfading of audio. If you want crossfades and/or full gapless support, enable the "flow mode" in the player's advanced settings.
- Enabling flow mode comes at the cost of loosing metadata on the player itself.
- It is not possible to group/sync cast players from within the MA interface (simply because an api does not exist for that). As a possible workaround delays can be set in the Google Home app.
- When using Google Cast groups then perfect sync across players in that group is possible
- Music Assistant does support playing to predefined cast groups you can create in the Google Home app.
- Any physical control buttons on the device should be  supported as long as flow mode is not enabled. Voice control should also work.


## Known issues/notes

- At time of writing (2.0 beta) the group support is not yet fully working and volume controls are missing, [this will be fixed soon](https://github.com/orgs/music-assistant/projects/2/views/1?pane=issue&itemId=22583723).
- At time of writing (2.0 beta) there are some issues with stereo pairs, [this will be fixed soon
](https://github.com/orgs/music-assistant/projects/2/views/1?pane=issue&itemId=22559664)


## Troubleshooting/tips

My Chromecast speakers not auto detected or randomly unavailable
- Make sure that your Cast enabled speakers are on the same network/subnet as your Music Assistant server.
- Make sure that multicast traffic (more specific mDNS) can travel freely as that is used for the discovery of players.
