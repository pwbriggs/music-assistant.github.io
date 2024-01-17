# Snapcast ![Preview image](../assets/icons/snapcast-icon.svg){ width=70 align=right }

_Available since version: 2.0.0b76 contributed and maintained by @SantiagoSotoC_

Music Assistant now supports Snapcast, a powerful solution for synchronized multi-room audio streaming. Snapcast enables seamless playback across various devices, creating an immersive audio experience.
Whether you're using Snapcast-compatible speakers or devices like Raspberry Pi, you can enjoy synchronized audio playback effortlessly.

## Features

- Synchronized playback across all Snapcast devices.
- Lossless audio quality with options for 48 kHz /16bits PCM.

## Known issues/notes

- Music Assistant currently implements Snapcast version 0.27.0 only; future updates may include support for newer versions.
- Snapcast players don´t support crossfading of audio by default. For full gapless support and enhanced crossfading, enable "flow mode" in the player's advanced settings.
- If it is necessary to adjust the latency of a client, it must be done from another interface such as snapdroid or snapweb
- Pausing the player is NOT supported. If you try and do that you will get weird behaviour.

## Troubleshooting/tips

- The snacast app for ios is broken, it uses an old version of snapclient, using it brings problems with this provider.
- Make sure you are using snapserver version 0.27.0 with the command "snapserver -v".
- Make sure that the ports on the snapserver host 1704, 1705 are open. Also make sure that for each client a port equal to or greater than 4953 is open.
- Try the default snapcast settings and then make changes as you see necessary.
- In Music Assistant settings, you can disable Snapcast devices you don't use.
- For detailed troubleshooting, check Music Assistant logs for insights and report any issues with the provided logs.

## Install Snapserver

### On Linux 

Snapcast packages are available for several Linux distributions:

- [Debian](#debian)
- [OpenWrt](#openwrt)
- [Alpine Linux](#alpine-linux)
- [Gentoo Linux](#gentoo-linux)
- [Archlinux](#archlinux)
- [Void Linux](#void-linux)

### Debian

For Debian (and Debian-based systems, such as Ubuntu, Linux Mint, elementary OS), download the package for your CPU architecture from the [latest release page](https://github.com/badaix/snapcast/releases/latest).

For example, for Raspberry Pi `snapserver_0.27.0-1_armhf.deb`, for laptops `snapserver_0.27.0-1_amd64.deb`.

#### Using apt 1.1 or later:

```bash
sudo apt install </path/to/snapserver_0.27.0-1_[arch].deb>
```

If you encounter the error `E: Unable to locate package` then do this in two steps:
```
sudo wget https://github.com/badaix/snapcast/releases/download/v0.27.0/snapserver_0.27.0-1_armhf.deb
sudo apt install ./snapserver_0.27.0-1_armhf.deb
```

#### Using dpkg:

Install the package:

```bash
sudo dpkg -i </path/to/snapserver_0.27.0-1_[arch].deb>
```

Install missing dependencies:

```bash
sudo apt-get -f install
```

### Alpine Linux

On Alpine Linux, use:

```bash
apk add snapcast-server
```

### Gentoo Linux

On Gentoo Linux, use:

```bash
emerge --ask media-sound/snapcast
```

### Archlinux

On Archlinux, Snapcast is available through the AUR. To install, use your favorite AUR helper, or do:

```bash
git clone https://aur.archlinux.org/snapcast
cd snapcast
makepkg -si
```

### Void Linux

To install the server:

```bash
# xbps-install snapserver
```

## Install Snapclient

### Linux

Snapcast provides packages for various Linux distributions to install the Snapclient.

#### Debian-based systems (e.g., Ubuntu, Linux Mint)

1. Download the Snapclient package for your CPU architecture from the [latest release page](https://github.com/badaix/snapcast/releases/latest).

   - For Raspberry Pi: `snapclient_0.27.0-1_armhf.deb`
   - For laptops: `snapclient_0.27.0-1_amd64.deb`

2. Using `apt`:

   ```bash
   sudo apt install </path/to/snapclient_0.27.0-1_[arch].deb>
   ```

3. Alternatively, using `dpkg`:

   ```bash
   sudo dpkg -i </path/to/snapclient_0.27.0-1_[arch].deb>
   sudo apt-get -f install
   ```
#### Alpine Linux

On Alpine Linux, use:

```bash
apk add snapcast-client
```

#### Gentoo Linux

On Gentoo Linux, use:

```bash
emerge --ask media-sound/snapcast
```

#### Archlinux

On Archlinux, Snapcast is available through the AUR. To install, use your favorite AUR helper, or do:

```bash
git clone https://aur.archlinux.org/snapcast
cd snapcast
makepkg -si
```

#### Void Linux

To install the client:

```bash
# xbps-install snapclient
```

### Enable SnapWeb

1. **Locate the Snapcast Configuration File:**
   - Find the configuration file for Snapcast on your system. It is often named `snapserver.conf`. The location of this file is normally found in /etc but may vary depending on your installation method and operating system.

2. **Edit the Configuration File:**
   - Open the `snapserver.conf` file in a text editor.

3. **Enable Snapweb:**
   - Look for a section in the configuration file related to http. There might be a line that looks like `doc_root = /usr/share/snapserver/snapweb` or similar. If this line is commented out (starts with `#`), remove the `#` to uncomment it and enable Snapweb. 
4. **[Optional]: Change web port**
     - Look for a section in the configuration file related to http. There might be a line that looks like `webport = 1780` or similar. If this line is commented out (starts with `#`), remove the `#` to uncomment it and enable Snapweb. You may also need to adjust the port number if desired.

5. **Save the Changes:**
   - Save the changes to the configuration file.

6. **Restart Snapcast:**
   - Restart the Snapcast server to apply the changes to the configuration. This can usually be done by restarting the Snapcast service or process.

7. **Access Snapweb:**
   - Open a web browser and navigate to the specified port (e.g., `http://localhost:1780` if the default port is used). This should allow you to access the Snapweb interface.

## Snapdroid for Snapcast on Android

Snapdroid is an Android app designed for use with Snapcast. It can be found on the Google Play Store.

### Installation Steps:

1. **Open Google Play Store:**
   - On your Android device, open the Google Play Store.

2. **Search for Snapdroid:**
   - Use the search bar within the Play Store to look for "Snapdroid."

3. **Select and Install:**
   - Find the Snapdroid app in the search results.
   - Tap on the app to view its details.
   - Click the "Install" button to download and install the app.

4. **Accept Permissions:**
   - During the installation process, the app may request certain permissions. Review them and click "Accept" if you're comfortable with the permissions.

5. **Wait for Installation:**
   - The app will be downloaded and installed on your device. Wait for the process to complete.

6. **Open Snapdroid:**
   - Once installed, you can open Snapdroid from your app drawer or home screen.