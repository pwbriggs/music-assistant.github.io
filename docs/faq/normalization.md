# Volume Normalization

The normalization value to totally avoid clipping should be -23 LUFS based on this official documentation https://tech.ebu.ch/docs/r/r128.pdf but values differ per plattform so it is complicated to get the right value.

Here is a good document from the mastering plugin developer izotope comparing different plattforms like YouTube, Spotify, Deezer, Tidal and many more. [This page explains the whole topic very well](https://www.izotope.com/en/learn/mastering-for-streaming-platforms.html#loudness-specifications-by-streaming-platform)

Noting the above, the default value is -17 which should be a good compromise in 99% of cases. MA originally had it set the to EBU's standard value of -23 but then there were complaints from people finding the music too silent.

The equalizer is bypassed when the value is set to 0 but in general, it is not recommended to turn off the volume normalization because there are so many different loudness levels, especially if music is played from different sources. MA uses an integrated loudness level based on the EBU-R128 standard and only adjusts gain of the entire track up or down so there is no compression of dynamic range. For that same reason of not losing dynamic range MA does not use a limiter and it's the user's responsibility to use sane values for the target level of the volume normalization.

If audio is only played from one single source (e.g. Deezer) and that audio source already has normalized its audio files, then its safe to disable normalization in MA. If audio is played from different sources or audio is not normalized at the source, it is highly recommended to leave normalization enabled for the best experience.

**More technical details**

All tracks are processed as raw pcm by Music Assistant internally. So everything that is played will be first converted to raw pcm in the sample rate and bit depth of the origin (unless flow mode is enabled) and the gain adjustment is done while extracting the raw source media so the pcm chunks passed into the streaming engine have the gain adjustment applied. In this way there should be enough headroom within the 16 or 24 bits bit depth. Converting to 32 or 64 bits floating point is something that has been considered but it was decided that it was not worth the overhead and comes at the risk of dithering when going back from 64 bits to 16 or 24 bits so instead the MA design settled on applying the correction gain while extracting the raw audio from its base codec.

All further processing in MA is done at PCM raw audio level, such as the optional equalizer (in the future maybe some room correction or other filters) - if "flow mode" is enabled crossfading is also done on the raw pcm chunks but that will upsample all audio into one static sample rate and bit depth to create one "flow" of audio to send to the player.

The final part in the chain is that MA sends either the raw pcm data to the player or encodes it into FLAC due to it being lossless while keeping a reasonable file size.
