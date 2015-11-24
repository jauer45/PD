# 2015/11/20

# PD
Pure Data Projects, Modules and default Audio Samples. Feel free to use, borrow, modify as you wish; 
open source. If, for whatever strange reason you wish to use a significant set of the code of a pd 
module/patch it would be appreciated if you could reference my authorship/contribution. Thanks :-)

Requisits:
  1. Make sure you are running latest stable build of Pd at least. Um, that should be it.
  

Notes:
  1. These patches were made on a Windows XP machines, (yes, you read that correctly). Mac, Linux and
     other Windows OS versions have not been tested yet. 

  2. In a Pd patch or/and module where a file path is hardcoded, (early days here and currently 
     in the process of learning to use openpanel effectively), please change the 
     filepath(s) to your audio storage area for WAV file audio file reads, 
     (You may need to do Cntrl+E to enter Edit Mode).
  3. The audio files contained come from a very old Fruity Loops demo and an JS web audio demo.
     They are not mine but are already available to anyone in some guise or other. These will be
	 replaced soon with our personal audio clips soon...


RoadMap:
  1. DONE:
		A) A 6 Track drum machine with BPM and Note (1/16 -> 1) is currently done		
      
  2. TODO (Add):
		A) Add a freq filter for drum machine sequence (and each sound if possible [mem constraints])
		B) Add noise, delay and reverb/echo effects (same wish(es) hold(s) as above ^)
		C) Add drum machine sequence PLAY, STOP and REC button / funcs (save to WAV/AIFF file)
		D) Add EQ mastering
		E) Add ADSR wave form editor (for given selected drum sound)
		F) Add granular synth sample/slicer (Master affect)
		(due date of the above: 2015/12/04)
		
  3. TROUBLE:
		A) USB MIDI input / output seems currently a NG. Have tried a couple times with failure of the MIDI
		   Message to be received, ("it seems" by CPU and mem handling that a active connection is being
		   tried but failing on the channel). More investigations required.
		B) Memory (how to refine for final prod)!
		
  4. MASTERPLAN:
		A) Personal Pure Data DAW to use in myriad of purposes; not just internal/MIDI composition.
		B) For use in live sets as a MIDI sync or networked live jam...
		C) Larger vision to integrate into the Web Browser via JS plugin support with Web Audio API.
		   Currently investigating Heavy, pdWeb, Processing.js (yes, there is an hardware component lurking...)
		D) "Plug" into a Arduino sound sequencer instrument currently in research...
		
  5. WHY ?:
		A) Why not ?! Pure Data is an open source lang that is essentially the same as Ableton's MAX/MSP, 
		   (same initial author even). It seems to me the days of a needed proprietary DAW like Ableton or 
		   FL Studio are gone now that anyone can code the essential source of it all. Or, at least, create 
		   decent VSTs which can be assembled to enhance the users experience of these established DAWs. 
		   IMO I am doing nothing special, it's just something so within any single person's ability to do 
		   that it really seems that it should be done as a matter of "fine upstanding morale principals". 
		   