# YouTube Music Provider ![Preview image](../assets/icons/ytm-icon.svg){ width=70 align=right }

Music Assistant has support for Youtube Music. Contributed by @MarvinSchenkel.

!!! danger "DISCLAIMER"
    Please note that Youtube does not offer an official API to retrieve data and streams. This means that everything is built on a best-effort basis. Unexpected behavior will occur whilst using this provider. For this reason if you have another streaming provider you may find it more convenient to use that instead of this one.

!!! note
    Free accounts are NOT supported.

## Features and Notes

There is no support for the disc and track number in album tracks listings. Currently, the disc number is always 0 and the track number is the order number in which the tracks were returned by Youtube Music. This should generally give the desired result, but could mess up multi-disc albums.

Whether music videos are selected for playback fully depends on what you are playing. If you have saved a specific album in your library, then that exact version will show up in MA and thus you will have the album version. However, if you start a radio on let's say a playlist, then Youtube Music decides which songs will be played in a 'dynamic radio' playlist which could include videos.

The highest available stream from Youtube Music will be selected for playback (similar to configuring 'high' in the web-app). This then gets re-encoded by MA to a (default) lossless FLAC (assuming you have this as the output codec (which it is by default)).

Uploaded Music should be able to be found when it is in a playlist. If it's just a single track being searched for then it may not be found, since often those uploaded songs don't have proper metadata. It will be hard to find them via the UI in MA.

## Installation Instructions
Music Assistant uses OAuth for Youtube Music, which means login is axcomplished just like is done on Gmail for example. To add the Youtube Music provider to MA:

- Navigate to 'Settings'
- Under Music Providers, click 'Add new', select 'Youtube Music' and click 'Authenticate with Youtube Music'
- A new window will open. Ignore the code and click 'Next'
- Login with your gmail account
- Optionally choose a brand account
- Click 'Allow'
- You can now manually close the tab to return to Music Assistant
- Click 'Save'
