DOC Init Build cmd (Cygwin Terminal Env): 

	User@User-PC ~Joseph
	$ for x in `ls -l PD | awk '{print $9}'`; do echo ${x} >> ReadmePD.md; ls -l PD/${x} | awk '{print "\t" $9}' >> ReadmePD.md; echo " " >> ReadmePD.md; done;


audioTR909

  About: Perc samples used by some pure-data patches here.
	
	BD.wav
	BD_2.wav
	CB.wav
	CHH.wav
	CHihat10-05.wav
	CL.wav
	CP.wav
	Crash10-05.wav
	CY.wav
	HandClap10.wav
	HC.WAV
	HighTom05-10-00.wav
	Kick05.wav
	Lc.wav
	LowTom05.wav
	LowTom05-10-00.wav
	MA.wav
	MC.WAV
	MidTom05-10-00.wav
	OHH.wav
	OHihat10-00.wav
	Ride10-05.wav
	RimShot10.wav
	RS.wav
	SD.wav
	SD_2.wav
	Snare05.wav
	TOM.wav
 
AVUnit

  Status: 85% - (Needs sync work: [CPU % load =~ 140.00])
	
	DrumPatch.pd
		- Is a percussion pattern algorithm patch which plays out to DAC
		- 6 [bng] send objects (for GEM receive patch: VidFeedArrayIII.pd)
		- Status: Working/OK (ignore out-of-range output error)
	GEMvisualArrayII.pd
		- Is a colour seperation and shape pd GEM patch
		- Status: Working/OK-NG (memory handling issues)
	VidFeedPCIII.pd
		- Is a PC video manipulation pd GEM patch
                - 4 [bng] receive objects (for controlling video rendering(s))
                - Status: Working/OK-NG ("glitchy" memory handling issue)	
	visualMotionGrp.pd
		- Is a colour seperation and shape pd GEM patch
                - Status: Working/OK-NG (memory handling issues)
 
bassMachine

  Status: OK; Sound Demo/Protype Idea; 100%
	
	bassMach_v_05.pd
		- Percussion pattern creator/composer
		- Has 3 VCOs, choice of Wave Type,(Sin, Saw, Tri, Sqr)
		- Has a Time sync input control inlet (change to OSC)
		- Has a record (WAV format), function
		- Has a Mixing subpatch
	README.txt 
		- Info about the patch
 
btSeqDev

  Status: Prototype/OK; 100%
	
	btSeq.pd
		- A Pd sample based percussion unit/pakckage
 
DNAAlgorithmicMusic

  Status: FAIL (Failed compositional idea based on tRNA and DNA
	amino acid sequence as a compositional form)

	freq2noteGuide.txt
	HumanInsulin.pd
	HumanInsulinModified.pd
	WaveTableSynthesis.txt
 
gemExamples

 Status:
	
	cylinder_wrapper.pd
	cylinder_wrapper_script.pd
		- Bundle patch set that allows x, y, z axis manipulation of 
		  cylinder and square shapes with alpha colour mask rendering.

	gemDrawCube.pd
	gemDrawCubeTrnslt.pd
		- Bundle patch set that

	gemDrawData.pd
	gemDrawSqr.pd

	gemDrawSqrTrnsltRotate.pd
	gemGeoManipColour.pd
	gemImageKeymap.pd

	gemImageManip.pd
	gemImageMetroTest.pd
	gemImageMetroTestII.pd
	gemImageMetroTestIII.pd
	gemImageMetroTestIV.pd

	gemImageMetroTestmkjam.pd
	gemImageMetroTestmkjam2.pd
	gemImageMetroTestmkjam3.pd
	gemInitTemplate.pd
	gemMousePolygonDraw.pd

	gemParticleImage.pd
	gemParticleImage2.pd
	gemParticleImage3.pd
	gemParticles.pd

	gemRecVidFileTest.pd

	gemVGazeCube4.pd
	gemVGazeCube5.pd
	gemVGazeManualManip.pd
	gemVGazeMinimalMix.pd
	gemVGazeMix.pd

	isotriangle_wrapper.pd
	isotriangle_wrapper_audio.pd
	isotriangle_wrapper_audio_script.pd
	isotriangle_wrapper_script.pd
		- Triangle shape GEM manipulation pd patch set

	LayoutEff.pd
	mymovie.mov

	pentagon_core.pd
	pentagon_core_wrapper.pd
		- Pentagon shape GEM manipulation pd patch set

	poly_wrapper_script.pd
	polygon_wrapper.pd
	polygonTest.pd
	polygonTestII.pd
	polyTests.pd
		-

	rn028_01.jpg
	rn028_02.jpg
	rn028_02_01.jpg
	rn028_02_02.jpg
	rn028_03.jpg
	rn028_03_01.jpg
	utaka.jpg
		- images used in the demo patches here
 
modularMachines

  Status: Demo/Prototype (100% in that it does what I set out to do;
	 20% in that the memory issue(s) severely seem to limit further
	 development.
 
  About: Initial attempt at building a DAW in Pure Data.
	 Memory issues have constrained the development of this
	 project currently. Currently there exists two main
	 components in the setup outside a mixing unit patch set:
	 1) A waveform sample percussion unit. 2) A synth set based
	 on Addative, Subtractive, FM and Granular synthesis.

	For the percussion unit and the melody shaper unit to work
	in pd the Product.pd, ProductB.pd and mix_rec.pd files need to be
	open. You can see a snapshot of this patch set in action under
	the vdocs/ folder, (modMachA.png, modMachB.png).
	
	+ bassMachine

		ProductB.pd
		pulseWidthMix.pd
		melodyShaper.pd
		seqCutoff.pd
		seqShaper.pd
		setWaveformDynamics.pd
		setBassMix.pd
		setWaves.pd
		setWavesIII.pd
		setWavesII.pd
		setWavesIV.pd
		wavAttDecFM.pd

	+ dnaMachine (You can ignore / delete this directory)

	hh_mod.pd
	hh_mod_bank01.pd
	hh_mod_bank02.pd
	hh2_mod.pd
	hho_mod.pd
	hho_mod_bank01.pd
	kick_8X8_mod.pd
	kick_mod.pd
	kick_mod_bank01.pd
	kick_mod_bank02.pd
	kick_mod_bank03.pd
	kick_mod_bank04.pd
	kick_mod_bank8X8.pd
	kick2_mod.pd
	kick3_mod.pd
	kick4_mod.pd
	main_hh.pd
	main_hhII.pd
	main_hho.pd
	main_kd.pd
	main_kdII.pd
	main_kdIII.pd
	main_kdIV.pd
	main_kdV.pd
	main_mixing_unit.pd
	main_sd.pd
	main_sdII.pd
	main_sdIII.pd
	mix_rec.pd
	Product.pd
	README.txt
	rec_file.pd
	saw_alt_wave.pd
	sn808_mod.pd
	snare_mod.pd
	snare_mod_bank01.pd
	snare_mod_bank02.pd
	snare_mod_bank8X8.pd
	sngam_mod.pd
	sqr_alt_wave.pd
	sqr_alt_waveII.pd
	tempo.pd
	timing_mod.pd
	tri_wave.pd
	tri_waveII.pd
	tri_waveIII.pd
 
modularMachinesII

  Status: See modularMachines 'Status' section

  About: Continuing omodularMachines development with an simple 
	 AV component where sound/music composition can be sync'd 
	 with pure-data GEM objects and patch(es)
	
	AudioEffectRecdUnit.pd
	basslineMod
	BassUnit
	BassUnitII
	example.wav
	GEMUnit
	GrnlrSynth
	mixer_output.pd
	PercUnit
	rec_file.pd
	SplrShflrUnit
	Synth
	SynthII
	tempo.pd
	WFormUnit
 
oscSequencer
	
	drumMachineMultiplexAnalog.pd
	oscSeq.pd
 
README.md
	PD/README.md
 
Sounds

  About: Perc samples used by some pure-data patches here.
	
	dinky-bass-1.wav
	dinky-bass-2.wav
	dinky-bass-3.wav
	dinky-cym.wav
	dinky-hat.wav
	dinky-hat-1.wav
	dinky-hat-2.wav
	dinky-kick-1.wav
	dinky-kick-2.wav
	dinky-kick-3.wav
	dinky-kick-4.wav
	dinky-kick-5.wav
	dinky-kick-6.wav
	dinky-snare-1.wav
	dinky-snare-2.wav
	dinky-snare-hat-1.wav
	PumpUpLondonMrLee.wav
 
testModule

  About: pd test modules. Some work; some do/may not.
	
	analogPercussionUnit.pd
	colour_anim_testV.pd
	colour_anim_testVI.pd
	colourr_anim_test.pd
	colourr_anim_testII.pd
	colourr_anim_testIII.pd
	colourr_anim_testIV.pd
	cube_buss_Interface.pd
	cube_pattern_set.pd
	cube_patternII_set.pd
	cylinder_buss_interface.pd
	cylinder_patternII_set.pd
	GEMGeoTest.pd
	GEMGeoTestII.pd
	GEMSquare.pd
	GEMvisualArray.pd
	GEMvisualArrayII.pd
	GEMvisualArrayIII.pd
	midiTest.pd
	midiTestChord.pd
	midiTestChordGEMSync.pd
	modAnaSynth_v04_8.pd
	README.txt
	sphere_buss_interface.pd
	sphere_pattern_set.pd
	sphere_patternII_set.pd
	square_pattern_set.pd
	square_patternII_set.pd


Environment Dev and Review:

Processor: 	Intel(R) Core(TM)2 Dou CPU   T5750 @2.00GHz 2.00
RAM: 		3.00 GB
System Type: 	32-bit Windows (Home Edition) 7 OS


