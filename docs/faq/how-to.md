# Use Assist and AI to Play my Music?

See [here](../integration/installation.md)

# Use volume normalization? How does it work?

The setting in MA is the target level for the volume normalization. MA does not compress the dynamic range (because that is bad for quality) but just adjusts the gain of the entire track based on its overall loudness as measured by the EBU R128 standard. A greater negative value will typically make the track sound less loud but leaves a lot of headroom. However, for each individual track the gain could rise or fall to ensure that the overall loudness of all tracks played is at the selected level. We recommend to use a value between -23 and -17 LUFS (and -17 is the recommended starting point). **Do not** set it too high (close to zero) because that can make your music sound distorted due to clipping.

More details [here](normalization.md)

# Have my music continue if I change rooms

Start streaming to a group that includes all the rooms you will move between. Power off or mute all the rooms except the one you are in. When you move rooms just power (or mute) on and off the respective rooms. Depending on the complexity of your setup you may need to use nested groups of speakers.

You can read, ask or contribute [on this topic](https://github.com/orgs/music-assistant/discussions/702)

# Shuffle Spotify/playlist/Youtube etc

You don't shuffle the music providers you enable shuffle on the queue for the player and then whatever gets added to the queue gets shuffled. You enable shuffle on the queue from within MA by selecting the Shuffle Icon in the Player frontend or you can select the QUEUE at the bottom, then the context menu Top Right then SETTINGS then SHUFFLE ON or you can do it with yaml as follows:
``` yaml
service: media_player.shuffle_set
target:
  entity_id: media_player.mass_bath
data:
  shuffle: true
```

# Add items to the queue via a script or automation

``` yaml
service: media_player.play_media
target:
  entity_id: media_player.mass_player_entity_goes_here
data:
  media_content_id: NameOfTheAlbumArtistOrPlaylistHere
  media_content_type: music
```

See also [mass.play_media service call](./massplaymedia.md)

# Start a playlist with a script

Use the `media_player.play_media` service call shown above or `mass.play_media` service as described here.

# Start a radio stream with an automation

Use the `mass.play_media` service call and set the `media_id` as the station name.

# Clear the queue with a script or automation

Use the HA service call of `media_player.clear_playlist` or the new `mass.play_media` service call and select the appropriate enqueue option if wanting to clear the queue and play something else.

# Add radio stations to MA

If you use the [TuneIn provider](../music-providers/tunein.md) then stations that are favourited in your account will appear.

If you use the [RadioBrowser provider](../music-providers/radio-browser.md) then BROWSE the provider and select ADD TO LIBRARY for the station desired.

Direct entry of stations can be done by navigating to the radio stations page and selecting the menu top right and ADD ITEM FROM URL
This will also work for locally hosted streams such as from Icecast. 

# Create playlists or use M3U files

You can create playlists from the MA UI. Adding items can also be done from the UI.

If wanting to create playlists manually acceptable formats are:
```
(file in same folder as playlist):
05 Blue Christmas.flac

and this (file is in subfolder relative to playlist file):
Elvis Presley/Blue Christmas/05 Blue Christmas.flac

and this (file has absolute path):
/Users/marcel/media/music/b05 Blue Christmas.flac

and this (full uri):
spotify://track/12345
or
filesystem_smb://track/blah
```

Relative paths to the playlist (e.g.` ../Mariah Carey/Merry Christmas/02 All I Want for Christmas Is You.flac` ) should also work.

# Go to next/previous radio station via a script

Create a playlist with multiple radio stations and start playing it. Now you can use next and previous to switch between the stations

# Stop the music after a period of time aka Sleep Timer

``` yaml
sequence:
  - wait_for_trigger:
      - platform: state
        entity_id:
          - media_player.mass_all_rooms
        attribute: media_title
    continue_on_timeout: false
  - service: media_player.turn_off
    data: {}
    target:
      entity_id:
        - media_player.mass_all_rooms
mode: single
alias: Stop after current track
```

Thanks to [AAsikki](https://github.com/Aasikki) who showed us [here](https://github.com/orgs/music-assistant/discussions/830#discussioncomment-3355921)

# Use MA with Mopidy

See here https://github.com/music-assistant/hass-music-assistant/discussions/439

# Use the MA service call `mass.play_media`

See [here](massplaymedia.md)

# Use the MA service call `mass.search`

See [here](masssearch.md)

# Get the URI?

For playlists, artists, albums and radio you can simply use the name.

For tracks you can use the name but that may result in ambiguous responses so you can limit by artist name by using `Billy Joel - A Matter of Trust` if that is still ambiguous then the service call has additional options which you can use to further restrict the search , for example:

``` yaml
data:
  media_type: track
  media_id: Running on Ice
  artist: Billy Joel
  album: The Bridge
```

Similarly, if the album name is ambiguous you can specify the artist name first (`Queen - Greatest Hits`)

# Run MA when I have SSL setup on my internal network?

Trying to run MA with SSL is not recommended. Having said that, whilst you can not run the stream service behind SSL you can configure the frontend entirely to your requirements. The default is that the frontend is protected by Ingress in HAOS. For those using docker, it is possible to host it on a desired port and then run a (Ingress) reverse proxy. No support will be provided for these setups, we recommend you use HAOS.

# Get the MA icon in the HA sidebar?

If you are running the addon within the HA host go to SETTINGS>>ADDONS>>MUSIC ASSISTANT and select "Show in sidebar".

If you are using docker then you can use an [iframe panel](https://www.home-assistant.io/integrations/panel_iframe/)

# Add a rotary encoder with push button to a piCorePlayer

See [here](https://github.com/orgs/music-assistant/discussions/1123#discussioncomment-7945369)
