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

In `MATLAB`, the provided code creates the first four measures of *"Over the Rainbow,"* combining the right and left hands. Using various functions, we can make specific notes and sum and concatenate pieces of music.

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

```{matlab}
function drone = droneTrack()
% a repeated or sustained single-frequency note
% used off and on throughout piece

% MAKE LEFT HAND NOTES
D3_quarter = makeNote(120, 'q', 147, 'triangle');
A2_quarter = makeNote(120, 'q', 110, 'triangle');
E3_quarter = makeNote(120, 'q', 165, 'triangle');
E3_half = makeNote(120, 'h', 165, 'triangle');

% COMBINE LEFT HAND NOTES
part1 = cat(2, D3_quarter, D3_quarter, D3_quarter, D3_quarter);
part2 = cat(2, A2_quarter, A2_quarter, A2_quarter, A2_quarter);
part3 = cat(2, A2_quarter, A2_quarter, A2_quarter, A2_quarter);
part4 = cat(2, E3_quarter, E3_quarter, E3_quarter, E3_quarter, E3_half);

% lined up one after another using concatenation
drone = cat(2, part1, part2, part3, part4, part1, part2, part3, part4);

end
```

- play the sound data, as shown below:

`mySong = myMusic;`

`sound(mySong, 44100);`

- assumed that music will be constructed at a sampling rate of 44100 Hz (i.e., samples/second)

