# Scale

---

## About Scale

![](images/NGEN_Scale.png){align=right}
Because NGEN is designed with live performance in mind, most of the Generators process notes in terms of musical intervals rather than specific notes. Therefore these Generators use the selected **Key** and **Scale** in the **SCALE** sub-menu to translate those intervals to the appropriate notes.

This approach lets the user change the **Key** and **Scale** of all **[Tracks](track.md)** simultaneously via the **SCALE** sub-menu (available in the **MAIN MENU**).

A global Octave control is also available under the Scale sub-menu.

---

## List of Available Scales

- Minor

- Major

- Harmonic Minor (```mHARM```)

- Melodic Minor (```mMELO```)

- Major Pentatonic (```MPENT```)

- Minor Pentatonic (```mPENT```)

- Blues

- Dorian (```DORIA```)

- Lydian (```LYDIA```)

- Locrian (```LOCRI```)

- Arabic (```ARAB```)

- Augmented (```AUGM```)

- Wholetone (```WHOLE```)

- Phrygian (```PHRYG```)

- Chromatic (```CHROM```)


<!-- 

	const byte MINOR_SCALE[12]  = {0, 0, 2, 3, 3, 5, 5, 7, 8, 8, 10, 10};
	const byte MAJOR_SCALE[12]  = {0, 0, 2, 2, 4, 5, 5, 7, 7, 9, 9, 11};
	const byte HARMONIC_SCALE[12]  = {0, 0, 2, 3, 3, 5, 5, 7, 8, 8, 11, 11};
	const byte MELODIC_SCALE[12]  = {0, 0, 2, 3, 3, 5, 5, 7, 7, 9, 11, 11};
	const byte MAJORPENT_SCALE[12]  = {0, 0, 2, 2, 4, 4, 7, 7, 7, 9, 9, 9};
	const byte MINORPENT_SCALE[12]  = {0, 0, 0, 3, 3, 5, 5, 7, 7, 7, 10, 10};
	const byte BLUES_SCALE[12]  = {0, 0, 3, 3, 3, 5, 6, 7, 7, 7, 10, 10};
	const byte DORIAN_SCALE[12]  = {0, 0, 2, 3, 3, 5, 5, 7, 7, 9, 10, 10};
	const byte LYDIAN_SCALE[12]  = {0, 0, 2, 2, 4, 4, 6, 7, 7, 9, 9, 11};
	const byte LOCRIAN_SCALE[12]  = {0, 1, 3, 3, 4, 4, 7, 7, 8, 8, 10, 10};
	const byte ARABIC_SCALE[12]  = {0, 1, 1, 4, 4, 5, 7, 7, 8, 8, 11, 11};
	const byte AUGMENTED_SCALE[12]  = {0, 0, 3, 3, 4, 4, 7, 7, 8, 8, 11, 11};
	const byte WHOLETONE_SCALE[12]  = {0,  -->