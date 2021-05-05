# Antibiotic activity of small molecules

Based on a simple _E.coli_ growth inhibition assay, the authors trained a model capable of identifying antibiotic potential in compounds structurally divergent from conventional antibiotic drugs. One of the predicted active molecules, Halicin (SU3327), was experimentally validated _in vitro_ and _in vivo_. Halicin is a drug under development as treatment for diabetes.

## Summary

* Predicts **antibiotic activity** of small molecules
* Takes **compound structures** as input
* Trained with **experimental** bioactivity data against _E.coli_
* Based on a dataset of **>2,000** molecules
* Results **validated experimentally**
* Used for **drug repurposing**
* Identified a **novel broad-spectrum** antibiotic
* Published in *Stokes et al., Cell, 2020*: [10.1016/j.cell.2020.01.021]()
* Processed data can be downloaded [here](https://github.com/yangkevin2/coronavirus_data/blob/master/data/ecoli.csv)

## Specifications

* Input: SMILES string (also accepts an InChIKey string or a molecule name string) 
* Endpoint: _E.coli_ growth inhibition at 50 uM (0: inactive, 1: active)
* Results interpretation: 
    * 99 initial hits were identified from the Drug Repurposing Hub, with prediction scores ranging from 0.967 to 0.294. Accuracy of prediction (based on _in vitro_ growth         inhibition of _E.coli_) was 51%, and higher prediction score correlated with higher probability of growth inhibition.
    * Halicin prediction score was 0.3315
    * False Negative rate was estimated to be 3.17% (2 of the 63 lowest scoring molecules displayed _E.coli_ growth inhibition potential _in vitro_)
    * The WuXi antituberculosis library highest score was 0.37, and none of its molecules demonstrated _E.coli_ growth inhibition _in vitro_
    * Of the 23 selected molecules from the ZINC library (scores > 0.8), 8 displayed activity against at least one of the following: _E.coli, S. aureus, Klebsiella                 pneumoniae, A.baumannii_ and _P. aeruginosa_

## History

1. Model was downloaded on 28/04/2021 from [http://chemprop.csail.mit.edu/checkpoints]() following the direct link.
2. We opened an issue on GitHub [#128](https://github.com/chemprop/chemprop/issues/108#issuecomment-802245616) to be sure about feature scaling.
3. We duplicated `predict.py` and `scripts/save_features.py` scripts from chemprop GitHub repository.
4. Model was incorporated to Ersilia on 28/04/2021.
