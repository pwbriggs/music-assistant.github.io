## My local HA device

Install the [squeezelite addon](https://github.com/pssc/ha-addon-squeezelite) which will then allow streaming over an audio connection from the HA host to your speaker or amplifier

## My random connected device

Install a [squeeze lite compatible application](https://sourceforge.net/projects/lmsclients/files/squeezelite/) to your mobile or other devices which MA will be able to stream to.

See here for info on [how to run squeezelite on Windows](https://github.com/orgs/music-assistant/discussions/1123#discussioncomment-6652948)

The [MA Companion App](../companion-app.md) can also be configured to run a squeezelite client which will allow playback to the device running it.

## My non-networked device or bluetooth speaker

If you have a spare Raspberry Pi (any model) then [PiCoreplayer](https://www.picoreplayer.org) is an excellent solution than can also connect to Bluetooth speakers. If you want better sound quality from your Pi you could add a [HiFiBerry](https://www.hifiberry.com/docs/hardware/comparison-of-hifiberry-cards-for-audio-recording/)

esp32-based hardware with at least 4MB of flash and 4MB of PSRAM will be capable of running [squeezelite-esp32](https://github.com/sle118/squeezelite-esp32). A nice solution with speaker terminals is the [Louder ESP32](https://www.tindie.com/products/sonocotta/louder-esp32/)

## My browser

Use a [Snapserver](../player-support/snapcast.md) and the Snapweb option.

## Music Assistant

You could use [Darkcast](http://www.darkice.org/) to stream to [Icecast](https://www.icecast.org/) which in turn sets up a web radio stream that you could add to MA! You could use this to stream your turntable around the house for example. Here is a [handy tutorial](https://maker.pro/raspberry-pi/projects/how-to-build-an-internet-radio-station-with-raspberry-pi-darkice-and-icecast). For input a [HiFiBerry](https://www.hifiberry.com/docs/hardware/comparison-of-hifiberry-cards-for-audio-recording/) could be used or a USB Audio Interface like [this one](https://www.behringer.com/product.html?modelCode=P0484) 

