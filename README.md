# il-graphene-ff

LAMMPS input files related to our paper on a polarizable force field for the IL/graphite interface (currently under review at *J. Phys. Chem. B*).
The repository is structured as follows:
1. [Interface Structure](./structure): contains the input files for the LAMMPS simulations used to analyze the structure of the IL/graphite interface (Figure 1 in the paper). 
There are subdirectories for [Case I](./structure/case-1) to [Case VI](./structure/case-6) of the paper. 
Each case contains a LAMMPS input file `input.lmp`, a data file `data*.lmp` and the pair potential files `pair_*.lmp`. 
These inputs were generated using [fftool](https://github.com/paduagroup/fftool) and [CONAN](https://github.com/kirchners-manta/conan) and manually modified as necessary.
2. [LJ Parameter Test](./lj_parameter_test/): input files for the 16 combinations of Lennard-Jones (LJ) paramters investigated, denoted by their numbers (e.g., [2-1](./lj_parameter_test/2-1/), as described in the paper). 
Again, the subdirectories contain the LAMMPS input file, data file and pair potential files.
3. 

General note: As outlined in the paper, multiple replica simulations were performed for all applications and Cases. 
In this repository, we only provide the input files for one of the replicas. The other replicas can be generated using the same input files by changing the random seed in the LAMMPS input file.

If further information is needed, please refer to the paper or contact us directly.