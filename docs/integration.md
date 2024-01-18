# Music Assistant Integration

[![latest version](https://img.shields.io/github/release/music-assistant/hass-music-assistant?display_name=tag&include_prereleases&label=latest%20version)](https://github.com/music-assistant/hass-music-assistant/releases)
[![discord](https://img.shields.io/discord/753947050995089438?label=Chat&logo=discord)](https://discord.gg/kaVm8hGpne)
[![hacs](https://img.shields.io/badge/HACS-Default-41BDF5?label=HACS)](https://github.com/hacs/integration)
[![sponsor](https://img.shields.io/github/sponsors/music-assistant?label=sponsors)](https://github.com/sponsors/music-assistant)

## Attention: Running Home Assistant 2023.3 or later?
Make sure to install at least the 2023.6.bx BETA version of the Music Assistant HA Integration. Older versions of the Integration are not compatible with recent Home Assistant versions. Music Assistant HA Integration version [2023.12.0](https://github.com/music-assistant/hass-music-assistant/releases/tag/2023.12.0) was released on Dec. 29 and should be used in the first instance. The subsequent beta versions introduce the voice control functionality.

## Installation of the Home Assistant Integration

- Make sure that you have the [Home Assistant Community Store](https://hacs.xyz/) installed.
- Within HACS, search for `Music Assistant` and click the entry in the search results.
- Click the big (blue) button at the bottom for `Download`.
- Click the button again and in the dialog make sure `Show beta versions` is selected if you want to use those versions.
- Download the desired version
- Restart Home Assistant.
- Go to Configuration -> Integrations and click the big `+` button.
- Look for Music Assistant and click to add it.
- If Music Assistant does not show, refresh your browser (cache).
- The Music Assistant integration is ready for use.

!!! note
    You need to set-up the players and music sources within Music Assistant itself.

!!! note 
    The HA integration will create new media_player entities for those player types which are supported natively by MA. To see the names of those players go to `settings > devices & services > integrations > music assistant`. It is these players that need to be targeted in your automations.

## OpenAI features

During [Chapter 5 of "Year of the Voice"](https://www.youtube.com/live/djEkgoS5dDQ?si=pt8-qYH3PTpsnOq9&t=3699), [JLo](https://blog.jlpouffier.fr/chatgpt-powered-music-search-engine-on-a-local-voice-assistant/) showed something he had been working on to use the OpenAI integration along with Music Assistant. We now have this feature baked in to the integration code directly, although some extra setup is still required.
- You need to be running the latest BETA of the HA Integration
- You need to create/add another OpenAI integration that is purely for Music Assistant.
- Add the prompt found [here](https://github.com/music-assistant/hass-music-assistant/blob/main/prompt/prompt.txt) to the configuration of the the OpenAI integration.
- Add a directory in your Home Assistant `config` dir name `custom_sentences/en`
- Add the file found [here](https://github.com/music-assistant/hass-music-assistant/blob/main/custom_sentences/en/play_media_on_media_player.yaml), to that dir.
- When setting up the Music Assistant integration, make sure that you select the correct Conversation Agent and also
allow the auto-exposure of Mass media players to Assist

![Preview image](assets/screenshots/screen6.png)

## I need help, I have feedback

- [issue tracker](https://github.com/music-assistant/hass-music-assistant/issues) to create bug reports, please include detailed info and logfiles. Please check if your issue has already been reported.
- [feature requests](https://github.com/music-assistant/hass-music-assistant/discussions/categories/feature-requests-and-ideas): Give your vote to an existing request, join the discussion or add a new request.
- [Q&A section](https://github.com/music-assistant/hass-music-assistant/discussions/categories/q-a-faq) Frequently asked questions and tutorials
- [discord community](https://discord.gg/kaVm8hGpne) Join the community and get support!
