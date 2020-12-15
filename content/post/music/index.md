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
  name: Matlab Code
  url: https://github.com/hluebbering/music-in-matlab
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

```{matlab}
function song = melodyTrack()
% single-pitch notes created from TRIANGLE waves
% MAKE RIGHT HAND NOTES
D5_eighth = makeNote(120, 'e', 587, 'triangle');
A4_eighth = makeNote(120, 'e', 440, 'triangle');
F4_eighth = makeNote(120, 'e', 349, 'triangle');
C5_eighth = makeNote(120, 'e', 523, 'triangle');
E4_eighth = makeNote(120, 'e', 330, 'triangle');
B4_eighth = makeNote(120, 'e', 494, 'triangle');
G4_eighth = makeNote(120, 'e', 392, 'triangle');
G4_quarter = makeNote(120, 'q', 392, 'triangle');
E4_quarter = makeNote(120, 'q', 330, 'triangle');
B4_half = makeNote(120, 'h', 494, 'triangle');

% COMBINE RIGHT HAND MELODIES
% lined up one after another using concatenation
melody1 = cat(2, D5_eighth, A4_eighth, F4_eighth, D5_eighth, A4_eighth, F4_eighth, D5_eighth, A4_eighth);
melody2 = cat(2, C5_eighth, A4_eighth, E4_eighth, C5_eighth, A4_eighth, E4_eighth, C5_eighth, A4_eighth);
melody3 = cat(2, C5_eighth, A4_eighth, E4_eighth, C5_eighth, A4_eighth, E4_eighth, C5_eighth, A4_eighth);
melody4 =  cat(2, B4_eighth, G4_eighth, E4_eighth, B4_eighth, G4_quarter, E4_quarter, B4_half);
melody5 = cat(2, D5_eighth, A4_eighth, F4_eighth, D5_eighth, A4_eighth, F4_eighth, D5_eighth, A4_eighth);
melody6 = cat(2, C5_eighth, A4_eighth, E4_eighth, C5_eighth, A4_eighth, E4_eighth, C5_eighth, A4_eighth);
melody7 = cat(2, C5_eighth, A4_eighth, E4_eighth, C5_eighth, A4_eighth, E4_eighth, C5_eighth, A4_eighth);
melody8 = cat(2, B4_eighth, G4_eighth, E4_eighth, B4_eighth, G4_quarter, E4_quarter, B4_half);

% RIGHT HAND MELODY ALL TOGETHER
% lined up one after another using concatenation
song = cat(2, melody1, melody2, melody3, melody4, melody5, melody6, melody7, melody8);

end

```


- `chordsTrack.m` function simulates the chords track played for harmony

```{matlab}
function chords = chordsTrack()
% chords lined up one after the other, matching up at key points with melody track
% Each chord is the sum of single-pitch notes

% MAKE LEFT HAND NOTES (KEY OF A FLAT)
% Play all B's, E's, A's and D's FLAT frequency
rest = makeRest(120, 'h');
E4_half = makeNote(120, 'h', 311, 'triangle');
B3_half = makeNote(120, 'h', 234, 'triangle');
A3_half = makeNote(120, 'h', 208, 'triangle');
D4_half = makeNote(120, 'h', 277, 'triangle');
G3_half = makeNote(120, 'h', 196, 'triangle');
F3_half = makeNote(120, 'h', 171, 'triangle');
C4_half = makeNote(120, 'h', 262, 'triangle');

% MAKE CHORDS
% chords created by summing notes 
chord1 = 0.25 * E4_half + 0.25 * B3_half + 0.25 * G3_half;
chord1_rest = cat(2, chord1, rest);

chord2 = 0.25 * D4_half + 0.25 * B3_half + 0.25 * F3_half;
chord2_rest = cat(2, chord2, rest);

chord3 = 0.25 * D4_half + 0.25 * B3_half + 0.25 * F3_half;
chord3_rest = cat(2, chord3, rest);

chord4 = 0.25 * F3_half + 0.25 * A3_half + 0.25 * C4_half;
chord4_rest = cat(2, chord4, rest);


% RIGHT HAND KEYS (KEY OF A FLAT)
% Play all B's, E's, A's and D's flat frequency
B4_eighth = makeNote(120, 'e', 466, 'triangle');
B4_quarter = makeNote(120, 'q', 466, 'triangle');
B4_half = makeNote(120, 'h', 466, 'triangle');
E5_quarter = makeNote(120, 'q', 622, 'triangle');
E5_eighth = makeNote(120, 'e', 622, 'triangle');
A4_half = makeNote(120, 'h', 415, 'triangle');
D5_quarter = makeNote(120, 'q', 554, 'triangle');
D5_eighth = makeNote(120, 'e', 554, 'triangle');
C5_quarter = makeNote(120, 'q', 523, 'triangle');
C5_eighth = makeNote(120, 'e', 523, 'triangle');
% RIGHT HAND MELODY
melody1 = cat(2, E5_quarter, E5_quarter, E5_quarter, E5_eighth, C5_eighth);
melody2 = cat(2, D5_quarter, C5_quarter, B4_half);
melody3 = cat(2, D5_quarter, D5_quarter, D5_quarter, D5_eighth, B4_eighth); 
melody4 = cat(2, C5_quarter, B4_quarter, A4_half);

% COMBINING LEFT HAND CHORDS AND RIGHT HAND MELODY
% in order to sum two lists of sound samples, 
% the two lists must have exactly the same number of numbers in them
part1 = chord1_rest + 0.25 * melody1;
part2 = chord2_rest + 0.25 * melody2;
part3 = chord3_rest + 0.25 * melody3;
part4 = chord4_rest + 0.25 * melody4;

% track is created by concatenating chords
chords = cat(2, part1, part2, part3, part4, part1, part2, part3, part4);


end
```


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

