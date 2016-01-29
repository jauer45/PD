MODULAR RYTHM MACHINE v 0.03
Joseph Auer, 2015/2016
(Creative Commons)

[Prerequisuits]

 	Pd-external v0.43 or >



[Dir Layout/Stuff]
	Extract to where Pd will see/read files

 	./rythmMachine/*

	- 38 files
	- 044.7 KB total memory size
	- 176.0 KB total memory size on disk



[Issues / TODO List]

	- The biggest annoyance is grieved over at the start. There now has
	been a couple attempts to modularise the mixing or "mixdown"
	flow where each sound group type is mixed through it's own
	abstraction, which in turn connects to the abstraction master 
	effect unit, which then routes to the DAC output/record 
	Pd abstraction. In this more modular diffuse set-up the output
	will heavily clip with the mastered output sound quickly
	detuning to a heavily distorted ersatz state. Investigating
	into why this more efficient code handling should cause this 
	affect, (taking away the delay and reverb affects check).
	 
	There may be a greater issue here where I have to "normalise"
	the "channel" mixing before going to the output.

	This is important as the current arch makes the addition
	off FM bass sounds quite difficult and cluttered.   
	  

	 - There is an issue with sound where, when an sound is initially
	selected in the ON state, loud noise will be heard - this is the
	sound "moving" at a very high tempo. A further move of the knob
	or a selection of the sound's related timer, (the horizontal radio
	array), will set the sound as normal in the tempo. Not sure why this
	is the case. (Will be fixed in future). Annoyance, but not affecting
	any other subsequent behaviours.


	 - There is an issue that, when an hradio timing is newly selected
	the change will not immeadiately occur. You need to move the knob
	to initiate the new timing state. Looking at how to initiate the
	change when the hradio selection changes, (probably requires adding
	a trigger to the current routing handling to solve this issue).

	 - Need to bring the recording facility to the "front panel" as it
	   currently sits deep in the sub-patch abstraction sets.

	- Need to add FM bass/synth mod integration

	- Need to code for OSC control allowing the Pd modules to "sync"
	on the tempo level, (establish clear MASTER/SLAVE setting). Need
	to look at how dac~ will be affected/can be controlled for 1db
	threshold clear state where addative sounds occur.   

	- File recording/saving  

[Code Layout]

 	_Patch (Abstract)
	  _SubPatch
 	    _Abstract
 	      _subPatch
	      _ Abstract 
	

	WAVE:
		Square: 	(square~)

		Square Alt:	sqr_alt_wave.pd (BS/KD)
				sqr_alt_waveII.pd (BS/KD)

		Triangle: 	tri_wave.pd (BS/KD)
				tri_waveII.pd (BS/KD)
				tri_waveIII.pd (BS/KD)

		Sine:     	(osc~)

		Saw:      	(phasor~)


	INSTR:
		KickDrum:	kick_mod.pd
		KickDrum2: 	kick2_mod.pd
		KickDrum3:	kick3_mod.pd
		KickDrum4	kick4_mod.pd
		Snare: 		snare_mod.pd
		Snare2: 	sngam_mod.pd
		HiHat Closed: 	hh_mod.pd
		HiHat2 Closed: 	hh2_mod.pd
		HiHat Open: 	hho_mod.pd


 	INSTR BANK: 
		Kick:		kick_mod_bank01.pd
				kick_mod_bank02.pd
				kick_mod_bank03.pd
				kick_mod_bank04.pd

		Snare:		snare_mod_bank01.pd
				snare2_mod_bank02.pd
		...
		HiHat:		hh_mod_bank01.pd
				hh_mod_bank02.pd
				hho_mod_bank01.pd
		...


	TIMINGS:
		Tempo/BPM:	tempo.pd

 	MAIN:	
		Main:
				Product.pd
					pd sndONOFF (sub-patch)
					pd product_mix_wiring (sub-patch)
 				main_kd.pd 
				main_kdII.pd
				main_kdIII.pd
				main_kdIV.pd
				main_sd.pd
				main_sdII.pd
				main_sdIII.pd (Not used)
				main_hh.pd
				main_hhII.pd
				main_hho.pd
				main_mixing_unit.pd

 	REC:
		Mix:		mix_rec.pd
		Record:		rec_file.pd
				(Currently the only mod not to have
			 	the GUI ready)


 	OTHERS (NOT USED CURRENTLY):
		Seperate Intstrument bank mastering attempt
		(with the completion of the GUI arch not sure how to integrate these):
				kick_mod_mixer.pd
				snare_mod_mixer.pd
				hh_mod_mixer.pd
	
	Others (Timing/Clock - issue with tempo display (seeting correct 
		diameter / circumfrance)):
				tempo.pd
				timing_mod.pd
			

END			
