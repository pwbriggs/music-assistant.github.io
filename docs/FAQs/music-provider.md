# Music Provider Summary

## General Notes
* You have to add providers in order to access your music even if the media is visible to HA. 
* If you remove a provider a cleanup of the database will be done but it takes a little time to complete. If you restart MA or the provider before the cleanup completes the task will be terminated and will not restart.
* For local music providers all artists/albums/tracks/playlists are imported into the MA library
* For streaming providers ONLY the SPECIFIC artists/albums/tracks/playlists that are in the streaming providers library (or favourites or however it is termed in the provider) will be imported in the MA library. This means, for example, if you have an artist in the providers library but none of their albums then all you will see in the MA library is the artist with NO associated albums or tracks. You have to subsequently add albums or tracks to the MA library if you want to see them in the MA LIBRARY. Note you can toggle the library / streaming provider option to see all that is available in the streaming provider.

![image](https://github.com/music-assistant/hass-music-assistant/assets/19848947/eac76ff8-8789-4c6f-9c7d-59b0a18f9952)

## How do I access my local music / How do I tag my local music

See [here for info on SMB / CIFS shares](../music-providers/filesystem-provider.md)

## How do I use YouTube Music

See [here for YouTube Music](../music-providers/youtube-music-provider.md)

## How do I use Qobuz

See [here for Qobuz](../music-providers/qobuz-provider.md)

## How do I use Spotify

See [here for Spotify](../music-providers/spotify-provider.md)

## How do I use SoundCloud

See [here for SoundCloud](../music-providers/soundcloud-provider.md)

## How do I use Plex

Please be advised this provider is currently not maintained. Issues may take a long time be resolved. Consider sharing your music directly with MA instead

See [here for outdated Plex info](https://github.com/orgs/music-assistant/discussions/1168)

## How do I use Tidal

See [here for Tidal](../music-providers/tidal-provider.md)

## How do I use Radio Browser

See [here for Radio Browser](../music-providers/radio-browser-provider.md)

## How do I use Deezer

See [here for Deezer](../music-providers/deezer-provider.md)

## How do I use TuneIn

See [here for TuneIn](../music-providers/tunein-provider.md)