ACCDB: A Collection of Chemistry DataBases
==========================================

A collection of reliable, freely available, computational chemistry databases, and a set of tools for their manipulation and automation, released under GNU GPL license by Peverati's Theoretical and Computational Chemistry group at Florida Institute of Technology (TCC@FIT). ACCDB was created for the evaluation and parametrization of electronic structure theory methods (such as DFT and semi-empirical WFT methods), but it can be useful in many other areas of computational chemistry research (benchmarking, basis sets development and evaluation, data analysis, etc). **The total number of unique reference data points in ACCDB is 44,094** (all at a level of theory significantly higher than DFT), making it one of the largest collection of computed chemical energies at high-level accuracy.

## The current version of ACCDB is v1.0 and it includes the following databases:
- **MGCDB84**: Head-Gordon's database, version 2017 [4,986 data in 91 subsets].
- **GMTKN**: Grimme's main group thermochemistry, kinetics and noncovalent interactions database [1,664 data in 56 subsets].
- **Minnesota Database** (version 2015B, excluding geometries and solid state databases): Truhlar's database [471 data in 27 subsets].
- **DP284**: Head-Gordon's 2018 dipole and polarizabilities databases [284 data in 2 subsets].
- **Metals**: Collection of databases containing transition metals [210 data in 8 subsets].
- **W4-17**: Martin's Weizman 2017 database [203 data in 3 subsets].

PLEASE READ CAREFULLY THE "**HOW TO CITE**" SECTION BELOW WHEN CITING ANY OF THE DATABASES COLLECTED HERE!

## Structure
ACCDB is composed of the following directories:
- **Automation**: Containing all snakemake file to automate calculations.
- **Databases**: Main directory containing all the reference data (DatasetEval.csv), the list of the molecules pertaining to each database (Database.txt), and the original citation (README.md) for all databases, organized in subdirectories.
- **Geometries**: Containing all geometries for single-point energy calculations, in xyz file format (including charge and spin multiplicity).

ACCDB contains 10,049 geometry files in xyz format that require single-point energy calculations. These calculations will result in 7,829 "traditional" unique reference data points. Two new large reaction energies databases have been obtained using automatic generation, based on W4-17 and Minnesota, containing further 36,276 "non-traditional" reference data points (27,140 in W4-17-RE, and 9,136 in MN-RE).

The reference energies for each database or set are reported in a csv file named DatasetEval.csv (3 equivalent files are available in each directory, with reference energies in Eh, kcal/mol, and kJ/mol). In general, reference values have been obtained with high-level theoretical calculations, refer to each set for details. Each csv file also includes the stoichiometry coefficients and reference to the corresponding filename in the Geometries directory for each unique reference data point, and can be easily parsed for calculation of statistics.
The list of the molecules pertaining to each database or set are also reported in a txt file, and can be used to extract the relevant xyz files from the **Geometries** directory.

A full description of each database or set is given in the README file in the **Database** directory, including credits to the original work where it was first introduced. Please do read each of them carefully, especially when citing the data in published scientific materials. In case you have any doubts about citations when using any of the databases reported here, please do give credit to the original work **before** giving credit to us and this work. Credit to ACCDB and TCC@FIT is appreciated, but credit to the original author(s) is mandatory.

## Automation

Automation of the jobs and calculation of the statistics is achieved through snakemake workflows. Refer to the README in the **Automation** directory for detailed instructions on how to use it, modify it, and extend it.

## How to cite:
This work is published under GNU-GPL license and credit must be given to the authors of the original material, as appropriate. Most of the databases are collected from free sources on the internet, and we act only as a central repository for them. (If you are the author or the owner of one of such databases and want your data to be excluded from this repository, plese do contact us, and we will remove it immediately.)
Some databases and the automation workflows have been created by us, and are presented here for the first time. Such databases and software are subject to the same license and are freely available to use and modify, as long as proper credit is given to the ACCDB project (see below).
Everything in ACCDB is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. 

**Citations for published scientific material:**

*For pre-existing databases or subsets:* 

You **must** cite the appropriate original reference for each database, as indicated within each folder, and you can cite the ACCDB project in addition, if you find this useful. 

*For the following new features presented here for the first time:* 

If you are using MN-RE or W4-17-RE you should cite the ACCDB project (see below), **and** the original paper by R.Bartlett et. al., as indicated in the README of each database.  If you are using the Porphyrins subset you should cite the ACCDB project (see below), **and** the original papers by K. Pierloot et. al. where the benchmarks where obtained, as indicated in the README of each database.  If you are using any of the automation scripts you should cite the ACCDB project (see below), **and** the snakemake original article.

*The reference for the ACCDB project is*: 

Morgante, P; Peverati, R.; J Comput Chem, 2018, XXX (*submitted*)


## Versions:

**v1.0 (08.2018)**: Initial public release

*v0.3 (07.2018)*: Addition of GMTKN

*v0.2 (06.2018)*: New Metals section with many subsets

*v0.1 (04.2018)*: Initial internal release


