---
title: Music in Matlab
subtitle: Example using OverTheRainbow.m
abstract: Make music in Matlab, Adobe Audition, and Waveform
date: 2019-07-12
math: true
diagram: true

links:
- icon: github
  icon_pack: fab
  name: Follow
  url: https://github.com/hluebbering
url_code: ""
url_pdf: ""
url_slides: ""
url_video: ""

---


<span style="color: #f2cf4a; font-family: Babas; font-size: 2em;">Music in Matlab</span>

*Make music in Matlab, Adobe Audition, and Waveform*

### In `MATLAB`, the provided code creates the first four measures of *"Over the Rainbow,"* combining the right and left hands. Using various functions, we can make specific notes and sum and concatenate pieces of music.

#### Example using OverTheRainbow.m

- Call function from the Command Line

- save in a variable the sound data returned from function call

- play the sound data, as shown below:

`rainbow = overTheRainbow;`

`sound(rainbow, 44100);`

`audiowrite('rainbow.wav', rainbow, 44100);`


#### Example using myMusic.m

- Simulating the use of tracks by making different sounds in MATLAB -- three different lists of numbers -- summed into one song

- `melodyTrack.m` function that simulates a melody track

- `chordsTrack.m` function simulates the chords track played for harmony

- `droneTrack.m` function simulates a droning or repeating sound

- play the sound data, as shown below:

`mySong = myMusic;`

`sound(mySong, 44100);`

- assumed that music will be constructed at a sampling rate of 44100 Hz (i.e., samples/second)

