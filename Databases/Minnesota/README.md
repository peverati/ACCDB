## Minnesota
### Minnesota Database 2015, 2015A, and 2015B (Truhlar's group), excluding geometries and solid state sets

**Taken from:** 

2015: Yu, H. S.; Zhang, W.; Verma, P.; He, X.; Truhlar, D.G. 2015, 17, 12146Ð12160. https://pubs.rsc.org/en/Content/ArticleLanding/2015/CP/C5CP01425E 

2015A: Yu, H.; He, X.; Truhlar, D.G.; J. Chem. Theory Comput. 2016, 12, 1280 https://pubs.acs.org/doi/10.1021/acs.jctc.5b01082 

2015B: Yu, H.; He, X.; Truhlar, D.G.; Chem. Sci., 2016, 7, 5032 http://pubs.rsc.org/en/content/articlelanding/2016/sc/c6sc00705h#!divAbstract.

The suggested basis set for each subset is reported below in square brackets (most non-conventional basis sets are also provided in the basis_sets folder).

**Subsets:**

*Main Group Bond Energies (MGBE150):*
- SR-MGM-BE9: Single-Reference Main-Group-Metals Bond Energies
	- SRM2: Single-Reference Main-group bond energies [MG3S]
	- SRMGD5: Single-Reference Main-Group Diatomic molecules [def2-TZVP]
	- 3dSRBE2: 3d single-reference metal-ligand bond energies [def2-TZVP(metal); ma-TZVP(non-metal)]
- SR-MGN-BE120: Single-Reference Main-Group-Non-metals Bond Energies [MG3S]
	- SR-MGN-BE107: Single-Reference Main-Group-Non-metals Bond Energies [MG3S]
	- ABDE13: Alkyl Bond Dissociation energies [ma-TZVP]
- MR-MGM-BE4: Multi-Reference Main-Group-Metals Bond Energies [cc-pCVQZ (metal); aug-cc-pCVQZ (non-metal); def2-TZVP (for K)]
- MR-MGN-BE17: Multi-Reference Main-Group-Non-metals Bond Energies [MG3S]

*Transition Metal Bonding Energies (TMBE33):*
- SR-TM-BE17: Single-Reference Transition-Metals Bond Energies [MG3S]
	- 3dSRBE4: 3d Single-Reference metal-ligand Bond Energies [def2-TZVP (metal); ma-TZVP (non-metal)]
	- SRMBE10: Single-Reference Metal Bond Energies [def2-TZVP]
	- PdBE2: Palladium complex Bond Energies [SDD-2fg (Pd); cc-pVTZ (non-metal)]
	- FeCl: FeCl bond energy [aug-pwCVTZ (Fe); aug-pVTZ (Cl)]
- MR-TM-BE13: Multi-Reference Transition-Metals Bond Energies 
	- 3dMRBE6: 3d Multi-Reference metal-ligand Bond Energies [def2-TZVP (metal); ma-TZVP (non-metal)]
	- MRBE3: Multi-Reference Bond Energies [def2-TZVP]
	- Others: CuH, CuCl, NiCl, and VO bond energies [aug-cc-pwCVTZ (metal); aug-cc-pVTZ (non-metal)]
- MR-TMD-BE3: Multi-Reference Transition-Metals Dimers Bond Energies [def2-TZVP]

*Barrier Heights (BH76):*
- HTBH38: Hydrogen Transfer Barrier Heights [MG3S]
- NHTBH38: Non-Hydrogen Transfer Barrier Heights [MG3S]

*Noncovalent Interactions (NC87):*
- NCCE23: NonCovalent Complexation Energies [MG3S]
- CT7: NonCovalent Complexation Energies with charge transfer [MG3S]
- NGDWI21: Noble gas dimer weak interaction [aug-cc-pVQZ]
- S6x6: Six dimers at six intermonomeric distances [def2-QZVP]

*Excitation Energies (EE18):*
- pEE5: p-block excitation energies [cc-pVQZ-DK; d-aug-cc-pVQZ-DK (F, Ar)]
- 3dAEE8: 3d transition metals Atomic Excitation Energies and first excitation energy of Fe [cc-pCVQZ (Ca); cc-pVQZ-DK]
- 4dAEE5: 4d transition metals Atomic Excitation Energies [cc-pVTZ-DK]

*Isomerization Energies (IsoE14):*
- 2pIsoE4: 2p Isomerization Energies [cc-pVQZ]
- 4pIsoE4: 4p Isomerization Energies [cc-pVQZ]
- IsoL6: Isomerization energies of Large molecules [MG3SXP]

*HydroCarbons ThermoChemistry (HCTC20):*
- HC7: Hydrocarbon Chemistry [6-311+G(2df,2p)]
- pTC13: ThermoChemistry of pi systems [MG3S]

*Others:*
- EA13: Electron Affinities [MG3S]
- IP23: Ionization Potentials
	- IP13: main group IPs [MG3S]
	- IPM10: IPs of Metals [For FeC: SDD+2fg for Fe, def2-QZVPP for C; all other metals: cc-pVQZ-DK]
- PA8: Proton Affinities [MG3S]
- DC9: Difficult Cases [MG3S]
- SMAE3: Sulfur Molecules Atomization Energies [MG3S]
- AE17: Atomic Energies [For H, He, B to Ne, Al to Ar: cc-pwCV5Z; for Li, Be, Na, and Mg: cc-pCVQZ]

**Not from Database 2015A (developed by TCC@FIT):**
- MN-RE: reaction energies from atomization energies of the Minnesota database  (developed in house based on the W4-11-RE script by R. Bartlett: http://pubs.rsc.org/en/content/articlelanding/2017/cp/c7cp00757d)
