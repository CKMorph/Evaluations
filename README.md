# Evaluations
This repository contains two datasets for evaluating the morphological analyzer of the Central Kurdish language.

## Functional Evaluation
To evaluate the precision and recall of a Central Kurdish morphological analyzer 1K unique tokens with their contexts are selected randomly from  [AsoSoft text corpus](https://github.com/AsoSoft/AsoSoft-Text-Corpus). The spelling mistakes are corrected according to the standards of the Kurdish orthography. One correct analysis (according to the given context) is manually chosen by native speakers of Kurdish.

## Coverage
To evaluate the coverage of a morphological analyzer, it should be tested on real-world texts of a general corpus.
The coverage of CKMorph is evaluated on [the small version of AsoSoft corpus](https://github.com/AsoSoft/AsoSoft-Text-Corpus).
By purging the punctuation marks, the digits, and the tokens with non-Kurdish characters, we extracted 4,220,805 tokens. A frequency list was prepared to be analyzed by the morphological analyzer.

The following table shows the coverage evaluation results of CKMorph (performed on 2021/05/05): 
| **Detection** | **Analyzed Tokens** | **Coverage** | **Unique Tokens** | **Unique Coverage** |
|-|-|-|-|-|
| **(X)** Not detected | 191,912 | 4.5% |  79,677 | 23.8% |
| **(A)** Detected without corrections | 3,741,995 | 88.7% |  151,173| 45.2% |
| **(B)** Detected after common character corrections | 56,216 | 1.3% |  14,951 | 4.5% |
| **(C)** Detected after one split | 204,339 | 4.8% |  73,558 | 22.0% |
| **(D)** Detected after two splits | 26,343 | 0.6% |  15,296 | 4.6% |
| **Total detected** | **4,028,893** | **95.5%** | **254,978** | **76.2%** |
| *Total* | *4,220,805* |   | *334,655* |  
