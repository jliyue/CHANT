CHANT dataset files

CSV contains 30 individual song transcriptions, a merged table of 4205 events
and 19 columns, and the song metadata. MusicXML, MIDI, and Score PDFs
contain 30 files each. Match files by their shared DG number and SID.

This release omits note-aligned lyrics from the individual CSVs, merged CSV,
MusicXML, and MIDI. The metadata retains lyricist credits. Each song CSV and the merged CSV
use the same 19 columns.

The MusicXML and MIDI files are generated from the CSV transcriptions. They
follow one pass through the recorded event sequence. MIDI uses piano and a
playback tempo of 120 BPM where the metadata provides no tempo. For DG2_SID005,
the MIDI uses 50 BPM as a playback interpretation of Largo. MusicXML represents
the transcription as staff notation. Use the score PDFs for the printed
jianpu notation, repeats, and original layout.

Symbolic timing is derived by summing the CSV durations. Saved onsets differ
on these songs (number of rows): DG1_SID002 (1), DG18_SID006 (9), DG23_SID018 (10), DG26_SID031 (62). Saved values remain in the
CSV tables. For DG1–DG9, Onset in Measure is calculated from cumulative durations
relative to the start of each meter section, modulo the bar length in
quarter-note units. DG3_SID007 is in 2/4 at events 1–165, 4/4 at events
166–222, and 2/4 again from event 223. Its symbolic exports use those
change points. Existing CSV Measure and Event values are retained.
When the pitch label and MIDI number differ, the symbolic exports use the
MIDI number. Differences:
DG8_SID020 event 39: D4 vs MIDI 74
DG8_SID020 event 40: D4 vs MIDI 74
DG9_SID026 event 112: D4 vs MIDI 74
DG9_SID026 event 115: D4 vs MIDI 74
DG9_SID026 event 171: E4 vs MIDI 76
DG9_SID026 event 172: D4 vs MIDI 74
DG9_SID026 event 174: D4 vs MIDI 74
DG9_SID026 event 175: E4 vs MIDI 76
DG9_SID026 event 176: D4 vs MIDI 74
DG9_SID026 event 179: D4 vs MIDI 74
DG10_SID028 event 25: Ab4 vs MIDI 56
DG10_SID028 event 26: Ab4 vs MIDI 56
DG10_SID028 event 59: Ab3 vs MIDI 68
DG10_SID028 event 60: Ab3 vs MIDI 68
DG10_SID028 event 82: Eb4 vs MIDI 75
DG10_SID028 event 83: Db4 vs MIDI 73
DG10_SID028 event 84: Bb4 vs MIDI 82
DG10_SID028 event 85: Db4 vs MIDI 73
DG10_SID028 event 86: F4 vs MIDI 77
DG10_SID028 event 87: F4 vs MIDI 77
DG10_SID028 event 88: Eb4 vs MIDI 75
DG10_SID028 event 89: Eb4 vs MIDI 75
DG10_SID028 event 90: F4 vs MIDI 77
DG10_SID028 event 91: Eb4 vs MIDI 75
DG10_SID028 event 92: F4 vs MIDI 77
DG10_SID028 event 93: Eb4 vs MIDI 75
DG10_SID028 event 94: Db4 vs MIDI 73
DG10_SID028 event 99: Db4 vs MIDI 73
DG10_SID028 event 179: Bb4 vs MIDI 58
DG10_SID028 event 180: Bb4 vs MIDI 58
DG10_SID028 event 182: Ab4 vs MIDI 56
DG10_SID028 event 183: Ab4 vs MIDI 56
DG10_SID028 event 206: Bb4 vs MIDI 82
DG10_SID028 event 207: Db4 vs MIDI 73
DG10_SID028 event 208: Eb4 vs MIDI 75
DG10_SID028 event 209: Db4 vs MIDI 73

DG5_SID013 uses 132 BPM as a playback interpretation of 較快，激昂地.
DG6_SID014 uses 104 BPM as a playback interpretation of 雄壯.
DG7_SID017 uses 108 BPM as a playback interpretation of 中等速度，昂奮地.

MIDI phrase markers follow the CSV Phrase End column. The first event and
each event immediately after an END row receive a start marker. Each end
marker sits at the onset of the END event and identifies that whole event
as part of the phrase, including its full duration. A marker can identify
a note or a rest. Markers follow END where the saved Phrase # disagrees.

DG8_SID020 uses 108 BPM as a playback interpretation of 中板.

DG16_SID003 was checked against the printed barlines and re-encoded as 161
events in 56 measures of 2/4. The export uses exact triplet durations.
