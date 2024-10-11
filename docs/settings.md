#Settings

---

## About Settings

NGEN features a number of settings that let you customize your unit to better suit your needs. 

Settings are stored in the device's internal memory and are retained even after the device is powered off.  
To save your current settings, select the ```Save``` option.

---

## List of Available Settings 

### General

| **Setting**                           | **Description**                                     |
|---------------------------------------|-----------------------------------------------------|
| **Advanced**                          | Enable or disables advanced parameters and settings |
| **Variation Amount (```Var Amount```)** | Sets the global variation amount for all generators |
| **Randomize State (```Rndmize State```)** | When enabled, NGEN will randomize the states of all tracks when generating new patterns ([Track States](track.md#track-states)). |

### Display

| **Setting**                              | **Description**                                                                                                                                                                                                                |
|------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Menu List**                            | Enables list mode for menus (except for the Generator sub-menu)                                                                                                                                                                |
| **Menu Wrap**                            | When enabled, scrolling past the last item in menu                                                                                                                                                                             |
| **Show Icons**                           | Enables or disables graphical icons on the Main Menu                                                                                                                                                                           |
| **Show Value**                           | When enabled, parameters mapped to the knobs will be displayed on the screen while being modified                                                                                                                              |
| **Idle Mode**                            | Determines what is displayed when the display goes idle (5 seconds):<br> **OFF**<br>**ANIMATION**: display's the active Generator's animation<br> **PARAM**: displays a list of the parameters currently mapped to the 4 knobs |
| **Idle Time**                            | Sets the amount of time before the display goes idle                                                                                                                                                                           |
| **Screensaver Period (```Screensavr```)** | Sets the amount of time before the screensaver is activated                                                                                                                                                                    |
| **Brightness**                           | Sets the display's brightness level                                                                                                                                                                                            |


### MIDI

| **Setting**                           | **Description**                                     |
|---------------------------------------|-----------------------------------------------------|
| MIDI CC Rx                            | Enables or disables MIDI CC input                   | 
| MIDI Thru                             | Enables or disables Soft MIDI Thru                  | 

!!! attention
    When using the MIDI Thru feature, make sure to check your MIDI routing to avoid MIDI feedback loops.

### CV OUT

This sub-menu contains parameters available for the CV outputs.

**Modes:**

- **CV 1-2**: converts MIDI notes from the CV Out 1 and 2 aux tracks to 1V/OCT signals.

- **4xTrig**: converts selected MIDI notes (based on parameters Note Trg 1-4) to 4 gate outputs. This mode is designed to be used with drum / percussive generators such as [DrumGen](generators.md#drumgen) and [Samba](generators.md#samba).

!!! note ""

    Keep in mind that these are still experimental settings.

| **Parameter**                   | **Description**                                      |
|---------------------------------|------------------------------------------------------|
| **Mode**                             | Set the mode for the CV outputs (CV 1-2 / 4xTrig) |
| **Octave**                        | Set the base octave for the CV output (CV 1-2 mode) |
| **Note Trg 1-4**                         | Select a MIDI note to be converted to a gate signal (4xTrig mode) |


### AUTO VARIATE (```AUTO VARI8```)

The Auto Variate feature in NGEN is designed to automatically generate sequence variations for enabled tracks after a certain number of bars. 
This feature works on a per-track basis and can be enabled or disabled for each track via the Auto Vari8 toggle available on the Track sub-menu.

When enabled, the Auto Variate feature will generate a new sequence variation for the track after a certain number of bars. The probability of the variation being generated can be set via the ```PROB``` parameter, and the amount of variation can be set via the ```VARIATION``` parameter.

Auto Variate settings are global and affect all tracks that have the feature enabled.


| **Parameter**                   | **Description**                                      |
|---------------------------------|------------------------------------------------------|
| **Probability**    | The probability of the variation being generated     |
| **Length (Bars)**                        | The number of bars before a new variation is generated |
| **Variation Amount (```Amount```)** | The amount of variation to be generated              |

Auto Variate does not affect the following [Generators](generators.md): Input Sequencer, MIDI Player, and Thru Generators.



### Device

| **Setting**                             | **Description**                                            |
|-----------------------------------------|------------------------------------------------------------|
| **Save**                                | Saves the current settings to the device's internal memory |
| **Reboot**                              | Reboots the device                                         |
| **Factory Reset**                       | Resets the device to factory settings                      |
| **Firmware Upgrade (```FW Upgrade```)** | Upgrades the device's firmware                             |
| **User Manual**                         | Displays a QR code for the NGEN User Manual                |
| **Info**                                | Shows device information                                   |
