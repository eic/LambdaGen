# PYTHIA8 Lambda Production

This code simulates proton-electron collisions using Pythia8 and saves in HepMC format only the events where a Lambda or anti-Lambda is produced.

## Installation

To run this code, you need to install [Pythia8](https://pythia.org/), a program for the generation of high-energy physics collision events. You can download the latest version of Pythia8 from [here](https://pythia.org/download/pythia83/pythia8306.tgz) and follow the installation instructions on the front page. 
For this code version 8.306 was used. 

## Usage

After installing Pythia8, you need to replace the main41.cc file in the examples folder with the code in `main41_Lam.cc`. Then, you can compile the code using `make main41` and run it using `./main41`. The code will generate four HepMC files, each containing events with a Lambda or anti-Lambda. The code will stop when the desired number of lambdas produced (Lcount) is reached. You can modify the value of Lcount in the code to change the number of events you want to generate.
