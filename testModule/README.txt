Name(s)	: Simple Modulation Synth (prototyping; experimental) 
   	: Analogue Percussion Unit (prototype) 	
Author	: Joseph Auer
Copyleft: (c) Joseph Auer, 2016


Dev Spec:
	-> Windows XP with SP3
		- Advent 4211 Intel Atom
		- CPU N270 @ 1.60GHz, 
		- 0.99 GM of RAM
 
	-> Pd-extended: v 0.43.4-extended  
	-> Standard MMIO sound driver used in dev and testing
	  (ASIO has been used - for MIDI testing but nothihg
	   worth noting as different that I could experience)


About:

	This is a legacy dev and current testing dev. I notice "branch bloat".
	To stop this I am treating this area now as a storage area. 

	
Approach:
	Subpatch modularity
	GUI aesthetics in layout and division of "racking" patch modules. (Secondary to functionality for now)
 


2016/01/29:
	...


2016/01/22: 

	Analog Percussion Unit:
	-> Waveform generator (Sine, Saw, Square, Triangle, Pulse,[This is pulse width modulation])
	-> Waveform synthesis (combining waveforms and controling their "mix")
	-> Basic Envelope (ADSR) Filter (AM synthesis)
	-> Frequency Modulation (limited FM synthesis) *
	-> 4 percussion oscillator combinations, (Bass Drum, Kick Drum, Filtered Snare, Open Hi-Hat)
	-> Built-in Gem visualiser subpatch component sync'd to tempo 
	-> Simple Melodic Table Sequencer connected to tempo and wave synthesisers. 


	-> NOTES (The Roadmap ahead; next 2 weeks):
		I think all components are done as far as can be now using
		the current subpatch methodology. Now it is time to begin
		planning out the GUI, Abstract patches/"classes" and, (when
		required - subpatches).

		Abstraction may is expected to be slower thus, GUI cleanup
		is priority, with some more sub-patching. After this work, (one week),
		Patch/Class layout begins.


	   In the next two weeks expect:
		-> Clean GUI with no sub-patch controlling.
		-> Percussion waveform synthesis will be an Abstract Patch and cleaned-up Patch/Sub-patch.
		   (The Abstract Patch will be an "experimental" look at using OSC locally)
		-> Mixing and Mastering sub-patches will be abstracted away from main patch.
		-> GEM sub-patch will be dropped for now, as it is not a primary goal currently.
		-> Corrected Tempo / BPM with (1/2, 1/4, 1/8, 1/16 time support)  
		-> Dropping the 16 step-sequencer aprroach as given in the synth patch.
		   (Using wave table for sequencing addative/fm synth melody part(s))
		-> Further tuning volume levels across the addative waveforms.
		-> Attempt adding a cleaned keyboard sample control
			- No MIDI support for now, sorry :-(
		-> Test OSC support between module components across local network.
		-> Test Network support for module connectivity across networks
		-> Module translations to SynthEdit for VST (testing)
			(PdVST looks too time consuming currently)
		-> Investigate Arduino support, (currently have Pduino installed with
		   PDuino Common libs successfully being called to create external 
		   [Arduino] control.
		-> Allow user control to Record and save as many WAV files as they
		   wish; like normal stuff. 
		-> Anything else that comes up ...
 	

		In the near future the github will be cleaned up.   

				 
	The Future... :
		-> Add granular synthesis support.
		-> Visual ADSR vector-based waveform shapping
		-> GEM integration - visual modules.
		-> Stramlining code for ease of migration over to Max/MSP
		   (so, goodby [spigot], [sin], [cos] logics)
		-> Arduino Prototyping against the Pd modules - looking to generate
		   a digital sound controller for use against Puredata patches and
		   standalone.


2016/01/11-ish:

	Simple Modulation Synth Features:
	-> Waveform generator (Sine, Saw, Square, Triangle, Pulse,[This is pulse width modulation])
	-> Waveform synthesis (combining waveforms and controling their "mix")
	-> Basic Envelope (ADSR) Filter (AM synthesis)
	-> Frequency Modulation (limited FM synthesis) *
	-> Key/MIDI "note" assignment capability **
		** [Computer keyboard mapping assingment works; synthesis assignment work needs to be done] 
		** [MIDI notein/ ctin not working in Windows XP with ASIO or default audio driver MMIO, (NG)]
	 	

	Simple Modulation Synth Features (Todo):
	-> 16 step sequencer
	-> 16 step melodic sequencer (limited composer)
		--> DNA algorithmic sequencer (2ndary importance to everything listed here)
	-> Tempo controler
	-> Sampling support - granular synthesis of waveforms - not "that other sampling". 
		(keeping it "pure" but will have a "unpure version")
	-> Convert to VST (Researched but unsure of all details)


 