# Motif Synthesizer Control

Free control software for the Yamaha Motif Rack ES, running directly in the browser via the Web MIDI interface.

## Version 19 — GM Song Mode, Free Multi Voices and Channel Activity

## Start

Open the current version [`beyhl_synth_V19.html`](beyhl_synth_V19.html) in Chrome and allow MIDI access, then connect the Motif Rack ES via USB.

Version 19 uses the Yamaha-documented Multi Part parameter-change addresses to control the 16 internal parts. In Multi mode, the right-side selector switches between **GM from song** and **Free selection on the left**. GM mode reads the initial banks and programs from the loaded MIDI file. Free mode keeps a separate editable setup for all 16 parts, with bank and categorized voice selection directly in the left mixer. Saved free setups can be loaded again later.

Each MIDI channel has a small activity indicator: gray means unused, green means used by the loaded song, and a short red flash marks an incoming note during playback. The loaded song name remains visible in both Voice and Multi modes. Mixer volumes start at 90 percent for a consistent level.

The installed PLG1 piano board remains available as a separate Part 00 with its own MIDI channel, voice, volume, pan, reverb, mute, and solo controls. In Voice mode, **INTERN** and **PLG1 PIANO** retain independent settings. Complete setups can be saved under freely chosen names and loaded again through the browser's file dialogs.

## Interface History

All three project screenshots are retained here:

![Beyhl Synth V17 with PLG1 Extension](Beyhl_Synth_V17_PLG1_Extension.png)

![Beyhl Synth V12 interface](Beyhl_Synth_V12.png)

![Earlier Motif Synthesizer Control interface](Synthesizer_%20Bedienprogramm.png)

## Notice

The voice names used in this program originate from the Yamaha Motif Rack ES and serve only as designations for the sounds. All rights to these names belong to Yamaha Corporation. The sounds can easily be adapted to other Yamaha synthesizers, not just the ES. This project is intended as an open source contribution to support the wonderful Yamaha synthesizers and make their great hardware even more usable.

## Open Source and Usage Terms

This program is made available as open source for non-commercial use.

- You may use, study, modify, and redistribute the program for non-commercial purposes.
- Any modified or redistributed version must clearly credit **Klaus Beyhl** as the original author and retain this notice.
- Commercial use, sale, paid distribution, or integration into a commercial product or service is not permitted without prior written permission from Klaus Beyhl.

## AI Integration and Extensibility

The program is deliberately designed so that it can be extended easily. Its browser-based structure and Web MIDI controls provide a practical foundation for adding an AI connection in the future. For example, an AI assistant could translate natural-language instructions into synthesizer parameter changes, manage sounds, automate control sequences, or provide context-aware help while operating the instrument. No AI service is included by default, so developers remain free to connect the model or local AI system of their choice.
