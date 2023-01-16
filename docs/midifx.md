# MIDI FXs

---

## About MIDI FXs:

NGEN features a number of different MIDI FX's that can be used to manipulate and enhance sequences played by the Generators non-distructively.

---


## MIDI FXs Parameters:

As with [Generators](generators.md), each MIDI FXs contains a set of parameters that can be adjusted via the ```MIDI FX``` sub-menu available in the [```MAIN MENU```](menunavegation.md#main-menu). 

While in the MIDI FX sub-menu, the most relevant parameters for selected MIDI FX are mapped to the NGEN's potentiometers:

* 4 Parameters mapped to the potentiometers directly.
* 4 Additional parameters are accesible by holding down **SHIFT** while moving the potentiometers.

Certain MIDI FX's also use the ++"GENERATE"++ button to generate new internal sequences.

---

## List of Available MIDI FXs:

### ACCENT

Accent changes the MIDI velocity of incoming MIDI notes according to it's internal velocity sequence in order to create more repeatable and prominent accent patterns.

**List of Parameters:**

| **Parameter** | **Description** | **Hardware Mapping** | **Advanced** |
|: ------------ |: ------------- |: -------------- |: ---------- |
| Generate | Generates a new accent sequence | ++"GENERATE"++ |   |
| Length | Length of the accent sequence | ++"PARAM 2"++ |   |
| Intensity | Increases the velocity of all MIDI notes to 127 | ++"PARAM 3"++ |   |


### CHORD

Chords transforms single notes into chords by adding up to 3 notes on top of incoming notes based on specified intervals. There's also an option to quantize those additional notes or leave them unquantized. 

** List of Parameters:**

| **Parameter** | **Description** | **Hardware Mapping** | **Advanced** |
|------------|:-------------|:--------------|:----------|
| Quantize | Quantizes all intervals to the active key / scale | | |
| Chord Interval 1 | Interval of the first chord note | ++"PARAM 1"++ | |
| Chord Interval 2 | Interval of the second chord note | ++"PARAM 2"++ | |
| Chord Interval 3 | Interval of the third chord note | ++"PARAM 3"++ | |


### ECHOES

Echoes is a MIDI delay effect that creates additional notes that are delayed by the specified delay time.

** List Of Parameters:**

| **Parameter** | **Description** | **Hardware Mapping** | **Advanced** |
| ------------ |: ------------- |: -------------- |: ---------- |
| Delay Time | Delay time in milliseconds | ++"PARAM 1"++ | |
| Feedback | Feedback amount | ++"PARAM 2"++ | |
| Probability (```PROB```) | Probability of the echoes | ++"PARAM 3"++ | |
| Falloff (```FALLOFF```) | MIDI Velocity falloff of the echoes | ++"PARAM 4"++ | |
| Octave Random (```OCT RND```) | Randomizes the octave of the echoes |  ++"FUNCTION"++ + ++"PARAM 1"++ | |

### GLITCH

The Glitch MIDI FX can be used to mangle and glith up sequences via a random ratcheting processor and pitch / velocity modulation. It's great for spicing up sequences and adding some IDM-style glitches to a performance.

** List of Parameters:**

| **Parameter** | **Description** | **Hardware Mapping** | **Advanced** |
|------------|:-------------|:--------------|:----------|
| Probability | Probability of a glitch happening | ++"PARAM 1"++ | |
| Repeats | Maximum number of note ratchets | ++"PARAM 2"++ | |
| Note Length | Length of the note ratchets | ++"PARAM 3"++ | |
| Random | Amount of glitch randomization | ++"PARAM 4"++ | |
| Pitch Mod | Enables octave randomization | | |

### HUMANIZER

Humanizer is designed to make sequences sound more natural as if it was played by a human. It works by adding random amounts of delay and velocity modulation to incoming notes.

It's great for making polyphonic sequences sound less mechanical and static.

** List of Parameters:**

| **Parameter** | **Description** | **Hardware Mapping** | **Advanced** |
|------------|:-------------|:--------------|:----------|
| Delay Probability (```DLY PROB```) | Probability of delaying a MIDI note | ++"PARAM 1"++ | |
| Velocity Probability (```VEL PROB```) | Probability of a modulating a note's velocity | ++"PARAM 2"++ | |
| Max Delay | Maximum delay length | ++"PARAM 3"++ | |
| Velocity Modulation (```VEL MOD```) | Depth of velocity modulation | ++"PARAM 4"++ | |

###MODULATOR

The Modulator FX can be used for modulating MIDI control changes (CC) of external instruments. A common use-case would be to use it to modulate a filter cutoff frequency of a synthesizer via MIDI CC.

** List of Parameters:**

| **Parameter** | **Description** | **Hardware Mapping** | **Advanced** |
|------------|:-------------|:--------------|:----------|
| Generate | Generates a new modulation sequence | ++"GENERATE"++ | |
| Send | Sends a CC message (for mapping purposes) | | |
| Sequence Amount (```SEQ AMOUNT```)| Amount of sequence modulation | ++"PARAM 1"++ | |
| Length | Length of the modulation sequence | ++"PARAM 2"++ | |
| CC Out | CC number to send | ||
| Depth | 

### PROGRAM SEQUENCER (PROG SEQ)

The Program Sequencer MIDI FX offer a way of sequencing MIDI Program Changes creatively. When used with synthesizer / drum machines that respond quickly to program changes, these program change sequences will make it sound as if there're multiple different instruments being played sequentially.

** List of Parameters:**

| **Parameter** | **Description** | **Hardware Mapping** | **Advanced** |
| ------------ |: ------------- |: -------------- |: ---------- |
| Generate | Generates a new program change sequence | ++"GENERATE"++ |   |
| Length | Length of the program change sequence | ++"PARAM 2"++ |   |
| Hits | Number of MIDI notes needed to advance the sequence | ++"PARAM 3"++ |   |
| Max Program (```MAX PROG```) | Maximum program change number | ++"PARAM 4"++ |   |
| Sync | Waits for the next clock pulse to send the next program change | | |
| Delay | | | |
| Step 1 | Sets the program change number of the first step | | | |
| Step 2 | Sets the program change number of the second step | | | |
| Step 3 | Sets the program change number of the third step | | | |
| Step 4 | Sets the program change number of the fourth step | | | |
| Step 5 | Sets the program change number of the fifth step | | | |
| Step 6 | Sets the program change number of the sixth step | | | |
| Step 7 | Sets the program change number of the seventh step | | | |
| Step 8 | Sets the program change number of the eighth step | | | |

### SHAPER

The Shaper MIDI FX scales incoming MIDI notes based on an adjustable pitch and velocity range.
It also includes options to multiply note lengths and to map MIDI notes to different MIDI channels based on their pitch (useful for triggering certain drum machines / samplers such as the Elektron Digitakt and Octatrack).

** List of Parameters:**

| **Parameter** | **Description** | **Hardware Mapping** | **Advanced** |
|------------|:-------------|:--------------|:----------|
| Pitch Minimum (```PITCH MIN```) | Lowest possible note (0-127) | ++"PARAM 1"++ | |
| Pitch Maximum (```PITCH MAX```) | Highest possible note (0-127) | ++"PARAM 2"++ | |
| Velocity Minimum (```VEL MIN```) | Lowest possible velocity (0-127) | ++"PARAM 3"++ | |
| Velocity Maximum (```VEL MAX```) | Highest possible velocity (0-127) | ++"PARAM 4"++ | |
| Length Multiplier (```LEN MULT```) | Multiplies the length of incoming MIDI notes | | |
| Channel Mapping (```CH Map```) | Maps incoming MIDI notes to different MIDI channels based on their pitch * | | |
| Map Pitch (```Map Pitch```) | Sets the pitch of converted MIDI notes (while in ```Ch Map```) | | |


** C notes are mapped to the Track's Output Channel and all other pitches are mapped according to their distance from C (in semitones), so D notes are mapped to Out Ch + 2, D# to Out CH + 3, and so on. After being mapped to their respective channels, all notes are set to the same pitch (Map Pitch).*

### SPRAY

The Spray MIDI FX creates a delay-like effect by generating copies of incoming MIDI notes based on probability and random delay time.

** List of Parameters:**

| **Parameter** | **Description** | **Hardware Mapping** | **Advanced** |
| ------------ |: ------------- |: -------------- |: ---------- |
| Max Delay | Maximum delay time (in milliseconds) | ++"PARAM 1"++ | |
| Max Repeats | Maximum number of repetitions of delayed notes (similarto feedback) | ++"PARAM 2"++ | |
| Probability (```PROB```) | Probability of spraying a note | ++"PARAM 3"++ | |
| Falloff (```FALLOFF```) | MIDI Velocity falloff of sprayed notes | ++"PARAM 4"++ | |
| Octave Random (```OCT RND```) | Randomizes the octave of the sprayed notes | ++"FUNCTION"++ + ++"PARAM 1"++| |
| Velocity Random (```VEL RND```) | Randomizes the velocity of the sprayed notes | ++"FUNCTION"++ + ++"PARAM 2"++ | |


### STRUM

The Strum MIDI FX can be used to create a strumming effect by adding a short random delay between notes received within the same 1/16 clock step.

** List of Parameters:**

| **Parameter** | **Description** | **Hardware Mapping** | **Advanced** |
|------------|:-------------|:--------------|:----------|
| Max Delay | Maximum delay time (in milliseconds) | ++"PARAM 1"++ | |