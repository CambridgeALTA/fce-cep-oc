# The FCE-CEP Open Cloze Test dataset

This repository contains the dataset described in: 

Mariano Felice, Shiva Taslimipoor and Paula Buttery. 2022. [**Constructing Open Cloze Tests Using Generation and Discrimination Capabilities of Transformers**]( http://arxiv.org/abs/2204.07237). In *Findings of the Association for Computational Linguistics (ACL 2022)*. Association for Computational Linguistics.

## Composition

This dataset is made up of the following files:

`original.json`

Original FCE open cloze tests with their gaps and answers (one per line).

`prediction.json`

Output of our extended multi-objective ELECTRA system for the sample tasks. Each line contains the tokens in the task, POS, dependency information, system confidence score and prediction (G: gap, O: no gap). The attribute "gold_labels" includes a list of the original labels (i.e. which tokens are gapped).

`ann_{1,2,3}.json`

Human annotations for our system output (one file per annotator). Judgements correspond to the each predicted gap in prediction.json in order, i.e. gap 1 in line 1 ann_*.json corresponds to the first predicted gap for the same task in prediction.json.

Human judgements consist of the following two attributes per gap:

`l`. Label, as follows:

- G:   Good
- TC:   Too close to other gaps
- TA:  Too many possible answers
- TP:  Too many gaps of this type
- DM:  Answers can change meaning
- DF:  Answers can have different POS
- D:   Gap depends on another
- R:   Repeated gap
- P:   Phantom gap
- UO:  Unacceptable outlier
- O:   Other (please specify)

`c`. Any additional comments by the annotator.

The order of the tasks is preserved across all files.

## Licence

This dataset is free to use for research purposes under the terms of the accompanying licence.

## Contact

If you have any questions, suggestions or bug reports, please contact the authors:

Mariano Felice, Shiva Taslimipoor, Paula Buttery

{mf501,st797,pjb48}@cam.ac.uk
