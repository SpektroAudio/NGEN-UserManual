# Hardware Setup

---

## Connecting NGEN to other your setup

NGEN can be connected to computers, drum machines and synthesizers via USB, MIDI and CV. These connections can also be used simultaniously.

### Connecting via USB

The simplest way to use NGEN is to connect it to your computer via USB. 

The USB connection powers the unit and it's capable of sending and receiving MIDI since it works as a Class Compliant MIDI device.

### Connecting via MIDI

NGEN can also be connected to other gear via the MIDI IN and MIDI OUT 3.5mm TRS jacks (Type-A).

*Please note that NGEN still needs to be powered via USB (check the Powering NGEN section below).*

The **[Test MIDI](settings.md#midi)** feature (available under Settings / MIDI) sends a short MIDI sequence to each of the 16 MIDI channels available sequentially and it can be used to check your MIDI routings when setting up NGEN with other gear.

<figure markdown="span">
  ![Test MIDI feature](images/NGEN_MIDI_Test.gif){ width="300"; align="left"}
  <figcaption>Test MIDI feature</figcaption>
</figure>

### Connecting via CV

NGEN also features 2 pairs of CV + Gate outputs that can be used to sequence other hardware instruments (such as modular synthesizers).

More information about the available CV modes is available in the [Settings section](settings.md#cv-out).

The four outputs are available as two pairs of additional outputs available via the ```Aux Out``` parameter in the [Track](track.md) sub-menu. 

To route the output of a [track](track.md) to one of the CV outputs:

1 - Enable Advanced Mode ([Settings / General](settings.md#general)).

2 - Select one of the available CV modes ([Settings / CV Out](settings.md#cv-out)).

3 - [Select the track](track.md#track-selection) you'd like to route to one of the CV output.

4 - Open the [Track](track.md) sub-menu, navigate to the ```Aux Out``` parameter and set it to ```CV 1``` or ```CV 2```.


**Test CV 1** and **Test CV 2** are also available (Main Menu / Settings / CV) and can be used to trigger a 2-second long C2 note to the desired CV output pair.


<figure markdown="span">
  ![Test CV 1 and 2 feature](images/NGEN_CV_Test.gif){ width="300"; align="left"}
  <figcaption>Test CV 1 and 2</figcaption>
</figure>


<!-- To enable the CV output ports, set the AUX OUT of any of [Tracks](track.md) to CV1 or CV2. -->

<!-- The CV and GATE outputs on NGEN have a limited range of 3.3V and a resolution of 12bits so we recommend using an external MIDI to CV converter for a wider range and better resolution. -->

!!! danger "WARNING"
    The CV and Gate jacks are **OUTPUTS** only. **Do not** send any CV signals into them or you may run the risk of damaging your unit.

*Please note that NGEN still needs to be powered via USB (check the Powering NGEN section below).*

---

## Powering NGEN externally

If you'd like to set up NGEN without a computer, you can power it using a USB power bank / battery or a standard USB wall charger.  
NGEN's power consumption is minimal so even a 0.5A charger should work.

!!! note
    Because of NGEN's low power consumption, certain USB power banks can dismiss it as an actively charging device and may turn off after a certain period. If this happens, try using a different power bank or a USB wall charger.

---

## I2C Connection

NGEN features an 1/8 TRS I2C connection on it's left side wired with SDA on the TIP and SCL on RING.

We plan on adding I2C-related features in future NGEN firmware updates.

!!! danger "WARNING"
    Do not connect any CV outputs or other signals via 1/8 to the I2C connection otherwise you may damage your unit.

---


## Setup Examples

---

### NGEN + Computer

``` mermaid
graph LR
  A[NGEN] ----- | USB | B[COMPUTER];
```

---

<div class="forced-pb"></div>

### NGEN + Hardware MIDI Synthesizer

``` mermaid
graph LR
  A["POWER SUPPLY / COMPUTER"] ---| USB | B[NGEN] -->|MIDI| C[SYNTH];
```


---

### NGEN + Modular Synthesizer

``` mermaid
graph LR
  A["POWER SUPPLY / COMPUTER"] ---| USB | B[NGEN] --->|CV| C[MODULAR SYNTH];
  B --->|GATE| C;
```


---

### NGEN + Multiple Gear

``` mermaid
%%{ init: { 'flowchart': { 'curve': 'stepBefore' } } }%%

flowchart LR
  A["POWER SUPPLY / COMPUTER"] ---| USB | B[NGEN] -->|CV| C[MODULAR VOICE 1];

  B -->|GATE| C;

  B -->|CV| D[MODULAR VOICE 2];
  B -->|GATE| D;

  B -->|MIDI| E[MIDI THRU BOX];

  E -->|MIDI| F[SYNTH 1];
  E -->|MIDI| G[SYNTH 2];
```