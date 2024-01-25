# PYTHIA8 Lambda Production

This code simulates proton-electron collisions using Pythia8 and saves in HepMC format only the events where a Lambda or anti-Lambda is produced.

## Installation

To run this code, you need to install [Pythia8](https://pythia.org/), a program for the generation of high-energy physics collision events. You can download Pythia8 using:
```
git clone git@gitlab.com:Pythia8/releases.git --branch pythia8XXX --single-branch
```
where XXX is the PYTHIA version number. You can find the list of Pythia8 releases [here](https://pythia.org/releases/). For this code version 8.306 was used. 
This will download zip `pythia8306.tgz`. Unzip and expand it with:
```
 tar xvfz pythia8306.tgz.
```
Move to the thus created pythia8306 directory, configure adding the hepmc3 package, and compile:
```
cd pythia8306
./configure --with-hepmc3
make
```

## Usage

After installing Pythia8, you need to replace the main41.cc file in the examples folder with the code in `main41_Lam.cc`. Then, you can compile the code using `make main41` and run it using `./main41`. The code will generate four HepMC files, each containing events with a Lambda or anti-Lambda. The code will stop when the desired number of lambdas produced (Lcount) is reached. You can modify the value of Lcount in the code to change the number of events you want to generate.
