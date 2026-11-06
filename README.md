# Chinese Historical Archive of Numbered Transcriptions (CHANT)

CHANT contains manually encoded Jianpu transcriptions of 30 songs from the sixth edition of *Dazhong Gesheng* (1938). This release includes pitch, rhythm, and phrase annotations. Song metadata includes lyricist credits.

| Files | Contents |
| --- | --- |
| [CSV](CSV/) | 30 song transcriptions, the merged event table, and song metadata |
| [MIDI](MIDI/) | 30 playback files |
| [MusicXML](MusicXML/) | 30 staff-notation files |
| [Score PDFs](Score%20PDFs/) | 30 scans of the source scores |
| [Release ZIP](CHANT_Data_No_Lyrics.zip) | A single download of the dataset files |

Match song files by their shared identifier, such as `DG18_SID006`. In the CSVs, each row represents an encoded event and durations are in quarter-note lengths. DG18's grace notes contribute zero to the notated measure. Its MIDI renders them within the following note's duration. The `MIDI` and `Pitch` columns are derived from the Jianpu key, degree, octave shift, and accidental. `Pitch` follows the spelling implied by the numbered degree. Further encoding and playback details are in the release ZIP.
