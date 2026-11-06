# CHANT data dictionary

The 30 song CSVs and `CHANT_merged.csv` share the 19 columns below. Each row represents a pitched note, a rest, or a spoken event. The files use UTF-8 and include a header row. Quarter lengths (QL) express musical time in quarter-note units.

| CSV column | Meaning | Units or examples |
| --- | --- | --- |
| `Corpus Song #` | Song's position in CHANT | `DG1` through `DG30` |
| `Song ID` | Identifier based on the song's number in the source collection | `SID002` for song 002 |
| `Seq` | Sequential event number within the song | Starts at 1 |
| `Measure` | Measure label recorded in the transcription | `1`, `2`, or `upbeat` |
| `Event` | Event number within the assigned measure | Starts at 1 in each measure |
| `Jianpu Degree` | Number transcribed from the Jianpu notation | `1`–`7` for pitched degrees, `0` for rests and spoken events |
| `Accidental` | Chromatic adjustment to the numbered degree | `-1` lowers by a semitone, `0` leaves the degree unchanged, `1` raises by a semitone |
| `Octave Shift` | Octave displacement relative to the unshifted degree | `-1` for one octave down, `0` for no shift, `1` for one octave up |
| `Duration (QL)` | Notated length of the event | `1` for a quarter note, `0.75` for a dotted eighth, `0` for DG18 grace notes |
| `Rhythm` | Saved duration label | `eighth`, `dotted-eighth`, `grace (32nd)`, or blank |
| `Phrase End` | Marks the last event included in an annotated phrase | `END` or blank |
| `Phrase #` | Saved phrase number for the event | `1`, `2`, `3`; MIDI markers follow `Phrase End` where the two fields differ |
| `Onset (QL)` | Saved start time from the beginning of the transcription | Quarter lengths, with `0` at the start |
| `MIDI` | Numeric pitch derived from the song's pitch reference, degree, accidental, and octave shift | `60` for middle C; blank for rests and spoken events |
| `Pitch` | Pitch name and octave, or an unpitched event label | `C4`, `F#4`, `Rest`, `spoken` |
| `QC` | Saved result of a workbook validation check | `OK`, `CROSSES BAR`, `ENTER DURATION`, or blank |
| `Active Meter` | Meter recorded for the event | `2/4`, `3/4`, `4/4`, or `1/4` for the DG18 pickup |
| `Bar QL` | Expected length of a measure in the active meter | `2` in 2/4, `3` in 3/4, `4` in 4/4 |
| `Onset in Measure` | Saved start time relative to the start of the measure | Quarter lengths, with `0` at the start of a bar |

The symbolic exports derive elapsed time from cumulative durations. Saved onset and measure fields can differ from that calculation. DG18 grace notes contribute zero to the notated measure and borrow time from the following note in MIDI playback.

## Song metadata

[`CSV/metadata.csv`](CSV/metadata.csv) has one row per song. Join it to the event CSVs using `Corpus Song #` and `Song ID` together.

| Column | Meaning |
| --- | --- |
| `Corpus Song #`, `Song ID` | Corpus position and source song identifier |
| `Song Name`, `Song Name (Pinyin)` | Song title in Chinese characters and pinyin |
| `Composer`, `Composer (Pinyin)` | Composer credit in Chinese characters and pinyin |
| `Lyricist`, `Lyricist (Pinyin)` | Lyricist credit in Chinese characters and pinyin |
| `Key` | Pitch reference for Jianpu degree 1. In DG23, degree 1 is D and degree 6 is B, the tonic of B minor. |
| `Meter` | Song-level time signature. See `Active Meter` for event-level changes. |
| `Comment` | Additional information about the song or its encoding |

Blank cells indicate that a value is unavailable in the corresponding field.
