# Voice Control

This section describes what is required to add a PLAY command which will be understood by Assist and will start playback to a specific player or an area. 

The core HA voice intents support NEXT TRACK, (PREVIOUS TRACK is coming), PAUSE, UNPAUSE and VOLUME to a specific player or to an area. HA does not intend to add any more media player service calls at this time so you will need to use custom sentences to cover any other of your requirements. See this [discussion for how](https://github.com/orgs/music-assistant/discussions/2176).

## LLM Conversation Agent

**Installation Requirements**

- You need to be running HA 2024.6.0 or later
- You need to be running the latest version of the HA Integration
- You need a voice assistant which uses a LLM AI conversation agent configured (even if you want to just type in the query)
- Preferably allow the auto-exposure of MA media players to Assist (otherwise you will have to do that manually)

### Usage

Any reasonable request to play on a device should be understood by the LLM thus there are no mandatory sentences that must be used. 

In some cases it is still advantageous to also setup the `MA Specific Conversation Agent` described below as it provides a more specific prompt for the AI model to use and the LLM will be made aware of and can use this additional functionality. For example, in testing the LLM did not return a good response for `play a list of 5 classic 80's rock tracks` if the `MA Specific Conversation Agent` described in the next section was not configured.

## MA Specific Conversation Agent

During [Chapter 5 of "Year of the Voice"](https://www.youtube.com/live/djEkgoS5dDQ?si=pt8-qYH3PTpsnOq9&t=3699), [JLo](https://blog.jlpouffier.fr/chatgpt-powered-music-search-engine-on-a-local-voice-assistant/) showed something he had been working on to use the OpenAI integration along with Music Assistant. Note that this originally worked by using custom intents and it was difficult to reliably specify a player or an area for the music to be sent to. For this reason the functionality is built into the MA Integration. This method does not require you to expose your entities to the AI LLM; media player entities only need to be exposed internally to Assist. This Integration only sends to openAI part of the request you make and openAI only responds with a JSON formatted response which is then used locally to initiate playback.  

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
