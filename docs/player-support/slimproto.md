# Slimproto (a.k.a Squeezebox) ![Preview image](../assets/icons/slim-icon.svg){ width=70 align=right }


Music Assistant (partly) emulates a Logitech Media Server and has a full implementation of the Slim protocol (aka slimproto).
This means you can use squeezebox players directly with Music Assistant. This applies to the original Logitech branded Squeezebox hardware players like the Radio and the Duet and any software variants of it like squeezelite which runs on almost any hardware, including your own desktop OS and even ESP32 boards.

## Features

- Slimproto devices are auto detected in Music Assistant
- Slimproto devices will play in sync
- It is possible to sync Airplay devices with slimproto based devices.
- Any physical control buttons on the device should be supported as long as flow mode is not enabled.
- The player settings include some basic equaliser settings.
- The player settings allow configuration of stereo pairs of speakers.

## Known Issues / Notes

- Make sure that you do not have Logitech Media Server running.
- Make sure that you do not have the "slimproto" integration running in Home Assistant.
 
