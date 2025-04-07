# il-graphene-ff

LAMMPS input files related to our paper on a polarizable force field for the IL/graphite interface (currently under review at *J. Phys. Chem. B*).
The repository is structured as follows:
1. [SAPT Calculations and LJ Parameters](./sapt): contains the input and output files of the SAPT calculations used to determine the interaction energy between the IL and graphite.
There are four subdirectories for the interaction energies between cicrumcoronene (`cc`)/dicircumcoronene (`dc`) and the IL cation (`c1c1im`) and anion (`bf4`), denoted by the components and separated by a dash (e.g., `cc-c1c1im`).
Each of these subdirectories has further subdirectories for the different distances between the molecules at which the SAPT calculations were performed, denoted by their distance (e.g., `3.0` for 3.0 Angstrom).
Additionally, there are subdirectories for the calculations of the multipole moments of all molecules (`gdma`) and for the calculation of the CHELPG charges of the ions (`chelpg`).
Based on the SAPT calculations, the LJ parameters were derived using a custom code, that can be inspected [here](https://github.com/kirchners-manta/ljfit).
2. [Interface Structure](./structure): contains the input files for the LAMMPS simulations used to analyze the structure of the IL/graphite interface (Figure 1 in the paper). 
There are subdirectories for [Case I](./structure/case-1) to [Case VI](./structure/case-6) of the paper. 
Each case contains a LAMMPS input file `input.lmp`, a data file `data*.lmp` and the pair potential files `pair_*.lmp`. 
These inputs were generated using [fftool](https://github.com/paduagroup/fftool) and [CONAN](https://github.com/kirchners-manta/conan) and manually modified as necessary.
3. [LJ Parameter Test](./lj_parameter_test/): input files for the 16 combinations of Lennard-Jones (LJ) paramters investigated, denoted by their numbers (e.g., [2-1](./lj_parameter_test/2-1/), as described in the paper). 
Again, the subdirectories contain the LAMMPS input file, data file and pair potential files.
4. [Surface Tension](./surface_tension/): input files for the surface tension simulations (see Supporting Information of the paper), performed for a [nonpolarizable](./surface_tension/nonpol/) and a [polarizable](./surface_tension/pol/) ionic liquid.
5. [Work of Adhesion](./work_of_adhesion/): as described very detailed in the paper and the Supporting Information, the work of adhesion was calculated for Cases I to VI. 
That includes the dispersion part (`disp`) for all cases and additionally, for Cases II, III and V, the induction part (`ind`).
To determine any part of the work of adhesion, the respective interaction was scaled from full to zero in 20 stages.
These stages are referred to by the percentage of their full value (e.g, `100`, `085`, `030`).


General note: As outlined in the paper, multiple replica simulations were performed for all applications and Cases. 
In this repository, we only provide the input files for one of the replicas. The other replicas can be generated using the same input files by changing the random seed in the LAMMPS input file.

If further information is needed, please refer to the paper or contact us directly.