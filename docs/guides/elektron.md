# Using NGEN with Elektron Devices

## Description

Some drum machines / samplers like the Elektron devices use a different method for MIDI input: instead of using different pitches (like C1, C#1, etc) to trigger the different parts, these devices use separate MIDI Channels per part.

In order to make the drum-related [Generators](../generators.md) work with these devices, we've included a special feature to the [**Shaper MIDI FX**](../midifx.md) called **Channel Mapping**.  

When enabled, Shaper splits incoming MIDI notes to different channels and changes the pitch value (set via the Map Pitch parameter).  
The Pitch of each incoming note is used to indicate a different offset (C = 0, C#1 = 1, D = 2 ... B = 11) which is added to the [**Track**](../track.md) **Output Channel** to calculate the final note MIDI channel.

<div class="no-print">

Example diagram:


``` mermaid
%%{init: {'flowchart' : {'curve' : 'linear'}}}%%
flowchart LR
  A[Track 1<br>DRUMGEN<br>Note 1: C1<br>Note 2: C#1<br>Note 3: D1<br> Note 4: D#1];
  S[Track 2<br>SAMBA<br>Note 1: C1<br>Note 2: C#1<br>Note 3: D1<br> Note 4: D#1]

  subgraph Shaper CH MAP 
    Z[Map Pitch: C3<br>Track Out Channel: 1];
    B[Channel Offset: 0];
    C[Channel offset: +1];
    D[Channel offset: +2];
    E[Channel offset: +3];
  end

  subgraph Shaper CH MAP 
    N[Map Pitch: C3<br>Track Out Channel: 5];
    J[Channel Offset: 0];
    K[Channel offset: +1];
    L[Channel offset: +2];
    M[Channel offset: +3];
  end

  subgraph Destination MIDI IN
    F[Channel 1];
    G[Channel 2];
    H[Channel 3];
    I[Channel 4];

    O[Channel 5];
    P[Channel 6]
    Q[Channel 7];
    R[Channel 8];
  end


  A -- C1 --> B;
  A -- C#1 --> C;
  A -- D1 --> D;
  A -- D#1 --> E;

  S -- C1 --> J;
  S -- C#1 --> K;
  S -- D1 --> L;
  S -- D#1 --> M;

  B -- C3 (Ch: 1) --> F;
  C -- C3 (Ch: 2) --> G;
  D -- C3 (Ch: 3) --> H;
  E -- C3 (Ch: 4) --> I;

  J -- C3 (Ch: 5) --> O;
  K -- C3 (Ch: 6) --> P;
  L -- C3 (Ch: 7) --> Q;
  M -- C3 (Ch: 8) --> R;
  

```
</div>

---

## Step-by-step Instructions

To use NGEN with an Elektron device, follow these steps:

1 - Connect NGEN's MIDI output to your Elektron device.

2 - Configure the Elektron device to listen to MIDI Channels 1-8. In this example, we'll use parts 1-4 for drums (kick, snare, hihat, percussion) and parts 5-8 for tonal instruments.

3 - In **NGEN**, select **Track 1**, open the Track sub-menu, and select the **DrumGen** Generator.

4 - Select the **Shaper MIDI FX** for Track 1.

5 - Return to the **Main Menu** and navigate to the **MIDI FX** sub-menu.

6 - Enable the **```Ch Map```** feature.

7 - Return to the **Main Menu** and navigate in to the **Generator** sub-menu.

8 - Set **DrumGen's Note 1-4** parameters to C1, C#1, D1, and D#1. With Ch Map enabled, the 4 DrumGen parts will output to the MIDI Channels 1, 2, 3, and 4. Using different pitches for these parameters will change the MIDI Channels used for DrumGen.

9 - Activate Track 2 in NGEN, set it's Output Channel to 5, and select an appropriate Generator / MIDI FX.

10 - Repeat step #9 for Tracks 3 and 4.