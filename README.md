# RALN: Reaper+AbletonLive+Ninjam
A short manual to set up Ninjam, Ableton Live via Reaper on macOS Catalina.
Just text (for now).

## But why?
This manual will allow you to setup a working environment for jamming online via Ninjam, on macOS Catalina. It's based on:
* BlackHole https://github.com/ExistentialAudio/BlackHole. Brilliant virtual audio driver for macOS.
* Ableton Live https://www.ableton.com/en/live/
* Reaper (with Ninjam) https://www.reaper.fm/

I'm sure similar setup can be achieved with different DAWs as well.

As a bonus, you will have a cue track setup as well that can be used as a local preview track, not sent to Ninjam.

## BlackHole
Obviously grab it first and install it. Then we proceed with the setup:
1. Go to macOS Audio MIDI Setup and create a new **Aggregate Device**. Name it somehow. We'll call it ADJam.
2. Have BlackHole and your mac speakers selected there. So in total 16 input and 18 output channels. 17 & 18 are your speakers. Make sure they are selected as output speakers in Configure Speakers section there.

## Live
1. In Preferences > Audio, select ADJam as your output device.
2. Still on same screen, go to output config and make sure stereo pairs 1/2 and 3/4 are selected.
3. Now in Live default view go to Master and set Master Out to 1/2 and Cue Our to 3/4.
4. Click on Master Solo button and turn it into Cue button. That way tracks marked as cue will be heard only by you, not the other participants of a jam.

You can download a simple Live set from here to see the basic setup.

## Reaper / Ninjam
This is the most complicated part that will route the audio to different channels so hold on tight... You can also download a sample Reaper project to see the baseline.
1. Go to Preferences > Audio > Device and select ADJam we set up earlier.
2. Have 2 track in the project. One will be for sending sound to Ninjam, one for a local cue.
3. In the Ninjam track:
* click on Fx button and add RealNinjam plugin. This is where you'll be connecting to ninjam sessions, adjust metronome, etc.
* click on the INFX drop-down and select Input: Stereo > BlackHole 1 / 2. This is where Input 1/2 from Live will go to!
* click on Route button and select new hardware output: Channel 17 / 18. These are the speakers we added earler!
4. In the cue track:
* click on the INFX drop-down and select Input: Stereo > BlackHole 3 / 4. This is the Live cue track.
* click on Route button and select new hardware output: Channel 17 / 18. We need to hear it on speakers too.

## Things that can go wrong
Q: I can't see Cue / Master Out in Live.

A: Make sure you have you I/O section on. It's a small... I/O button on the right edge of the screen.

Q: Others can hear my cue tracks during jam.

A: Those tracks need to go via 3/4 cue track **only**. Make sure that track cue button is on and the main activator is off.

Q: I can't hear anything.

A: Well... There can be 1000 reasons why. You can should always go to see a doctor and do a hearing check. Apart from that, the setup described above **will only work if you have Live and Reaper launched**. Otherwise the sound will go to a black hole...

Q: I hear a lot of reverb.

A: Try muting Master Channel in Reaper, but leave track outputs intact. Just guessing...
