# Tools

--- 

## About Tools

NGEN also includes some extra tools that can be used to improve your workflow.

---

## List of Available Tools

### MIDI MONITOR (```MONITOR```)

![](images/NGEN_MIDIMonitor.gif){align=right}
The built-in MIDI Monitor lets you track incoming and outgoing MIDI messages.
It can be used to make sure that NGEN is receiving MIDI clock, notes, and control changes from other devices and that it's also sending MIDI messages appropriately.

The four columns in the MIDI Monitor represent message type, number (note or CC number), value, and channel.

To switch between ```IN``` and ```OUT```, press the ++"GENERATE"++ button.


### CV OUT

This sub-menu contains some parameters available for the CV outputs.

!!! note ""

    Keep in mind that these are still experimental settings.

| **Parameter**                   | **Description**                                      |
|---------------------------------|------------------------------------------------------|
| **Out 1 Oct**                        | Set the base octave for the CV 1 output |
| **Out 2 Oct**                        | Set the base octave for the CV 2 output |


### AUTO VARIATE (```AUTO VARI8```)

The Auto Variate feature in NGEN is designed to automatically generate sequence variations for enabled tracks after a certain number of bars. 

| **Parameter**                   | **Description**                                      |
|---------------------------------|------------------------------------------------------|
| **Bars**                        | The number of bars before the variation is generated |
| **Probability (```PROB```)**    | The probability of the variation being generated     |
| **Variation (```VARIATION```)** | The amount of variation to be generated              |

Auto Variate does not affect the following [Generators](generators.md): Input Sequencer, MIDI Player, and Thru Generators.