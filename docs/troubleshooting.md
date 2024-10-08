---
toc_depth: 3
---


# Troubleshooting 

This section contains step-by-step instructions on how to troubleshoot common issues related to NGEN.

---


## MIDI Connectivity

### NGEN is not sending / receiving MIDI

#### Step 1: Check your connections

- **USB**: Make sure to use USB data cable. Some USB cables are power-only and don't transmit any data via the USB.

- **3.5mm TRS MIDI I/O**: make sure to use Type-A adaptors for 1/8" TRS to MIDI DIN5.

#### Step 2: Check NGEN's MIDI input

- **MIDI Clock**: Check if your DAW (or other MIDI Clock source) is set to output MIDI Clock to NGEN (via USB or 3.5mm TRS) 

- **Free Clock**: Check if the Free Clock is Active

- From the Main Menu, go to Tools and open the **[MIDI Monitor](tools.md#midi-monitor-monitor) (```Monitor```)**. Check if NGEN is receiving Start, Stop and Tick messages.

#### Step 3: Check NGEN's tracks and generators

- From the Main Menu, go to the [Track](track.md) sub-menu and check if at least one of NGEN's tracks are **Active**. (Use  ++"TRACK | CLK"++ + ++"MENU ENCODER"++ to scroll through different tracks).

- If you're using a [**Generator**](generators.md) that includes a **Density** or **Probability** parameter, check if that parameter is not set to 0 (zero).

- If you're using a [**Generator**](generators.md) that requires an **external file** to operate (MIDI Player / NSL Engine), check if a file is currently loaded.

-  If you're using a [**Generator**](generators.md) that requires a **live input** (Polyform / Thru), check if the track is receiving MIDI on the selected MIDI input channel or from another track (via [Aux Out](tracks.md)).

#### Step 4: Check NGEN's MIDI output

- Use the **```Test MIDI```** feature available in [**Settings / MIDI**](settings.md#midi)

- Open the **MIDI Monitor** and press the ++"GENERATE"++ button to switch to the Output view. Check if NGEN is generating MIDI notes and what channels it's sending MIDI notes to (fourth / last column).

- Check if your destination (synthesizer, drum machine, or DAW instrument) is set to receive MIDI on the correct **MIDI channel**.

---

## microSD Card Storage

### microSD card not working

#### Step 1: Check the microSD

- Try a microSD with 32GB or less

- Format the microSD card as FAT32 / MBR

#### Step 2: Download Factory Content

- Download the NGEN factory content and copy to your microSD root (instructions available on the [File Management](filemanagement.md#factory-content) page)

#### Step 3: Check if NGEN can access the card

- When loading a file in NGEN (project, DrumGen template, etc), NGEN displays the location of the file on the right side of the display (```INTERNAL``` or ```MICROSD```). This can be used to check if NGEN has successfully identified the microSD card.

---

## CV Outputs

### NGEN not sending any CV

- From the Main Menu, navigate to [Settings / CV Out](settings.md#cv-out), 