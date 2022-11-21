# Structural modeling of KDM6A-TLE1 related interactions

This repository represents the structural modeling part of the "Truncated KDM6A exhibits differential chromatin occupancy and regulatory interactions" conducted by Gülden Özden Yılmaz, Busra Savas, Ahmet Bursalı, Aleyna Eray, Alirıza Arıbaş, Şerif Şentürk, Ezgi Karaca, Gökhan Karakülah, Serap Erkek-Ozhan. 

## Motivation

Here in this work, we aimed to find the interacting regions of KDM6A, TLE1, HES1, RUNX1-2, and HHEX to understand the potential arrangement of the biomolecular complexes they involved in. Checking the literature gave us the advantage to create the initial contact map of the interested proteins (see figure below). 

<img width="2024" alt="github-fig" src="https://user-images.githubusercontent.com/62547137/203048915-07c31303-b33a-4dd1-a54f-a859f91beabf.png">

Using this map, we modeled interacting protein pairs in domain-domain or domain-motif level. The details are listed in below:

- **KDM6A-TPR:TLE1-Q** interaction is modeled by using a reference structure, [6EJN](https://www.rcsb.org/structure/6EJN), showing the evidence of interaction in between TPR and coiled coils. [FATCAT](https://fatcat.godziklab.org/fatcat/fatcat_pair.html) server is used to obtain superimposed model.  
- **TLE1-Q:HHEX** interaction is modeled by [AlphaFold](https://github.com/deepmind/alphafold) multimer. Sequences of Q domain and the first N-ter 98 are used for TLE1 and HHEX, respectively.


- **TLE1-WDR:HHEX** is originated from WDR:EH1 complex, [2CE8](https://www.rcsb.org/structure/2CE8). The sequence of EH1 peptide, MFSIDNILA, is converted to FYIEDIL through modeling TLE1-WDR:HHEX complex by mutating the necessary amino acids. We improved the positions of side chains in the interface after implementing the mutations by [HADDOCK 2.4](https://wenmr.science.uu.nl/haddock2.4/submit/1).

- **TLE1-WDR:RUNX** complex is originated from WDR:WRPW complex, [2CE9](https://www.rcsb.org/structure/2CE9). The original WRPW peptide is mutated into WRPY peptide to form TLE1-WDR:RUNX interaction. Mutation implementation and refinement procedures also carried out by HADDOCK 2.4.

- **TLE1-WDR:HES1** interaction exists in [2CE9](https://www.rcsb.org/structure/2CE9) complex. Therefore, we only applied refinement to improve the interface with HADDOCK 2.4. 


## Our folders describe:

- **[AlphaFold](https://github.com/deepmind/alphafold):** contains the AlphaFold models. Input FASTA files and output files are provided.

  - **KDM6A-database**: *[Human KDM6A](https://alphafold.ebi.ac.uk/entry/O15550) model is retrieved from [AlphaFold-Database](https://alphafold.ebi.ac.uk/).*
  - **KDM6A-monomer**: *monomer_ptm is chosed as model preset during the modeling.*
  - **TLE1-Q_HHEX-multimer**: *multimer is chosed as model preset during the modeling.*
  
- **[HADDOCK](https://wenmr.science.uu.nl/haddock2.4/submit/1):** contains the HADDOCK refinement related files of TLE1-WDR containing complexes. Input PDB files, distance restraint file and outputs are provided for each complex.
  - **TLE1-WDR_HES1**: *Refinement of whole WDR domain and MWRPW peptide.*
  - **TLE1-WDR_HHEX**: *Refinement of whole WDR domain and MFYIEDILA peptide.*
  - **TLE1-WDR_RUNX**: *Refinement of whole WDR domain and MWRPY peptide.*
  
- **[FATCAT](https://fatcat.godziklab.org/fatcat/fatcat_pair.html):** contains the the input PDB files and superimposed structures.
  
## To clone the repository

```
git clone https://github.com/CSB-KaracaLab/XXXX.git
```
or if you would like to get the content directly via wget:
```
wget https://github.com/CSB-KaracaLab/XXXX/archive/master.zip
```

## Acknowledgements
This research is supported by EMBO installation grant (#4421). 

## Contact 
ezgi.karaca@ibg.edu.tr
