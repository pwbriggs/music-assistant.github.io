# Deezer Provider ![Preview image](../assets/icons/deezer-icon.svg){ width=70 align=right }

Music Assistant has support for [Deezer](https://www.deezer.com/). Contributed and maintained by [arctixdev](https://github.com/arctixdev) and [micha91](https://github.com/micha91) 

!!! tip "Note"
    - Because of Deezer's TOS we only support HiFi/Premium/Family accounts.
    - It is normal that syncing all your items from Deezer takes some time.

## Features
- Searching from the Music Assistant interface supports Artists, Albums, Tracks and Playlists.
- Items in your Deezer Favourites will be imported into the MA Library and automatically marked as a "Favorite" in MA.
- If you add an item from Deezer to the MA library then nothing will happen in Deezer unless you also mark it as a favourite (at which time the item will be added to the Deezer favourites)
- Artist, Album, Track and Playlist metadata is fully supported.
- Playlist creation is possible as well as adding and removing tracks from existing playlists.
- Easy oAuth login
- Logging of played tracks in Deezer
- Radio mode (Similar to Deezer flow)

## Configuration
Login by pressing the `Authenticate` button when adding the provider in the Music Assistant interface.

**If this does not work ensure that you:**
- Are on the same network as Music Assistant
- Can access Music Assistant using its IP address
- Have a Hifi/Premium/Family account
- Are on the latest Music Assistant version
- Try different browsers

## Not yet supported
- Podcasts support ([see this feature request](https://github.com/music-assistant/hass-music-assistant/discussions/429))
- Fully featured recommendation/flow ([see this feature request](https://github.com/music-assistant/hass-music-assistant/discussions/535))

Big thanks to [Deezer-python](https://GitHub.com/browniebroke/deezer-python) made by [browniebroke]((https://github.com/browniebloke). Without it, this would have taken alot longer to make.
