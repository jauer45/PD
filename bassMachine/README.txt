Name	: bassMachine v.05 (Very beta! Experimental)
Author	: Joseph Auer
Copyleft: (c) Joseph Auer, 2016

	The normal Open Source Creative Commons "rules" apply: 
	Hacks, modifications and usage is free. It would be nice if you 
	extensively referenced or used to generate an audio composition 
	from this patch that you note it. -- thanx

Dev Spec of sorts:
	-> Windows XP with SP3
		- Advent 4211 Intel Atom
		- CPU N270 @ 1.60GHz, 
		- 0.99 GM of RAM
 
	-> Pd-extended: v 0.43.4-extended  
	-> Standard MMIO sound driver used in dev and testing
	  (ASIO has been used - for MIDI testing but nothihg
	   worth noting as different that I could experience)
	


----------------------------------------------------------------------
A Guide Of Sorts 
----------------------------------------------------------------------


Requisits:


	To run this Puredata patch you need to have 
	Puredata version, (Microsoft Windows, Mac OSX, Linux):

		- Get Pd-extended here: 
		- Pd-extended: v 0.43.4-extended  



About:

	This is a Puredata patch ring modulated low-high frequency 
	generator with a simple attack, sustain, decay and release 
	capability.

	This is to be a modular component of a much larger project 
	to build a "modular" Puredata, (Pd), patch DAW which I, 
	(or anyone else), can use to construct a piece of 
	music/sound/noise/whatever audio.

	There is a recording facility for a one shot recording
	of the sounds you make for any length you so wish, (note that a 
	six minute recording will generate around a 16 Mb WAV file). The 
	generated 'example.wav' file will be created in the directory 
	where you opened this Pd BassMachine patch.



Feature Set (+ Quirks/Bugs !):

> 'POWER'
	(Mouse click once) Off	: Sets the Pd-extended DSP off (no sound generated)
	(Mouse click once) On	: Sets the Pd-extended DSP on (sound generated)

	* However, when On is clicked, you will still not be able to hear the audio.
	  The reason for this is that the 'AUDIO' digital audio connection, (dac) will not 
	  have been set active.   


> 'AUDIO'
	Toggle Box = [ ] or [x]

	(Mouse click once) If [ ] Then the digital audio connection for speaker 
	sound output is not set. 
		(cannot hear sound from speakers)
  
	(Mouse click once) If [X] Then the the digital audio connection for speaker 
	sound output is set.
		(Can hear the sound from the speakers) 


> 'Tempo':
	For the Tempo setting the range is set from 0.1 - 120 (this seems imo not
	to be a correct manifestation of bpm despite the assurances I am getting
	that the maths is correct in determining the BPM - odd).

	The result is that when you are playing with tempo and you set the knob
	to the far-most left position the tempo will stay in the stopped position,
	even if the tempo is increased. To get the tempo to behave normally again just
	click the 'AUDIO' toggle off ([ ]) then on ([X]). It should now be moving
	normal again.

		Status: currently working on fixes/augmentations against the above issues


> WAV FORM (Waveform modulation):
	These four knobs set the ring modulation against a wave type, (e.g. Square Wave).
	These knobs modulate the selected wave type(s), as well as determine a selected
	wavform's envelope shape, (ADSR). Play around and have fun; experiment.

	* NOTE: The ring modulation currently uses sine wave and saw waves for modulating against.
		It means that even if all WAV TYPE wave forms are not selected a sound will still
		be heard. This is essentially a feature but I would like to control the off/on
		state of these pre-set modulators in future. 


> WAV TYPE (Type of Waveform):
	Select one or more of the following wave types to be manipulated:
	(Mouse click) Sine Wave (Sin): 
		Off: []; On: [X]

	(Mouse click) Saw Wave (Saw):
		Off: []; On: [X]

	(Mouse click) Saw Wave (Tri):
		Off: []; On: [X]

	(Mouse click) Saw Wave (Sqr):
		Off: []; On: [X]	 
	

	*NOTE: Multiple on off selections of the waveform types needs more
		development in completely cutting off the selected waveform tone.
		It is mainly the case that when you select or deselect a waveform
		The waveform will "start" to be active at the current VCO, CUTOFF
		and WAV FORM settings. This means that when you deselect a wave form
		it is mostly the case that that shut down waveforms last recorded "tone"
		will be still audible/active. This has the "neat" by-product of creating
		a louder overtone with a greater pulsewidth. So, you can create a deeper
		louder waveform with some "neat" melodic complexity, (hence why here a
		"bug" can be seen as a "feature" - this needs more control though; so
		on the TODO list it goes...).


> SYNC IN 
	*** Not Working. No function for now. Ignore for now. 
	    In future the idea is for network/OSC tempo control. ***


> VOL
	The overall volume of the wave sound(s) being generated. 


> VCO
	Pitch 1: lower frequency relative to LFO Rate
	Pitch 2: less lower frequency relative to LFO Rate
	Pitch 3: higher frequency relative to LFO Rate
	Rate + Int:
		Set the saw waveform frequenc(y/ies) for pulewidth, 
		(aka wave "fatness")


> CUTOFF
	See WAV FORM section

 

> AUDIO (and) REC
	See AUDIO section about switching the AUDIO on.

	When the AUDIO is active (i.e. '[X]'), then that status is passed on to
	this AUDIO REC area. Here the digital audio connection is made for speaker
	output. It is here that out recroding facility is needed to be set as output, 
	live recording and playback actions all requuire access to the digital
	audio controller.

	REC (section):
		Record:
			set [X] to record. Set [ ] to not record
		
			On:
				Start recording
			Off:
				Stop recording
			Playbk:
				Play back the audio recording you have just recorded.


		Extra bit:
			[pd Recd] sub-patch object has a right-most outlet which has a 'bang' attached.
				You can click on this object to see the visual waveform output. If the
				waveform - for some reason - should have it's amlitude (Y-axis), exceed
				the table then you need to turn down the volume.
			[tabwrite~ Recorded] object has a bang attached to it's input slot. You can
				press this after doing 'playbk'to see if - somehow - your recording level
				is exccessively high, (again, if the amplitude exceeds the table boundry 
				then you need to check why the recording might be too loud. I cannot think
				of a reason other than a soundcard issue).

     

		* NOTE: Because sound is currently saved to a prenamed file callled example.wav
			the recording can only be saved once. Any subsequent recording will
			overwrite the previous recording. For storing multiple recordings
			you need to rename the example.wav file to a name of your own choosing.
			Once done, the recording is safe and will not be overwritten by
			this Pd patch. This is on the TODO list as well.



----------------------------------------------------------------------
TODO List:
	MAIN AIM: Create a "Modular" DAW which is designed in such a way as to be
		  visually suggestive of an same Hardware DAW set.
 

	01) Pulse Width Wave Type control setting.
	02) Correctly unsetting a deselected wave type.
	03) Refactoring the codebase into controller and Audio tiers for 
	   OSC / Network functionality add. IMPORTANT !!!
	04) Add a beatMachine module patch
	05) Add a mixMachine module patch
	06) Add granular synthesis to the mixMachine patch
	07) Add GEM component to mixMachine (simple VJ thingy)
	08) Pd -> pdVST or Pd -> recode to SynthEdit -> VST suport
		-> currently investigating SynthEdit / Pd confluence
	09) Pduino support, (this is complet on the Pd side; Arduino side TODO)
	10) Add many more modular components
	11) Add key/MIDI control to modules, (currently have a key controlled
		bassMachine in prototype but some playbacks are loosing pulsewidth
		or/and a selected waveform altogether; not harmonic enough imo) 
	12) More to come I am sure as things move along here
