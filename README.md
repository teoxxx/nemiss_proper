# nemiss_proper
nemiss code repo 2023
nemiss neutrino emission from hydrocode data, describing a simulated stellar binary system with relativistic jets, aka micro-quasar.

Updated: 201123, 281123

A folder with a pipeline setup to run PLUTO-nemiss-rlos2 resides in the current repo, minus the sim data of course. it is called torblob18dummies.

repo also includes a folder with the three files needed to run a pluto sim, at the neutrino scale. The modified pluto.ini PLUTO file is there, with the modification to produce required PLUTO dummy data files, that shall act as containers for the output of nemiss.

Careful, PLUTO 4.2 is used in this version of the pipeline. It should reside in the system and its setup.py file, located in PLUTO dir, should be called appropriately from the run folder. 

Another folder contains rlos2, accompanied by numerous PLUTO's auxiliary .pro IDL files. Out of those, pload.m is modified suitably, in order to facilitate running rlos2.

There are also two external param files, in another folder. These are used by rlos (one of them) and by nemiss (both of them). They make life easier, by avoiding editing hardwired vars in the code. 

Finally, a folder with nemiss. nemiss also includes pload_4d, which is an extended version of pload.nb, originally provided by PLUTO. 

The above files also exist mixed together in the main run folder, torblob18dummies. 

Actually, in order to run,  files need to be in the same folder. But they are also placed at separate folders for clarity.
In experimental_nemiss subfolder, minor upgrades were made, e.g. nemiss091123 fixes a bug in relation to TR11 relativistic conversion of a hot proton power-law particle distribution.

****How to run: (directions revolving around ubuntu linux setup)****

download to your machine the repo with its folder structure. Install IDL, Mathematica, C compiler and mpi.

move to torblob18dummies folder

from there, open a terminal and run: python ~/PLUTO/setup.py (replace with your PLUTO folder location)

menu of PLUTO pops up in terminal. press enter a few times. then, select def files for linux mpicc, from the menus.

exit pluto menu. in terminal, run make. 

if it compiles well, then good to go. run: mpirun -n 4 ./pluto -x2jet (four core run)

wait for hydrocode to end.

open nemiss in mathematica

run it, till the main loop that calculates nemission at eligible cells. then run next big cell, that writes results to pluto 'dummy' vars.  If all is well, we now have a large number of pluto data files with nemiss output. DO NOT RERUN PLUTO now in this dir, else we lose nemiss output. and nemiss is slower than pluto!

Now: run idl and open rlos. run it, reading pluto data files, some of them with nemiss content! 

Obtain special-relativistic synthetic neutrino image! 

***careful with external param files, they set up the whole thing! Leave intact at first!****









