# Deezer Provider

Music Assistant has full support for [Deezer](https://www.deezer.com/) as Music Provider added in version 2.0.0 beta 30, contributed and maintained by @micha91 and @arctixdev.

> [!NOTE]
> - Because of Deezer's TOS we only support HiFi/Premium/Family accounts.
> - It is normal that syncing all your items from Deezer takes some time.

### Supported features
- Support for "library" Artist, Albums, Tracks and Playlists.
- Items in your Deezer library will be marked as "Favorites" too in Music Assistant.
- Marking an item as "Favorite" from the Music Assistant interface will also mark it as favorite in Deezer.
- Playback of Deezer content to all players supported by Music Assistant in FLAC HiFi.
- Searching from the Music Assistant interface support Artists, Albums, Tracks and Playlists.
- Full Artist, Album, Track and Playlist metadata.
- Playlist creation + adding and removing tracks from playlists.
- Easy oAuth login
- Logging played tracks in Deezer
- Radio mode (A bit like Deezer flow)

### About logging in:
Logging in should be as simple as pressing the `Authenticate` button when adding the provider in the Music Assistant interface.

**If this does not work make sure you:**
- Are on the same network as Music Assistant
- Can access Music Assistant using its IP address
- Have a Hifi/Premium/Family account
- Are on the latest Music Assistant version
- Try different browsers

### Not yet supported, but will be added later:
- Podcasts support ([see this feature request](https://github.com/music-assistant/hass-music-assistant/discussions/429))
- Fully featured recommendation/flow ([see this feature request](https://github.com/music-assistant/hass-music-assistant/discussions/535))

Big thanks to [Deezer-python](https://GitHub.com/browniebroke/deezer-python) made by @browniebroke. Without it, this would have taken alot longer to make possible.

If you have problems please report a bug here on Github or on the [Discord server](https://discord.gg/kaVm8hGpne) :slightly_smiling_face: