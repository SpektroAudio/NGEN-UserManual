# File Management

---

## About File Management

NGEN can use external files to store and load data for [Projects](projects.md), [MIDI files](generators.md#midi-player), [DrumGen templates](generators.md#drumgen), and [NSL scripts](nsl.md).
These files can be either be stored in the microSD card or in NGEN's internal memory.

During it's boot process, NGEN checks if a microSD card is inserted. If no microSD card is inserted, NGEN will use its internal memory instead.

NGEN currently doens't offer a way of transferring files between its internal memory and the microSD card (coming soon).

## Using NGEN with a microSD card

We recommend using microSD cards with a capacity of 32GB or less, formatted as FAT32.

Before inserting a microSD card into NGEN, we recommend that you copy the Factory Content to the microSD card in order to have the necessary folders for MIDI files, DrumGen templates, and NSL scripts.

## Factory Content

The Factory Content for NGEN (including MIDI files, DrumGen templates, and NSL scripts) is available on the [NGEN Resources repository on Github](https://github.com/SpektroAudio/NGEN-Resources/).

If you'd like to download or update the Factory Content, follow these steps:

1 - Download a copy of the Factory Content [available on the NGEN repository on Github](https://github.com/SpektroAudio/NGEN-Resources/archive/refs/heads/main.zip).

2 - Navigate into the Factory Content folder and copy the contents to the root of your microSD card.

!!! attention
    It's currently not possible to copy new files into NGEN's internal memory. If you'd like to use new files available in the Factory Content, you'll need to use a microSD card.

## List of File Types

|  **File Type**   |                    **Description**                     | **Sub-Folder** | **Extension** |
|:----------------:|:------------------------------------------------------:|:------------:|:-------------:|
|   NGEN Project   |        Stores data for [Projects](projects.md)         |   / (Root)   |     .HEX      |
|    MIDI File     | MIDI files to be played by the MIDI Player generator.  |    /MIDI     |     .MID      |
| DrumGen Template | DrumGen templates to be used by the DrumGen generator. |   /DRUMGEN   |     .HEX      |
|    NSL Script    |      NSL scripts to be used by the NSL generator.      |     /NSL     |     .NSL      |
