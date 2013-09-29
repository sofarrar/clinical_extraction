README
INSTALL/SETUP
Requirements: Both cTAKES and MetaMap require JDK 1.6+
1. unzip ctakes_medphora.zip to ctakes folder (called $CT)
   easier to use my installation, located in github. There is some customization to run from command line.
2. install MetaMap
   a. unzip public_mm_linux_main_2013.tar.bz2 to metamap folder (called $MM)
      I got it from here http://metamap.nlm.nih.gov/#Full_Download, but you need the UMLS license download to download.
	tlingmed, Biocc29 is my login
   b. run $MM/public_mm/Install MetaMap.sh (may have a slightly different name)

RUNNING cTAKES and MetaMAP
Pipeline Notes
1: runctakesCMD.sh has a minimum memory parameter of 1024M. It may require more, but I usually haven't been able to run it with less
it is called in the preprocess script and located $CT/bin/runctakesCMD.sh.
2: clinical notes file needs to be a written file in the fs. If the input from the pilot is a buffer, then it should be written to the fs, as a requirement for the pipeline.
3: Pipeline has two steps. Additional methods of IE can be added as an intermediary step between preprocess (e.g. step 2a) and process or as a postprocessing step (e.g. Step 3). 
   a. A CRF ML system can be employed from the output of MM/CT and fed to the processing step.
   b. The current state of the problem slots in the *.parsed ouput from step2 can be used as candidate list for a ML system.

STEP 1: PreProcess
bash MedPhora/medphora_pipeline_preprocess.sh INPUTDIR NOTE_FILENAME OUTPUTDIR CTAKES_ROOT METAMAP_ROOT
STEP 2: Process
java -jar MedExtractor.jar INPUTDIR_OR_INPUTFILE OUTPUTDIR

Output of MetaMap, cTAKES, and MedExtractor are all located in OUPUT Directory
