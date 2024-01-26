### MA play_media Service Call

This service calls allows you to finely select the media to play. Create your service call or automation via the HA GUI or YAML

You can use a name together with the media type

![image](https://github.com/music-assistant/hass-music-assistant/assets/19848947/b142459a-4e21-4332-868e-a8c8a3bed9ea)

Or just a URI

![image](https://github.com/music-assistant/hass-music-assistant/assets/19848947/38e9815b-90f9-4a77-9bc2-6d80ba56bb7b)

Or the library id together with the media id

![image](https://github.com/music-assistant/hass-music-assistant/assets/19848947/32f4c0b2-6c60-4cde-bb68-c56c5753b608)

Or a track defined with the artist name, media type is recommended but optional

![image](https://github.com/music-assistant/hass-music-assistant/assets/19848947/cc77394b-21bf-4963-80e8-6b2349ed9979)

You can also have a list of items

![image](https://github.com/music-assistant/hass-music-assistant/assets/19848947/84a5f42f-b110-4a1c-8339-2bab1c112a0a)

Or a list of uris which can even be from different music providers

![image](https://github.com/music-assistant/hass-music-assistant/assets/19848947/d084bc6d-efaf-4d2f-bb77-0b3110797cad)

!!! note The regular `media_player.play_media` service call also accepts all of the above but it cannot take multiple items

There are additional options as well. These will appear when an entity that supports them is selected.

![image](https://github.com/music-assistant/hass-music-assistant/assets/19848947/010cca85-9e2c-40e8-b02e-87a1d17cce7c)
