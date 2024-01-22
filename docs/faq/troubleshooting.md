### **First things to try and how to report issues**

Probably the most common issue is people trying to run MA with complicated network setups. Running behind VPNs, across subnets or VLANs, behind firewalls, local SSL, using reverse proxies or inside containers is not supported (it might work but we can’t troubleshoot for you as MA is run by a small team who don't have the resources to help with non-MA issues). Search Discord for these problems as users have regularly reported these issues and found that it is their setup that was causing the fault; their solution might help you.

There are settings available in MA SETTINGS>>CORE>>STREAMSERVER>>ADVANCED that might help you if you have complicated setups. If you are running MA in your own docker container then make sure you have the correct  PUBLISHED IP ADDRESS set in the SETTINGS for the STREAMSERVER.

Most players are discovered using mDNS (broadcast) so if your players do not get discovered it means that your network is blocking that traffic (e.g. IGMP or multicast snooping or filtering). You will have to check your settings (e.g. WiFi setup) if multicast is being blocked. Business solutions tend to block multicast traffic as much as possible as it hurts performance when there are many clients. In a home setup is it mandatory to have because all home gear relies on multicast.

Make sure the HA internal url is set correctly. HA Settings --> System --> Network --> Home Assistant URL --> Local network (set to automatic or use your internal HA IP). If it is automatic you can try changing it to http://your.internal.ip:8123/

MA streams at high quality which may max out poor network connections. If possible used wired connections for MA players. Try changing to a lower quality codec by going to SETTINGS>>PLAYERS>>(Menu for player desired)>>CONFIGURE>>ADVANCED SETTINGS>>OUTPUT CODEC (Do not think that because you are playng an MP3 this isn't important as MA re-encodes the music stream. Input codec is not always the same as the output codec) 

Report issues using the template with as much detail as possible. Often posts aren’t clear about exactly what is typed where, how something is configured or what series of menus are selected. Look in the LOGS for errors. You can also look in the Browser console when you have front end issues which in Chrome browser is --> F12 for developer tools --> console. Please include the following in ALL reports:

- What music provider is in use
- What player provider is in use
- Are the players grouped?
- How is playback being instigated (e.g. automation or via the UI)

!!! note
    You can retrieve the full MA logs by going to the MA settings and clicking on CORE

### **Why aren't tracks/albums matching between providers**

Matching items between streaming providers is challenging as they do not all provide the same or unique metadata to definitivly identify a match. If you think there is an obvious match (eg. same artist and track and album) then please submit an issue report. For more information about how MA uses metadata in various ways see here https://github.com/music-assistant/hass-music-assistant/discussions/543

### **My media player is not available or not playing**

Review the list of player providers. If your device doesn't support one of the listed protocols then it won't currently work. Review the [GitHub Discussions](https://github.com/orgs/music-assistant/discussions) to see if others have requested support and join in the conversation.

If your device does support one of the supported protocols then review the documentation for that player provider for known issues and troubleshooting tips.

If your device still doesn't work and you think it should then review the full logs for discovery information and errors. Review the first things to try at the top of this page as usually if you get this far without identiying why the player isnt working it will be a networking or non-standard installation issue which, generally, you will need to resolve. Search the Github [Issues](https://github.com/orgs/music-assistant/issues), [Discussions](https://github.com/orgs/music-assistant/discussions) and [Discord](https://discord.gg/kaVm8hGpne)) as likely someone has asked your question before.

### **All my media is missing** 

Ensure the favourites filter is OFF. At the top of each view is a ❤️. Ensure it is hollow.

If you are trying to view playlists through the HA media view then you should note that only favourited playlists will show up and additionally you need to have a MA player selected to see the MA Library. HA's media browser doesn't have any filter or sorting options like MA's frontend has.

### **I don't see any tracks or albums for an Artist on a streaming provider** 

See the [Usage and Music Provider notes](../usage.md)

### **My local album art isn’t being picked up**

Art embedded in music tracks will always be picked up but folder.jpg images will only be imported if the folder name **exactly** matches the album (except for any characters that are prohibited in folder names. E.g. / )

### **There isn't any metadata for my music**

For local files, you can either fully tag your music (this is preferred and it is recommended to use [Picard](https://picard.musicbrainz.org/)) or have an artist folder with the artist.nfo in there (just like the images) and that will be preferred. Online metadata providers are only queried when there is no local data. https://kodi.wiki/view/NFO_files

### **I have updated but MA looks like the old version or isn’t working**

Possibly your browser is using a cached version of the front end. Try forcing a refresh Chrome, Firefox, or Edge for Windows: Press Ctrl+F5 (If that doesn’t work, try Shift+F5 or Ctrl+Shift+R).

if the above doesn’t work look [here for some more options](https://www.webinstinct.com/faq/how-to-disable-browser-cache)

For the IOS app see [here](https://community.home-assistant.io/t/anyone-know-how-to-clear-cache-in-the-ios-app/64569/10)

### **The second zone of my amplifier is not seen by MA or MA won't turn on my amplifier**

MA is an INPUT to your amplifier. So you need to power on your amplifier and then select the INPUT that MA is streaming to (e.g. Airplay, DLNA, Chromsecast). For this reason MA does not see the amplifier zones it only sees the compatible inputs of the amplifier. 

Some amplifiers may auto turn on when a signal is detected so check the amplifier options. If this functionality is not available then you will need to power on the amplifier via another means. The power icons that are seen beside the players must be seen as starting and stopping the stream to the player not as physically powering on or off the device.

### **My local music isn’t being imported or I’m seeing missing ID3 tag warnings in the logs** 

This is likely a tagging problem. See [here](../music-providers/filesystem/)
