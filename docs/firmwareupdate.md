# Firmware Update

---

## How to update the NGEN firmware

To update the firmware on your NGEN, you'll need to download the latest firmware version from the links below and follow the instructions for your hardware version.

If you have any questions or need help updating your NGEN, don't hesitate to get in touch with us via the [Contact page on our website](https://spektroaudio.com/contact).

### NGEN HW V1.1 and newer (Batch #2 and newer / USB-C)

1 - [Download the latest version of the NGEN firmware for HW v1.1](http://files.spektroaudio.com/ngen/firmware/NGEN_FWUpdate_v13_hw11.zip).

2 - Connect NGEN to your computer via USB.

3- Navigate to the [Settings](settings.md) page and select the "FW Update" option.

4 - NGEN should now appear as a USB flash drive on your computer.

5 - Drag the latest version of the firmware (.uf2) to the NGEN's USB flash drive.

6 - NGEN should automatically apply the update and restart after it's finished.

7 - After rebooting, apply a Factory Reset (files will not be deleted).

??? "Firmware Archive for NGEN HW v1.1+"       
      - [1.2 Update for NGEN HW v1.1](http://files.spektroaudio.com/ngen/firmware/NGEN_FWUpdate_v12_hw11.zip)
      - [1.1.2 Update for NGEN HW v1.1](http://files.spektroaudio.com/ngen/firmware/NGEN_FWUpdate_v112_hw11.zip)

??? "Alternative Flashing Method"
        NGEN HW v1.1 also features a backup method for updating the firmware that can be used in case of issues with the primary method or failed updates.

        This method does require some minor disassembling so we only recommend using it as a backup.

        1 - Remove the 4 screws on the side of the unit and the microSD card if present.

        2 - Detach the bottom panel of the case. It should come off without removing any knobs or screws from the top panel.

        3 - Locate the BOOT button on the back side of the PCB (visible). It should be located on the center of the PCB.

        4 - Connect the unit via USB while holding down the BOOT button.

        5 - NGEN should mount as a USB drive on your computer. Once mounted, release the BOOT button.

        6 - Follow steps 5-7 of the primary method to update the firmware.

        7 - Disconnect the USB and re-assemble the case.


###  NGEN HW v1.0 (Batch #1 / Micro USB / Serial #0001 - 0020)

1 - [Download the latest version of the NGEN firmware for HW v1.0](http://files.spektroaudio.com/ngen/firmware/NGEN_FWUpdate_v13_hw10.zip)

2 - Download and install TyTools: [https://github.com/Koromix/tytools/releases/](https://github.com/Koromix/tytools/releases/)

3 - Connect the NGEN to your computer via USB

4 - Open the TyUploader application

5 - Select the NGEN from the drop-down menu and click on the Upload button

6 - Select the firmware file (.hex extension)

TyUploader will then upload then new firmware to your NGEN units and restart it after it's finished. 

We highly recommend that you perform a Factory Reset (available in Settings) after updating.

!!! warning "Attention"
        If TyUploader is not recognizing NGEN, try a different USB cable. Some USB cables are power-only and will not transmit data between your computer and NGEN.  
        If you have any problems updating your unit, don't hesitate to get in touch with us via the Contact page on our website.

??? "Firmware Archive for NGEN HW v1.0"       
      - [1.2 Update for NGEN HW v1.0](http://files.spektroaudio.com/ngen/firmware/NGEN_FWUpdate_v12_hw10.zip)
      - [1.1.2 Update for NGEN HW v1.0](http://files.spektroaudio.com/ngen/firmware/NGEN_FWUpdate_v112_hw10.zip)


---

## Change-Log

---

### Version 1.3

#### Added 
- **New Song Mode (under [Tools](tools.md))**
- [FILE MANAGEMENT](filemanagement.md): Added support for file transfer via serial.
- [FILE MANAGEMENT](filemanagement.md): New file operations (load / copy to microSD or Internal Memory / delete) while in file selector (Function + Menu Encoder).
- [NSL](generators.md#nsl-engine) Added new Animation.
- [MENU SYSTEM](menunavigation.md#menu-navigation): Added support for menu transitions / visual effects.
- [MENU SYSTEM](menunavigation.md#menu-navigation): New glitch transition UI VFX when entering Idle Mode.
- [STRUM](midifx.md#strum) Added MIDI mapping for Velocity and Random.
- [POP](generators.md#pop): Added new Expression parameter.
- [POP](generators.md#pop): Added new "DUAL ESEQ" mode.
- [SCALE](scale.md): Added support for chord expressions to the Chord builder framework.
- [SETTINGS](settings.md#midi): Added "Test MIDI Out".
- [SETTINGS](settings.md#cv-out): Added "Test CV Out".
- [SETTINGS](settings.md#display): New setting (```UI Visual FX```) for enabling / disabling UI Visual Effects.
- [SETTINGS](settings.md#general): New setting (```Storage```) for switching between internal and microSD storage (HW v1.1 or newer).
- [SHAPER](midifx.md#shaper): Added missing MIDI Mapping for parameters.
- [SHORTCUT](menunavigation.md#shortcuts): New Active (track mute) shortcut from Track Selector (Function + Menu Encoder).
- [TRACK](track.md): New Clear option in the Track Edit sub-menu.
- [TRACK](track.md): New Clock Source selector in the Track sub-menu.

#### Improved 
- [ACDGEN](generators.md#acdgen): Reduced memory usage (saving and loading ~30% faster).
- [FREE CLOCK](clockgen.md#free-clock): Improved animation.
- [FREE CLOCK](clockgen.md#free-clock): Improved BPM accuracy.
- [MIDI CLOCK](clockgen.md#midi-clock): Improved sync accuracy and stability.
- [MIDI FX](midifx.md): Improved chord handling
- [PATTERNS](pattern.md): Improved pattern switching
- [POP](generators.md#pop): Optimized data model and memory usage
- [POP](generators.md#pop): Increase Octave parameter range
- [PROJECTS](projects.md): Improved support for backwards compatibility 
- [SAMBA](generators.md#samba): Note Len mapped to FN + Param 2
- [SCALE](scale.md): Octave mapped to Param 3
- [SHAPER](midifx.md#shaper): Mode mapped to FN + Param 1, Length Multiplier mapped to FN + Param 2, Map Pitch mapped to FN + Param 3
- [STRUM](midifx.md#strum) Max Delay re-mapped to Param 1, Velocity Multiplier mapped to Param 2, Random mapped to Param 3
- [THRU](generators.md#thru): Add MIDI mappings for Delay and Quantize
- [THRU](generators.md#thru): Delay parameter mapped to FN + Param 4
- Improved handling of larger files
- Updated CV out implementation
- Animation now updates correctly while all clocks are stopped

#### Fixed 
- [ACDGEN](generators.md#acdgen): Fixed glitched line on the top-left corner of the display during animation
- [ACDGEN](generators.md#acdgen): First note is now properly draw during animation
- [ACDGEN](generators.md#acdgen): Fixed a bug that caused the first note of the sequence to not be rendered correctly
- [MIDI MAPPINGS](midimapping.md): Fixed MIDI Mappings for Track Selection and Perform Macros
- [PATTERNS](pattern.md): The pattern edit modal (++"FUNCTION"++ + ++"PATTERN"++) can now only be opened from the pattern selector.
- [PATTERNS](pattern.md): Pattern Edit modal now properly returns to the Pattern sub-menu
- [PROJECTS](projects.md): Creating a new project now disables all tracks except for Track 1
- [SCALE](scale.md): Scale Editor now works correctly when Key is other than C.
- [SHAPER](midifx.md#shaper): Pitch min/max values not visible when using parameter knob
- [TRACK](track.md): Fixed Track Reloading in empty patterns
- [TRACK](track.md): Track Edit modal now properly returns to the to Track sub-menu
- Exiting Track selection (via the Return button) now properly returns to the previously active track
- NGEN now properly re-activates the Idle Mode after a Parameter knob pick-up.


### Version 1.2

#### Added 

- New internal framework for better threading / multicore processing (HW 1.1).
- New internal framework for generating and manipulating chords.
- New internal framework for managing available chords based on the active [Key / Scale](scale.md) (for polyphonic Generators).
- [MENU SYSTEM](menunavigation.md): Added fast scrolling for List Selector (Function + Menu Encoder).
- [MENU SYSTEM](menunavigation.md): The list selector now sorts items alphabetically.
- [PROJECTS](projects.md): Added "New" option under Projects.
- [PROJECTS](projects.md): Project changes are now quantized to 1 bar (while NGEN is playing).
- [SETTINGS](settings.md): Added viewable QR code for User Manual.
- [SETTINGS](settings.md): Added new MIDI Thru setting.

#### Improvements 
- Improved display response.
- Improved Param 1-4 response on all hardware versions.
- [DRUMGEN](generators.md#drumgen): Improved Random.
- [MENU SYSTEM](menunavigation.md): Track number indicator now displays active status of the selected track.
- [MENU SYSTEM](menunavigation.md): Improved rendering of OS notifications.
- [MENU SYSTEM](menunavigation.md): Improved display refresh rate when showing parameter values during animations.
- [MENU SYSTEM](menunavigation.md): The confirmation dialog now shows the active project name when saving projects.
- [PERFORM](perform.md): Macro mapping will now only get cancelled from the Main Menu (Return button).
- [POP](generators.md#pop): Integrated support for the new chord frameworks.
- [POP](generators.md#pop): Improved state randomization.
- [PROJECTS](projects.md): Updated project file format to include support for upcoming features.
- [PROJECTS](projects.md): Reduced glitches and stutters when processing projects (saving / loading / deleting) during playback (using the new threading framework).
- [PROJECTS](projects.md): Improve support for loading projects saved with previous firmware versions (projects are now automatically updated to the new format).
- [TRACK](track.md): Disabled tracks are now properly restored when loading patterns / projects.
- [TRACK](track.md): Tracks will now send MIDI note-offs for all active notes when disabled.
- Update display transmission for HW v1.1.
- General performance improvements and optimizations.

#### Fixes 
- [DRUMGEN](generators.md#drumgen): Templates are now properly reloaded when loading projects / patterns.
- [GENERATORS](generators.md): Param 1-4 are now properly mapped when selecting a new Generator from the Track sub-menu.
- [GLITCH](midifx.md#glitch): Fixed bug that caused the Glitch MFX to output MIDI notes to incorrect MIDI channels.
- [MENU SYSTEM](menunavigation.md): Fixed a bug that caused the hardware controls to stop working when entering Track or Pattern selection immediately after a notification.
- [MENU SYSTEM](menunavigation.md): The Param List Idle Mode now renders correctly when entering Idle Mode.
- [FREE CLOCK](clockgen.md#free-clock): Fixed bug that caused Free Clock to drop MIDI notes.
- [PERFORM](perform.md): Macro 5-8 control via Function + Param 1-4 now work correctly.
- [SCALE](scale.md): Key and Scale can now be properly controlled via Param 1 and 2 while in the Scale sub-menu.
- [PROJECTS](projects.md): Project > Save now properly overwrites the currently active project.


### Version 1.1.2

#### Added

- Updated internal framework for apps / tools that require custom UI / controls.
- New list selector based on the updated framework.
- [PERFORM](perform.md): Added option for removing a mapping.
- [MENU SYSTEM](menunavigation.md): Added new confirmation modal for important actions.
- [SCALE](scale.md): Added new Scale Editor (beta).

#### Improvements
- Improved potentiometer readings for better accuracy and smoother operation.
- Improved list scrolling / selection.
- Upgraded the Name Editor to new framework.
- Upgraded the Info view to new framework.
- [SETTINGS](settings.md): Renamed "Restart" to "Reboot".
- [MENU SYSTEM](menunavigation.md): Improved navigation during Idle Mode.
- [PROJECTS](projects.md): Improved project management for forward and backwards compatibility.

#### Fixes
- NGEN can now output to MIDI Channel #16 correctly
- The MIDI channel of incoming MIDI notes via 3.5mm MIDI IN is now properly detected.
- [SETTINGS](settings.md): MIDI CC RX now properly saves and loads.
- [MENU SYSTEM](menunavigation.md): When receiving MIDI CC values, the UI now updates to display the correct values.
- [PATTERNS](pattern.md): NGEN no longer re-loads the previous pattern when saving a new one.
- [POP](generators.md#pop): Balance parameter now works correctly.
- [THRU](generators.md#thru): Delay now works after loading a pattern / project.

### Version 1.1.1

#### Added

- [CV OUT](setup.md#connecting-via-cv): Added new 4xTrig mode and Trigger 1-4 parameters.
- The [MENU SYSTEM](menunavigation.md) now retains the position of each menu during navigation.
- AutoVari8 and CV Out settings are now stored as global settings on the device EEPROM (requires manual save via the Settings sub-menu).


#### Improvements

- [SCALE](scale.md): Updated scale engine to improve support for scales of different sizes.
- [SETTINGS](settings.md): Improved menu order.
- [TRACK](track.md): Improved Aux Output support.
- Moved AutoVari8 and CV Out sub-menus to Settings.
- [POP](generators.md#pop): Improved algorithm.

#### Fixes

- NGEN can now properly boot when powered via external power supplies (rev1 only).
- Incoming MIDI notes are now properly routed to tracks.
- [SETTINGS](settings.md): The Firmware Update screen now displays correctly.
- [TRACK](track.md): Track 1 Aux Out is now disabled by default.
- [DRUMGEN](generators.md#drumgen): Opening the template selector no longer causes system delays.


---

### Version 1.1

#### Added
- New NGEN Framework: The entire NGEN's internal framework has been re-factored to improve performance and make it easier to add new features.
- Pattern Generation: algorithmically generate or variate an entire pattern.
- [TEMPLATES](tools.md#template): Use templates to quickly set up multiple tracks in your current pattern.
- Pattern & Track reloading: Quickly reload a pattern or track from their last saved state in a project (++"TRACK|CLK"++ or ++"PATTERN"++ + ++"RETURN"++).
- [ACDGEN](generators.md#acdgen): Added new Base Velocity and Accent parameter new Lead and Legato algorithms.
- [POLYFORM](generators.md#polyform): Added new Inversion, Inversion Range, Chord Quality and Trigger parameters.
- [THRU](generators.md#thru): Added new Delay parameter.
- [CHORDS](midifx.md#chord): Added 1 more interval (4 in total now) and a new Probability parameter.
- [SHAPER](midifx.md#shaper): new Mode parameter (Clip / Scale / Drop).
- [STRUM](midifx.md#strum): Added a new Probability parameter.
- [SCALE](scale.md): 2 new scales (Phrygian and Chromatic) and new global Octave parameter.
- [TRACK](track.md): New Clock-rate options: 4, 2, 1, 1/2, 1/4, 1/6, 1/8, 1/12, 1/16, 1/24, 1/32.
- [TRACK](track.md): New modal menu for managing tracks (save / copy / paste / delete).
- [PATTERN](pattern.md#pattern-menu): New modal menu for managing patterns (save / copy / paste / delete).
- [PATTERN](pattern.md): Quickly queue a [Pattern](pattern.md) by holding down the ++"PATTERN"++ button and turning the the ++"MENU ENCODER"++ .
- [PERFORM](perform.md): Use the 4 NGEN buttons (++"TRACK|CLK"++, ++"PATTERN"++, ++"FUNCTION"++, and ++"GENERATE"++) to mute / unmute the first 4 tracks while in the Perform sub-menu.
- [SETTINGS](settings.md): New Global Variation Amount (```Var Amount```) parameter.
- [SETTINGS](settings.md): New settings for Screensaver time (```Screensaver```), Idle Mode time (```Idle Time```), and Factory Reset.

#### Improvements
- Updated user interface design: The entire NGEN UI has been update with new designs for pages(Pattern Selector), notifications, modals (Pattern / Track edit), animations, list view, and more.
- Parameter course control: Parameters can now be adjusted in larger increments by holding down the ++"MENU ENCODER"++ or ++"FUNCTION"++ while turning it (coarse step determined by the parameter type).
- Re-designed settings page: NGEN's settings are now organized into separate pages for easier navigation.
- [MIDIPLAYER](generators.md#midi-player): Updated MIDI SMF file parsing and parameters.
- [PATTERN](pattern.md): The Pattern Selector view now shows the active Generator and MIDI FX for the first 3 active tracks of the selected pattern.
- [MIDI CLOCK](clockgen.md#midi-clock): Swing now works with both 1/16 and 1/8 clock-rates.
- [FREE CLOCK](clockgen.md#free-clock) now outputs MIDI Clock.
- Active project in memory: The active project now remains entirely in memory to improve performance and to allow users to modify the project's settings while playing without affecting the save file.
- Multi-core [Project](projects.md) management: NGEN now saves and loads projects using it's second-core to improve performance and avoid glitches while playing (pcb v1.1 and newer).
- When saving [projects](projects.md), NGEN will now check if there's enough space available.
- When loading [projects](projects.md), NGEN will now check if the project version is compatible with the current firmware version.
- New [Project](projects.md) file format with support for dynamic file size.
- Updated MIDI CC assignments for [Free Clock](clockgen.md#free-clock), [Bounce Clock](clockgen.md#bounce-clock), [Arper](generators.md#arper), [MIDI Player](generators.md#midi-player), [Chord](midifx.md#chord) 
- Improved potentiometer readings (better accuracy and less jitter).
- Updated screensaver design.

  
#### Fixes
- Major improvements to Project's saving and loading.
- Various minor bug fixes across the entire firmware.
- MIDI Player's Direction parameter now displays the correct values.

### Version 1.01

#### Added

- [POLYFORM](generators.md#polyform): Polyform now adjusts the length of generated notes based on the length of incoming MIDI notes.
- [SAMBA](generators.md#samba): New Note Length parameter.
- [SHUFFLER](generators.md#samba): New Offset parameter.
- New "MIDI CC Rx" setting for enabling / disabling MIDI CC input.

#### Improvements

- The [++"MENU ENCODER"++](hardwarecontrols.md#encoder) should now be more responsive and less prone to skips.
- Beta features will now show a "BETA" warning in the bottom-right corner.
- The [MIDI Monitor](tools.md#midi-monitor-monitor) will now promptly display the monitor view when selected.
- Improvements to the SAMBA generator.
- Improvements to the menu system.
- Minor UI design improvements.

#### Fixes
- Selecting the currently active Generator / MIDI FX in Track's settings will no longer reset the active Generator / MIDI FX.
- The display's header now gets properly re-drawn when exiting the selected Idle Mode and screensaver.
- [Screensaver](menunavigation.md#screensaver) now properly activates after 5 minutes of no hardware interaction.
- [Idle Mode (Animation / Param List)](menunavigation.md#idle-modes) now activates after 5 seconds of no hardware interaction while in the Generator and Clock sub-menus.


### Version 1.0

- Initial Version