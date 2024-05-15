# Bagel eval 

Difficult eval for AI models that predict designed enzyme function 


## Data files 

The primary data file is `dataset.csv`, which contains the following columns: 

- `kcat`. The experimentally measured turnover number. This has been compared to the baseline
   of 880 per minute for native BglB and log-transformed. `log(mutant/wt)`  
- `km`. Experimentally measured Michaelis constant, compared to baseline and transformed 
   by taking the log, so that higher numbers represent  `log(mutant/wt)` 
- `mutant`. The standard biochemical name for the mutant, such as "C167A" to indicate that
  the cysteine residue at position 167 is replaced with alanine. 
- `sequence` the full-length sequence of the mutant. The native sequence is [UniProt 
  entry P22505](https://www.uniprot.org/uniprotkb/P22505/entry)


## Evaluation metrics 

Predict the scalar value catalytic rate `kcat` for designed sequences. Evaluate by Spearman rank correlation. 

- In our paper, we achieve 0.57 using an elastic net model on features derived from molecular mechanical simulation of the enzyme–transition state complex. 

Predict the scalar value representing substrate binding affinity `km` for designed sequences. Evaluate by Spearman rank correlation. 

- In our paper, we achieve 0.68 using the same regularized linear model with features from molecular mechanics described above. 

