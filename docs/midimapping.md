# MIDI Mapping

---

## About MIDI Mapping

Most of the settings, parameters, and actions available in NGEN can be controlled, modulated, and automated via MIDI CC. This lets you automate parameters during a live set or even use an external MIDI controller to access certain parameters directly.

MIDI CC messages are routed to [Tracks](track.md) according to their IN CH (MIDI Input Channel) settings. The values received are processed depending on the behaviour of the parameter / setting / action (check MIDI chart below).  
The different behaviours are:

- **Scaled:** values 0-127 are scaled to the parameter's minimum and maximum range.
- **Action:** values greater than zero trigger the action.
- **Absolute:** the value is used directly according to the range described (values outside of the described range are ignored). 

Because NGEN uses MIDI Channel 16 for global settings, tracks set to IN CH 16 will only receive MIDI notes.



<!-- **Settings and parameters** will convert the 0-127 range of MIDI CC messages to their respective minimum and maximum range.

**Actions** are triggered if a value greater than 0 (zero) is received. -->

---

## MIDI Chart

### GLOBAL SETTINGS

| **Feature**      |     **Parameter**     | **MIDI CC Number** |  **Behaviour**  |
|------------------|:---------------------:|:------------------:|:---------------:|
| **Scale**        |          Key          |         1          |     Scaled      |
|                  |         Scale         |         2          |     Scaled      |
| **MIDI Clock**   |        Status         |         10         |     Scaled      |
|                  |         Swing         |         11         |     Scaled      |
| **Free Clock**   |        Status         |         20         |     Scaled      |
|                  |       Generate        |         21         |     Scaled      |
|                  |          BPM          |         22         |     Scaled      |
|                  |        Length         |         23         |     Scaled      |
|                  |        Amount         |         24         |     Scaled      |
| **Bounce Clock** |        Status         |         30         |     Scaled      |
|                  |         Reset         |         31         |     Scaled      |
|                  |         Speed         |         32         |     Scaled      |
|                  |         Balls         |         33         |     Scaled      |
|                  |         Width         |         34         |     Scaled      |
|                  |        Height         |         35         |     Scaled      |
| **Perform**      |        Macro 1        |         40         |     Scaled      |
|                  |        Macro 2        |         41         |     Scaled      |
|                  |        Macro 3        |         42         |     Scaled      |
|                  |        Macro 4        |         43         |     Scaled      |
| **Patterns**     |    Load Pattern 1     |         50         |     Action      |
|                  |    Load Pattern 2     |         51         |     Action      |
|                  |    Load Pattern 3     |         52         |     Action      |
|                  |    Load Pattern 4     |         53         |     Action      |
|                  |    Load Pattern 5     |         54         |     Action      |
|                  |    Load Pattern 6     |         55         |     Action      |
|                  |    Load Pattern 7     |         56         |     Action      |
|                  |    Load Pattern 8     |         57         |     Action      |
|                  | Load Previous Pattern |         58         |     Action      |
|                  |   Load Next Pattern   |         59         |     Action      |
|                  |    Load Pattern #     |         60         | Absolute (1-8)  |
|                  |     Save Pattern      |         61         |     Action      |
| **Tracks**       | Select Previous Track |         70         |     Action      |
|                  |   Select Next Track   |         71         |     Action      |
|                  |    Select Track  #    |         72         | Absolute (1-16) |
| **Menu**         |  Open Track Settings  |         80         |     Actions     |
|                  |    Open Generator     |         81         |     Actions     |
|                  |     Open MIDI FX      |         82         |     Actions     |


### GENERATORS

#### ACDGEN

| **Parameter**   | **MIDI CC Number** | **Behaviour** |
|-----------------|:------------------:|:-------------:|
| Generate        |         1          |    Action     |
| Variate         |         2          |    Action     |
| Shift           |         3          |    Scaled     |
| Length          |         4          |    Scaled     |
| Density         |         5          |    Scaled     |
| Algorithm       |         6          |    Scaled     |
| KB Shift        |         7          |    Scaled     |
| Octave          |         8          |    Scaled     |
| Note Length     |         9          |    Scaled     |
| Random Velocity |         10         |    Scaled     |

#### ARPER

#### DRUMGEN

| **Parameter** | **MIDI CC Number** | **Behaviour** |
|---------------|:------------------:|:-------------:|
| Generate      |         1          |    Action     |
| Variate       |         2          |    Action     |
| Density 1     |         3          |    Scaled     |
| Density 2     |         4          |    Scaled     |
| Density 3     |         5          |    Scaled     |
| Density 4     |         6          |    Scaled     |
| Length 1      |         7          |    Scaled     |
| Length 2      |         8          |    Scaled     |
| Length 3      |         9          |    Scaled     |
| Length 4      |         10         |    Scaled     |
| Note 1        |         11         |    Scaled     |
| Note 2        |         12         |    Scaled     |
| Note 3        |         13         |    Scaled     |
| Note 4        |         14         |    Scaled     |

#### INPUT SEQUENCER

| **Parameter** | **MIDI CC Number** | **Behaviour** |
|---------------|:------------------:|:-------------:|
| Shift         |         3          |    Scaled     |
| Length        |         4          |    Scaled     |
| Probability   |         5          |    Scaled     |
| Quantize      |         6          |    Scaled     |

#### MARP

| **Parameter** | **MIDI CC Number** | **Behaviour** |
|---------------|:------------------:|:-------------:|
| Generate      |         1          |    Action     |
| Variate       |         2          |    Action     |
| Shift         |         3          |    Scaled     |
| Length        |         4          |    Scaled     |
| Density       |         5          |    Scaled     |
| Offset        |         6          |    Scaled     |
| Length 1      |         7          |    Scaled     |
| Length 2      |         8          |    Scaled     |
| Length 3      |         9          |    Scaled     |
| Length 4      |         10         |    Scaled     |

#### MIDI PLAYER

#### POLYFORM

| **Parameter**     | **MIDI CC Number** | **Behaviour** |
|-------------------|:------------------:|:-------------:|
| Generate          |         1          |    Action     |
| Variate           |         2          |    Action     |
| Shift             |         3          |    Scaled     |
| Length            |         4          |    Scaled     |
| Density           |         5          |    Scaled     |
| Delay             |         6          |    Scaled     |
| Pitch Probability |         7          |    Scaled     |
| Gate Probability  |         8          |    Scaled     |
| Chord Probability |         9          |    Scaled     |
| Random Velocity   |         10         |    Scaled     |

#### POP

| **Parameter**         | **MIDI CC Number** | **Behaviour** |
|-----------------------|:------------------:|:-------------:|
| Generate              |         1          |    Action     |
| Shift                 |         3          |    Scaled     |
| Length                |         4          |    Scaled     |
| Density               |         5          |    Scaled     |
| Velocity              |         6          |    Scaled     |
| Type Probability      |         7          |    Scaled     |
| Chord Length          |         8          |    Scaled     |
| Inversion Probability |         9          |    Scaled     |
| Balance               |         10         |    Scaled     |
| Mode                  |         11         |    Scaled     |

#### SAMBA

| **Parameter** | **MIDI CC Number** | **Behaviour** |
|---------------|:------------------:|:-------------:|
| Generate      |         1          |    Action     |
| Spread        |         3          |    Scaled     |
| Length        |         4          |    Scaled     |
| Density       |         5          |    Scaled     |
| Random        |         6          |    Scaled     |
| Rotate        |         7          |    Scaled     |
| Probability   |         8          |    Scaled     |

#### SHUFFLER

| **Parameter**      | **MIDI CC Number** | **Behaviour** |
|--------------------|:------------------:|:-------------:|
| Generate           |         1          |    Action     |
| Variate            |         2          |    Action     |
| Repeats            |         3          |    Scaled     |
| Length             |         4          |    Scaled     |
| Density            |         5          |    Scaled     |
| Mode               |         6          |    Scaled     |
| Note Length        |         7          |    Scaled     |
| Random Probability |         8          |    Scaled     |
| Quantize           |         9          |    Scaled     |
| Start              |         10         |    Scaled     |

#### THRU

| **Parameter**   | **MIDI CC Number** | **Behaviour** |
|-----------------|:------------------:|:-------------:|
| Shift           |         3          |    Scaled     |
| Max Velocity    |         4          |    Scaled     |
| Probability     |         5          |    Scaled     |
| Random Velocity |         6          |    Scaled     |
| Quantize        |         7          |    Scaled     |

#### TURING

| **Parameter** | **MIDI CC Number** | **Behaviour** |
|---------------|:------------------:|:-------------:|
| Write         |         1          |    Action     |
| Clear         |         2          |    Action     |
| Shift         |         3          |    Scaled     |
| Length        |         4          |    Scaled     |
| Probability   |         5          |    Scaled     |
| Loop          |         6          |    Scaled     |
| Octave        |         7          |    Scaled     |
| Spread        |         8          |    Scaled     |
| Range         |         9          |    Scaled     |
| Voices        |         10         |    Scaled     |

### MIDI FXS