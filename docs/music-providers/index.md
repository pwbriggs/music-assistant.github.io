# Music Providers

<figure markdown>
  ![Apple Music](../assets/icons/apple-music.svg){ width=70 } ![MA](../assets/icon.png){ width=70 } ![Deezer](../assets/icons/deezer-icon.svg){ width=70 } ![Filesystem](../assets/icons/localfiles-icon.png){ width=70 } ![Jellyfin](../assets/icons/jellyfin-logo.svg){ width=70 } ![Preview image](../assets/icons/plex-icon.svg){ width=70 } ![Qobuz](../assets/icons/qobuz-icon.svg){ width=70 } ![Radio Browser](../assets/icons/radiobrowser_icon.png){ width=70 } ![Soundcloud](../assets/icons/soundcloud-icon.svg){ width=70 } ![Spotify](../assets/icons/spotify-icon.svg){ width=70 } ![Subsonic](../assets/icons/subsonic_icon.png){ width=70 } ![Tidal](../assets/icons/tidal-icon.svg){ width=70 } ![TuneIn](../assets/icons/tunein-icon.svg){ width=70 } ![YouTube Music](../assets/icons/ytm-icon.svg){ width=70 }
</figure>

For specific music provider information refer to the relevant section.

General Notes:

- You have to add providers in order to access your music even if the media is visible to HA.
- If you remove a provider a cleanup of the database will be done but it takes a little time to complete. If you still see entries from a deleted provider after some time, then try a MA restart to retrigger the cleanup process.
- Music providers are added by navigating to MA Settings and then clicking on ADD MUSIC PROVIDER at the top of the page

!!! tip "Note" 
    If a problem occurs the automatic linking process may need to be initiated again. If what appears to be identical albums or tracks are seen then navigate to the album or track and using the ⋮ menu in the banner at the top of the view select "Refresh Item". This will trigger the linking process and should result in the same albums and tracks being collapsed together. Submit an issue report if this is required so that it can be investigated.

![image](../assets/screenshots/add-music-provider.png)
