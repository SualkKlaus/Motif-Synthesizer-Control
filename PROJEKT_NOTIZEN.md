# Projekt-Notizen: Motif Synthesizer Control

Diese Datei hält die wichtigen lokalen Quellen und technischen Entscheidungen für
die Weiterentwicklung des Bedienprogramms fest.

## Projektdateien

- Projektordner: `/home/klaus/Dokumente/GitHub Projekte/Motif-Synthesizer-Control`
- Aktuelle Programmversion: `beyhl_synth_V22.html`
- Zielgerät: Yamaha MOTIF-RACK ES

## Verbindliche MIDI-Quelle

Die richtige Data List für dieses Gerät ist:

`/home/klaus/Musik/Motif Bedienprogramm/MOTIF_RACK_ES_DataList_stimmt_mit_Rack.pdf`

Wichtig: Für das Programm die **MOTIF-RACK-ES**-Data-List verwenden, nicht die
allgemeine `MOTIF_ES_DataList.pdf`.

### Richtige Tabelle für die Part-Steuerung

- Tabellenname: `MIDI PARAMETER CHANGE TABLE (MULTI PART)`
- PDF-Seite: **73**
- Im Dokument aufgedruckte Seite: **72**
- Basisadresse: `37 pp xx`
- `pp = 00–0F` entspricht Part 1–16

Wichtige Parameter aus dieser Tabelle:

| Adresse `xx` | Parameter |
|---|---|
| `00` | Bank Select MSB |
| `01` | Bank Select LSB |
| `02` | Program Number |
| `03` | Receive Channel |
| `0D` | Volume |
| `0E` | Pan |
| `12` | Reverb Send |
| `13` | Chorus Send |
| `17` | Filter Cutoff Frequency |
| `18` | Filter Resonance/Width |
| `23` | AEG Attack Time |
| `25` | AEG Decay Time |
| `26` | AEG Release Time |

Das im Programm verwendete SysEx-Schema lautet:

```text
F0 43 10 7F 00 37 pp xx value F7
```

Die Umsetzung befindet sich in `beyhl_synth_V22.html` in der Funktion
`multiPartParam()`.

## Stand V22

In V22 funktionieren zusätzlich diese Bedienbereiche:

- Mix und Effekte
- Filter
- Amplitude EG

Filter und Amplitude EG senden im Voice-Modus die vom Rack akzeptierten
Offset-Adressen unter `40 70`. Die sichtbaren Kurzangaben im Programm sind:

- Filter: `40 70 47 / 48`
- Amplitude EG: `40 70 49 / 37 / 38 / 4A`

## Weitere lokale Yamaha-Unterlagen

- Bedienungsanleitung:
  `/home/klaus/Musik/Motif Bedienprogramm/motifrackes_en_om_b0.pdf`
- MIDI-Einstellungen:
  `/home/klaus/Musik/Motif Bedienprogramm/Einstellung Midi Motif Rack.txt`

## Merksatz

Bei Fragen nach „der richtigen MIDI-Tabelle“ ist immer die Datei
`MOTIF_RACK_ES_DataList_stimmt_mit_Rack.pdf` und darin die Tabelle
`MIDI PARAMETER CHANGE TABLE (MULTI PART)` auf PDF-Seite 73 gemeint.
