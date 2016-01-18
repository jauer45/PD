Name: Simple Modulation Synth (very beta, gamma even; experimental) 
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

	This is a legacy dev.

	This is a test. Unless you know a decent amount about Pd this probably is not for you
	as it is undocumented very beta testing ideas stuff with all the badness that entails. 
	Nothing is very clean here. The basics of this "synth" have been used as the basis 
	for the bassMachine modular unit, which is better documented and more 
	fufilling to use imo.
 

Approach:
	Subpatch modularity
	GUI aesthetics in layout and division of "racking" patch modules. (Secondary to functionality for now)
 

Features:
	Waveform generator (Sine, Saw, Square, Triangle, Pulse,[This is pulse width modulation])
	Waveform synthesis (combining waveforms and controling their "mix")
	Basic Envelope (ADSR) Filter (AM synthesis)
	Frequency Modulation (limited FM synthesis) *
	Key/MIDI "note" assignment capability **
		** [Computer keyboard mapping assingment works; synthesis assignment work needs to be done] 
		** [MIDI notein/ ctin not working in Windows XP with ASIO or default audio driver MMIO, (NG)]
	
	 	

Features (Todo):
	16 step sequencer
	16 step melodic sequencer (limited composer)
		-> DNA algorithmic sequencer (2ndary importance to everything listed here)
	Tempo controler
	Sampling support - granular synthesis of waveforms - not "that other sampling". 
		(keeping it "pure" but will have a "unpure version")
	Convert to VST (Researched but unsure of all details)