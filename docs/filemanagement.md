# File Management

---

## About File Management:

NGEN can use external files to store and load data for [Projects](projects.md), [MIDI files](generators.md#midi-player), [DrumGen templates](generators.md#drumgen), and [NSL scripts](nsl.md).
These files can be either be stored in the microSD card or in NGEN's internal memory.

During it's boot process, NGEN checks if a microSD card is inserted. If no microSD card is inserted, NGEN will use its internal memory instead.

NGEN currently doens't offer a way of transferring files between its internal memory and the microSD card (coming soon).

## List of File Types:

|  **File Type**   |                    **Description**                     | **Sub-Folder | **Extension** |
|:----------------:|:------------------------------------------------------:|:------------:|:-------------:|
|   NGEN Project   |        Stores data for [Projects](projects.md)         |   / (Root)   |     .HEX      |
|    MIDI File     | MIDI files to be played by the MIDI Player generator.  |    /MIDI     |     .MID      |
| DrumGen Template | DrumGen templates to be used by the DrumGen generator. |   /DRUMGEN   |     .HEX      |
|    NSL Script    |      NSL scripts to be used by the NSL generator.      |     /NSL     |     .NSL      |
