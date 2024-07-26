# Patterns

---

## About Patterns

![](images/NGEN_PatternSelector_v2.jpeg){align=right}

The pattern system in NGEN is designed to let users create and perform different sections of a song/project. 
Patterns can store and recall settings for all tracks (including their Generators and MIDI FX). Global and clock settings are only stored in [**Projects**](projects.md). 

Each [Project](projects.md) contains 8 pattern slots that can be saved, copied, pasted, and deleted from the Pattern Selector menu (accessible via the **PATTERN** button).

The **Pattern Selector** displays the active pattern on the left (```ACTIVE```), the selected pattern on the center (```NEXT```) and the [Generator](generators.md) and [MIDI FX](midifx.md) selected for the first 3 active tracks.

---

## Loading / Queuing Patterns

NGEN offer 3 methods for loading / queuing patterns:

1 - Press the ++"PATTERN"++ button to open the Pattern Selector, select the pattern using the ++"MENU ENCODER"++ and click on the encoder to load.

2 - Turn the ++"MENU ENCODER"++ while holding down the ++"PATTERN"++ button to select a pattern, release the button to load the selected pattern.

3 - Use the shortcuts ++"PATTERN"++ + ++"GENERATE"++ to load the next pattern in the sequence or ++"PATTERN"++ + ++"FUNCTION"++ + ++"GENERATE"++ to load the previous pattern in the sequence.

Patterns are queued and loaded at the beginning of the next bar if NGEN is playing or immediately if NGEN is stopped.

---

## Saving Patterns

The changes you make in NGEN are not automatically saved to the current pattern to avoid accidental overwriting of patterns.

To save the current pattern to one of the available slots, follow these steps:

1 - Open the Pattern Selector by pressing the ++"PATTERN"++ button.

2 - Select which pattern slot you'd like to save the current pattern to by turning the ++"MENU ENCODER"++.

3 - Open the Pattern Edit menu by holding down the ++"FUNCTION"++ button and pressing the ++"PATTERN"++ button.

4 - Select the ```Save``` option to save the current pattern to the selected slot.

It's also possible to use the shortcut ++"PATTERN"++ + ++"MENU ENCODER"++ to save the current pattern to the selected slot while in the Pattern Selector.

---

## Pattern Generation

![](images/NGEN_PatternGeneration.jpeg){align=right}

NGEN includes a new Pattern Generation feature that lets users generate an entire pattern at once by holding down ++"TRACK | CLK"++ and pressing the ++"GENERATE"++ button.
This shortcut will generate new sequences for all active tracks.

If the [Randomize State setting](settings.md#general) is enabled, NGEN will also assign random states to all tracks when generating a new pattern.  
For more information about track states, check out the [Track States](track.md#track-states) section in the Track documentation.

It's also possible to generate variations of the current pattern by holding down ++"TRACK | CLK"++ + ++"FUNCTION"++ and pressing the ++"GENERATE"++ button.

<br>
<br>
<br>

---

## Pattern Menu

![](images/NGEN_PatternEdit.jpeg){align=right}

The pattern edit menu can be accessed by holding down the ++"FUNCTION"++ button and pressing the ++"PATTERN"++ button (accessible from the Main Menu or from the Pattern Selector).

The menu includes options for saving, copying, pasting, and deleting the selected pattern.


<br>
<br>
<br>

---

## Generate All / Variate All

![](images/NGEN_PatternGenerateAll.jpeg){align=right}

The last 2 options in the Pattern menu are **Generate All** and **Variate All**. These options let you explore NGEN's algorithmic pattern generation capabilities by generating or variating all patterns at once starting from the selected pattern.  
These features can be used to create all 8 patterns in a project at once or to fill subsequent empty patterns.

**Generate All** generates 8 unique patterns and automatically saves them to the current project.

**Variate All** generates 8 variations of the current pattern and automatically saves them to the current project.

!!! warning
    Generate All and Variate All won't affect / overwrite already saved patterns. If you'd like to overwrite a pattern, make sure to delete it first.


<br>
<br>
<br>

---

## Pattern Reloading

![](images/NGEN_PatternReloading.jpeg){align=right}

NGEN includes a new feature that lets users quickly reload the active pattern from it's last saved state by holding down  ++"PATTERN"++ and pressing the ++"RETURN"++ button.

This feature is useful for quickly reloading an entire pattern after making changes to it during a live performance.

<br>
<br>
<br>

---

## Workflow Suggestion

The pattern system can be used to create, store and load different variations based on the initial pattern.

After creating your first pattern, return to the Main Menu and save it as pattern one.  
You can then create different variations by tweaking the different parameters and generating new sequences. To save each variation, load an empty pattern and save the current variation to it.





