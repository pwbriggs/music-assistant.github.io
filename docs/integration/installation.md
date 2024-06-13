## Installation of the Home Assistant Integration

!!! note
    Ensure the MA server is up and running properly with music and player providers added before trying to link it to HA via the integration

- Make sure that you have the [Home Assistant Community Store](https://hacs.xyz/) installed.
- Within HACS, search for `Music Assistant` and click the entry in the search results.
- Click the big (blue) button at the bottom for `Download`.
- Click the button again and in the dialog make sure `Show beta versions` is selected if you want to use those versions.
- Download the desired version
- Restart Home Assistant.
- The MA server will normally be discovered automatically by HA and you can just click on CONFIGURE.
- If for some reason you need to add the integration manually the go to HA Settings>>Devices & services>>Integrations and click the big `+ ADD INTEGRATION` button. Look for Music Assistant and click to add it. You will need to add the server IP and port (usually 8095). Look for the relevant line in the server logs. For example, `Starting server on 172.30.32.1:8095`. 
- Click SUBMIT and the Music Assistant integration is ready for use.

!!! note 
    The HA integration will create new media_player entities for those player types which are supported natively by MA. To see the names of those players go to `HA settings>>Devices & services>>Integrations>>Music Assistant` and view the entities. It is these players that need to be targeted in automations.

## Installation of the Home Assistant Player Provider

Once the HA Integration is installed it is possible to stream to HA media player entities. In order to do that the HA Player Provider need to be installed.  However, first the Home Assistant Plug-in provider needs to be installed.

- Navigate to MA SETTINGS>>PROVIDERS and add the plug-in provider
- If using the Music Assistant add-on (i.e. HAOS), you wont need any server details, it should auto connect to the local HA instance
- If using the docker version of the MA server, you will be required to enter the URL to your HA instance and then authenticate

Next install the Home Assistant Player Provider

- You need the HA plug-in first before you can use/install this provider
- In the provider settings, you can select which players you want to utilise
- You can only use players that support "play_media", other players will be filtered out
- MA players will also be filtered out

!!! note
    Features are most likely limited with these players. Always prefer a native player provider if it exists in MA as that is optimised

## Service Calls

The integration adds three service calls for use in scripts and automations. 

- [mass.play_media](../faq/massplaymedia.md)
- [mass.play_annnouncement](../faq/massannounce.md)
- [mass.search](../faq/masssearch.md)

## OpenAI features

During [Chapter 5 of "Year of the Voice"](https://www.youtube.com/live/djEkgoS5dDQ?si=pt8-qYH3PTpsnOq9&t=3699), [JLo](https://blog.jlpouffier.fr/chatgpt-powered-music-search-engine-on-a-local-voice-assistant/) showed something he had been working on to use the OpenAI integration along with Music Assistant. Note that this originally worked by using custom intents and it was difficult to reliably specify a player or an area for the music to be sent to. For this reason the functionality is built into the MA Integration. Some people have used the [Extended OpenAI Conversation](https://github.com/jekalmin/extended_openai_conversation) custom component to do something similar but the difference is that component requires you to expose your entities to openAI. This Integration only sends to openAI part of the request you make and openAI only responds with a JSON formatted response which is then used locally to initiate playback.  

**Installation Requirements**

- You need to be running the latest version of the HA Integration
- You need a voice assistant configured (even if you want to just type in the query)
- You need to create/add another OpenAI integration that is purely for Music Assistant.
Add the prompt found [here](https://github.com/music-assistant/hass-music-assistant/blob/main/prompt/prompt.txt) when completing the configuration. For the ChatGPT version `gpt-3.5-turbo-1106` has been found to work well.
- Add a directory to your Home Assistant `config` directory named `custom_sentences/en`
- Add the file found [here](https://github.com/music-assistant/hass-music-assistant/blob/main/custom_sentences/en/play_media_on_media_player.yaml), to that directory.
- Navigate to Music Assistant in the Integration view of the HA settings. Click on CONFIGURE in the `Integration entries` section.
- Ensure the correct Conversation Agent is selected and preferably allow the auto-exposure of MA media players to Assist (otherwise you will have to do that manually)

![Preview image](../assets/screenshots/screen6.png)

### Usage

!!! note
    This functionality has only been tested with `Home Assistant` selected as the `Conversation Agent` in the voice assistant configuration.

The command to play must follow a certain format. For the following examples assume the house has three areas called `Study`, `Kitchen `and `Karen's Bedroom` and there are three media players with friendly names "`Study Sonos`", "`Google Home`" and "`Karen's Speaker`". Assist aliases are supported for areas and entities.

There are two main formats which differ by where the playing location appears in the sentence. 
```
Play Nirvana in the Study
Listen to Nirvana in the Study
In the Study play Nirvana
In the Study listen to Nirvana
```
!!! note
    You cannot ask to play to an area if there is more than one media player in that area.

You can do exactly the same as the above but use the friendly names or any assist aliases of the media player instead of the area name:

```
Play Nirvana on the Google Home
Play the Dixie Chicks First Album on Karen's Speaker
```

You can also use the words `speaker` or `player` or `media player` in conjunction with the area name:
```
Play Beds are burning by Midnight Oil on the Kitchen speaker
Play Journey Don’t stop believing on the Study media player
On Karen's Bedroom player listen to Journey Don’t Stop Believing
```

!!! note
    Queue behaviour when adding items by voice will follow the settings in MA SETTINGS>>CORE>>PLAYER QUEUES CONTROLLER.
    
### Troubleshooting

- A response of "Sorry I couldn't understand that" indicates a failure in the pipeline before it reaches the HA integration. In this case consider doing the following.
    - Ensure media players and areas are exposed to Assist
    - Try typing the command
    - Look carefully for differences as the ASCII level for punctuation variation between devices. This ’ and this ' are different
    - Try adding an alias to the MA media player entity (which can be identical to the friendly name)
    - Add the following to your `configuration.yaml` so you can see more detail about the intent failure
```
    logger:
      default: warning
      logs:
        homeassistant.components.conversation: debug
        homeassistant.components.intent: debug
```

- If when trying to play to an area you receive “An unexpected error occurred while handling the intent” then:
    - Check the log for errors related to `No entities matched`. If found then make sure you don't have any entities named identically to your area
    - Ensure you aren't trying to play to an AREA and that area has multiple media players
