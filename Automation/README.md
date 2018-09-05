# Automation

Automation of the jobs is achieved through snakemake workflows. Follow the instructions on the following website to install snakemake and its dependencies (http://snakemake.readthedocs.io/en/stable/index.html). Suggested installation is through conda. Modifications of snakefiles and extension for specific purposes is straightforward using snakemake (python-like) syntax.

A simple run of some or all subsets requires just a few modifications in the config.yaml file. More substantial modifications must be done in the snakefile directly.

### Required steps for a simple run:
1) Create a mol_list directory and copy in it the list of all the subsets that you want to run (make sure they have the .txt extension).
2) Copy a template file to the working directory (or create a new one).
3) Modify the config.yaml file:
    - Select the method(s) and the basis set(s) you are going to use.
    - Specify the pathways of the input/output files, the geometries folder, and  the the mol_list directory.
    - Indicate the name of the template file (it must be in the working directory).
    - Select the program call, the number of processors/cores/threads to be used for each single-point calculation, and eventually the regexp used for extraction of the final energies.
4) use <code>snakemake</code> to run all calculations. Useful (highly recommended but not required) flags that can be combined are:
    - <code>snakemake -k</code> to ignore unsuccessful jobs (and also for resubmission of failed workflows, without repeating previously completed jobs).
    - <code>snakemake -j #of_jobs_running_in_parallel</code> to run # jobs in parallel (do not confuse this with NPROC, explained below). The -j flag is used for specifying the number of threads for a snakemake workflow. In our case, where we usually choose the number of processors/cores/threads for each qcengine job (the time-consuming part of the workflow) in the template file, the -j flag is useful to select how many qcengine jobs are run at the same time (dirty trick, but it works fine if the maximum number of processors/cores/threads of the machine is not exceeded). For example, on a 32 threads machine (16 physical cores, 1 processors) we can run 1 qchem job on 32 threads by selecting <code>qchem -nt 32</code> in the snakemake file and launching <code>snakemake</code> (qchem jobs will run sequentially), or 2 jobs at 16 threads at the same time by selecting <code>qchem -nt 16</code> in the snakemake file and launching <code>snakemake -j 2</code> (two qchem jobs will run simultaneously and independently with 16 threads each), or every other combination.

### Details of the keywords in the configfile (config.yaml)
Use conventional yaml syntax (e.g. make sure to use one '-' and one space before each list of keywords (e.g. '- HF', and not '-HF')

-- **TEMPL1**: Template file for the quantum chemistry engine (sample .tmpl files are provided for Gaussian and Q-Chem)

-- **METHODS**: List of methods (e.g. - HF, MP2, PBE, etc.)

-- **BASES**: Similar to METHODS, but for basis sets

-- **OTHERS** [optional, leave it empty if not used]: Open for any use (e.g. RHF or UHF, SG1 or SG2 integration grids, etc.)

-- **GEOMETRIES_DIR**: This is the directory used to get the xyz files for all calculations.

-- **OUTPUTS_DIR**: This is the directory where all input and output files are going to be collected as OUTPUTS_DIR/{method}/{basis}/{molecule}/

-- **MOL_LIST_DIR**: This is the directory where a list of all databases 

-- **PROC**: Number of threads or cores or processors (depending on the machine and the quantum chemistry engine) for the quantum chemistry engine 

-- **QCENGINE_CALL**: The shell call to the quantum chemistry engine (examples for Q-Chem and Gaussian are provided)

-- **REGEXP** [optional, used only if you want to print final energies to a file]: The regular expression used to extract the final calculated energies from each output file (examples for Q-Chem and Gaussian are provided)

### Details of the Snakefile workflow
The Snakefile is used to generate all input files from a list of molecules and a set of xyz files containing the geometry of the molecules, to run all the calculations using a quantum chemistry engine (Q-Chem and Gaussian have been tested and included, extension to other program is straightforward and requires just small modifications to the configfile - see above), and to print all the final calculated energies into a csv file.

Below are the main rules defined in the Snakefile that can be run either in sequence (rule ALL, or no rule specified) or individually:

-- **rule QCENGINE_INPUT**: Generates all input files based on the configuration of the configfile 

-- **rule QCENGINE_RUN**: Run the quantum chemistry engine for all input files

-- **rule ALL_ENERGY_PRINT**: Extract all final energies and print them in a csv file named {method}_{basis}_energy.csv
