# File Management

---

## About File Management

NGEN can use external files to store and load data for [Projects](projects.md), [MIDI files](generators.md#midi-player), [DrumGen templates](generators.md#drumgen), and [NSL scripts](nsl.md).
These files can be either be stored in the microSD card or in NGEN's internal memory.

During it's boot process, NGEN checks if a microSD card is inserted. If no microSD card is inserted, NGEN will use its internal memory instead.


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


<div class="forced-pb"></div>

## List of File Types

|  **File Type**   |                    **Description**                     | **Sub-Folder** | **Extension** |
|:----------------:|:------------------------------------------------------:|:------------:|:-------------:|
|   NGEN Project   |        Stores data for [Projects](projects.md)         |   / (Root)   |     .HEX      |
|    MIDI File     | MIDI files to be played by the MIDI Player generator.  |    /MIDI     |     .MID      |
| DrumGen Template | DrumGen templates to be used by the DrumGen generator. |   /DRUMGEN   |     .HEX      |
|    NSL Script    |      NSL scripts to be used by the NSL generator.      |     /NSL     |     .NSL      |

## Storage File Tree

The file tree for the microSD card should match the following:

```
/DRUMGEN (folder)
    /HOUSE.HEX (template)
    /DNB.HEX
    /ELECTRO.HEX
    ...
/MIDI (folder)
    /CHORDS.MID (midi file)
    ...
/NSL (folder)
    /EBASS.HEX (nsl script)
    ...
FILE_01.HEX (project)
FILE_02.HEX (project)
FILE_03.HEX (project)
...
```

---

## File / List Selector

NGEN uses a custom file / list selection screen to let users select and load different files such as projects and templates.

The list is automatically populated with the files available in the active storage (internal or microSD) according to the relevant sub-folder (see table above) and can be navigated using the ++"MENU ENCODER"++.

To select an option from the list, click the ++"MENU ENCODER"++.

Additional options can be accessed by pressing ++"FUNCTION"++ + ++"MENU ENCODER"++.

The right side of the display indicates the location of file and the number of files available at the bottom right corner. 


---

## File Copying

To copy files between different storage locations (internal x microSD):

1. Select the source storage location via the [Storage parameter (Settings / General)](settings.md#general).

2. Open the file selector according to the file type:

    1. **Projects:** Navigate to ```Projects``` / ```Load```

    2. **DrumGen Templates:** Load [DrumGen generator](generators.md#drumgen) and nagivate to ```Generator``` / ```Template```

    3. **MIDI Files:** Load [MIDI Player generator](generators.md#midi-player) and nagivate to ```Generator``` / ```Load File```

    4. **NSL Engine Scripts:** Load [NSL generator](generators.md#drumgen) and nagivate to ```Generator``` / ```Load```
  
3. Scroll to the file to be copied using the ++"MENU ENCODER (Scroll)"++

4. Press ++"FUNCTION"++ + ++"MENU ENCODER"++ to the open additional options.

5. Select the ```Copy To [...]``` option