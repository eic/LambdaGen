# PYTHIA8 Lambda Production

This code simulates proton-electron collisions using Pythia8 and saves in HepMC format only the events where a Lambda or anti-Lambda is produced.

## Installation

1) Get and run [eic-shell](https://eic.github.io/tutorial-setting-up-environment/02-eic-shell/index.html)

2) Clone and make Pythia8.306
```
mkdir Pythia8306
cd Pythia8306
git clone https://gitlab.com/Pythia8/releases.git --branch pythia8306 --single-branch
cd releases
./configure --with-hepmc3
make
cd bin
export LD_LIBRARY_PATH=$(pythia8-config --libdir):${LD_LIBRARY_PATH}
cd ../../
```

3) Clone and compile LambdaGen against Pythia
```
git clone https://gitlab.com/eic/LambdaGen.git --branch pythia8.306-1.0 --single-branch
cd LambdaGen
g++ main41_Lam.cc -o main41_Lam `pythia8-config --cflags --libs --hepmc3`
```

## Usage

1) Execute Lambda generator
```
./main41_Lam
```
The code will generate four HepMC files, each containing events with a Lambda or anti-Lambda. The code will stop when the desired number of lambdas produced (Lcount) is reached. You can modify the value of Lcount in the code to change the number of events you want to generate.

2) Take the generated outputs and run [afterburner](https://github.com/eic/afterburner) with the right setting for example
```
  abconv -p ip6_hidiv_275x18 hepmc_Lambda1.dat
```

