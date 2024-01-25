# Spotify Provider ![Preview image](../assets/icons/spotify-icon.svg){ width=70 align=right }

Music Assistant has full support for Spotify media listing and playback.

## Features

- Support for Artists, Albums, Tracks and Playlists.
- Items in your Spotify library will be added to the Library in Music Assistant.
- Adding an item from Spotify to the Music Assistant Library will also add it to "Your Library" in Spotify
- Multiple Spotify accounts can be added. All playlists from all accounts will be shown. If a playlist is selected for playback the source Spotify account will be used.

## Configuration
- In the configuration, you need to enter your Spotify username and password
- If you login to Spotify with 3rd party accounts (eg. Facebook) then you can set a device password to use by going [here](https://www.spotify.com/de-en/account/set-device-password/)
- You will receive an error of “Only premium accounts are supported” if you use incorrect login credentials so check the login details, try a different account or reset the password if you think that error message is incorrect.

## Known Issues / Notes

- Only Spotify PREMIUM accounts are supported (includes Duo and Family), free accounts will not work.

## Not yet supported

- Podcasts support ([see this feature request](https://github.com/music-assistant/hass-music-assistant/discussions/429))
- Recommendations ([see this feature request](https://github.com/music-assistant/hass-music-assistant/discussions/535))
