# nemiss_proper
nemiss code repo 2023
nemiss neutrino emission from hydrocode data, describing a simulated stellar binary system with relativistic jets, aka micro-quasar.

Updated: 201123, 281123

A folder with a pipeline setup to run PLUTO-nemiss-rlos2 resides in the current repo, minus the sim data of course. it is called torblob18dummies.

repo also includes a folder with the three files needed to run a pluto sim, at the neutrino scale. The modified pluto.ini PLUTO file is there, with the modification to produce required PLUTO dummy data files, that shall act as containers for the output of nemiss. PLUTO reads this file as a priority from the run folder, versus the one in the source PLUTO folder. 

Careful, PLUTO 4.2 is used in this version of the pipeline. It should reside in the system and its setup.py file, located in PLUTO dir, should be called appropriately from the run folder. 

Another folder contains rlos2, accompanied by numerous PLUTO's auxiliary .pro IDL files. Out of those, pload.m is modified suitably, in order to facilitate running rlos2.

There are also two external param files, in another folder. These are used by rlos (one of them) and by nemiss (both of them). They make life easier, by avoiding editing hardwired vars in the code. 

Finally, a folder with nemiss. nemiss also includes pload_4d, which is an extended version of pload.nb, originally provided by PLUTO. 

The above files also exist mixed together in the main run folder, torblob18dummies. 

Actually, in order to run,  files need to be in the same folder. But they are also placed at separate folders for clarity.


In experimental_nemiss subfolder, minor upgrades were made, e.g. nemiss091123 fixes a bug in relation to TR11 relativistic conversion of a hot proton power-law particle distribution.
