# NSL - NGEN SCRIPTING LANGUAGE

The NSL Engine [Generator](generators.md#nsl) is a powerful tool that lets you create your own custom algorithms using a simple scripting language.

At it's core, the NSL Engine features a 32-step sequence (with individual pitch, velocity, length (in beats) and density per step) and standard parameters such Shift, Length and Density to control playback.

Instead of using a pre-defined algorithm to fill the 32-step sequence, the NSL Engine lets you load a script to generate it using your own custom algorithm. 

Each NSL script consists of a series of hex values that are parsed into commands and values. Hex values above 160 (0xA0) trigger new commands and values below 160 are assigned as values / parameters for these commands.
The engine also includes 32 registers (Memory Buffer) that can be used to store values and use them later in the script and 4 generic parameters (Param 1-4) with ranges from 0-100.


!!! warning
    The NSL Engine is still in beta and it's not fully documented and implemented yet. This section of the manual will be updated as we continue to develop the NSL Engine.
    Faulty scripts can cause the NSL Engine to crash and require a reboot.

---

## ngen_nsl Rust Library

[ngen_nsl](https://github.com/spektroaudio/ngen_nsl) is a custom Rust library available via [cargo / crates.io](https://crates.io/crates/ngen_nsl) that make it easier to create and parse NSL scripts for the NSL Engine.

To add it to your Rust project, run the command ```cargo add ngen_nsl``` in your project's directory.

Documentation for ngen_nsl is available at [https://docs.rs/ngen_nsl](https://docs.rs/ngen_nsl).

---

## NSL Programming Reference

### Parameter Types

NSL commands require set of different parameters to execute correctly and each parameter's value is used according to the list below:


#### VALUE

The VALUE parameter type returns a constant values from ```0x00``` to ```0x7F``` (0-127) and values stored in the NSL Engine's memory buffer from ```0x80``` to ```0x9F``` (128-159). 
    

#### DESTINATION / SOURCE

The DESTINATION / SOURCE parameters consists of 2 x ```VALUE``` parameters that are used in pair to retrieve values from different parts and features of the NSL Engine.

SOURCE parameters are used to retrieve data while DESTINATION parameters are used to set data.

The first ```VALUE``` in the pair (aka ```VALUE 1```) is used to indicate the type / location of the value that follows it (```VALUE 2```) according to the table below:

|**PART / FEATURE**|**VALUE 1 (Address)**| **VALUE 2 (Value / Index)** |**VALUE 2 RANGE**|**SOURCE**|**DESTINATION**|**DESTINATION RANGE**|
|:--------------------:|:-----------------------:|:-------------------------------:|:-------------------:|:------------:|:-----------------:|:-----------------------:|
|**Constant Value**|          0x00           |              Value              |        0-127        |      ✔︎      |         ✕         |           N/A           |
| **Random Value** |          0x01           |          Random Range           |        0-127        |      ✔︎      |         ✕         |           N/A           |
|  **Step Pitch**  |          0x02           |   Step Number (Zero-Indexed)    |        0-31         |      ✔︎      |        ✔︎         |   0-127 (MIDI PITCH)    |
|**Step Velocity** |          0x03           |   Step Number (Zero-Indexed)    |        0-31         |      ✔︎      |        ✔︎         |  0-127 (MIDI VELOCITY)  |
| **Step Length**  |          0x04           |   Step Number (Zero-Indexed)    |        0-31         |      ✔︎      |        ✔︎         |      0-32 (BEATS)       |
| **Step Density** |          0x05           |   Step Number (Zero-Indexed)    |        0-31         |      ✔︎      |        ✔︎         |          0-49           |
|**Memory Buffer** |          0x06           |   Step Number (Zero-Indexed)    |        0-31         |      ✔︎      |        ✔︎         |          0-255          |
|  **Params 1-4**  |          0x07           | Parameter Number (Zero-Indexed) |         0-3         |      ✔︎      |        ✔︎         |          0-100          |
|    **Scale**     |          0x08           |     Note position in scale      |        0-127         |      ✔︎      |         ✕         |           N/A           |
|    **Scale (Quantized)**     |          0x09           |     Note position in scale      |        0-127         |      ✔︎      |         ✕         |           N/A           |


Some features such as Constant and Random use the second ```VALUE``` in the pair (```VALUE 2```) as the actual value while the other types use it as an index to indicate the location of the value in the NSL Engine's memory.

Examples:

- ```0x00 0x05``` : Returns a constant value (```ORIGIN``` = ```0x00```) of 5 (```VALUE``` = ```0x05```).
- ```0x02 0x10``` : Returns the step pitch (```ORIGIN``` = ```0x02```) at index 16 (```VALUE``` = ```0x10```).
- ```0x07 0x20``` : Returns a random value (```ORIGIN``` = ```0x07```) between 0 and 32 (VALUE = ```0x20```).


#### INT16

The INT16 parameter type uses a pair (x and y) of 8-bit values (0-255) to create a 16-bit value (0-65535) by shifting the first value 8 bits to the left and adding the second value to it (```(x << 8) + y```).

---

### List of Commands

#### **```0xA1``` SET** 

**Description:** Sets the value of a destination to the value of a source.  

**Parameters:** ```DESTINATION``` ```SOURCE```

**Examples:** 

- ```0xA1 0x02 0x00 0x01 0x10``` : Sets the pitch of step 1 to a random value between 0 and 16.

- ```0xA1 0x03 0x00 0x03 0x01``` : Sets the velocity of step 1 to the velocity of step 1.

- ```0xA1 0x06 0x00 0x05 0x04``` : Sets the value of the memory buffer at index 0 to the density of step 5.

#### **```0xB0``` ADD**

**Description:** Adds the value of a source to a destionation.

**Parameters:** ```DESTINATION``` ```SOURCE``` 

**Examples:**

- ```0xB0 0x02 0x00 0x00 0x2``` : Add 2 (```0x00 0x02```) to the pitch of the first step (```0x02 0x00```).

#### **```0xB1``` SUBTRACT**

**Description:** Subtracts the value of a source from a destination.

**Parameters:** ```DESTINATION``` ```SOURCE```

**Examples:**

- ```0xB1 0x02 0x00 0x01 0x10``` : Subtract a random value between 0 - 16 (```0x01 0x10```) from the pitch of the first step (```0x02 0x00```).

#### **```0xC0``` LOOP SET**

**Description:** Enables looping and set the loop count to the value of a source.

**Parameters:** ```SOURCE``` (Loop Count)

**Examples:**

- ```0xC0 0x00 0x03``` : Enables looping and set the loop count to 3.

#### **```0xC1``` LOOP END**

**Description:** Ends the current loop.

**Parameters:** None

#### **```0xC2``` JUMP**

**Description:** Jumps to a specific position in the program.

**Parameters:** ```INT16``` (Jump Position)

**Examples:**

- ```0xC2 0x02 0x24``` : Jumps to position 548.

#### **```0xFF``` END**

**Description:** Ends the program.

**Parameters:** None


[ MORE INFORMATION COMING SOON ]