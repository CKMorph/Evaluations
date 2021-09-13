# Evaluations
This repository contains two datasets for evaluating the morphological analyzer of the Central Kurdish language.

## Analysis Evaluation
To evaluate the accuracy of a Central Kurdish morphological analyzer 1,000 unique tokens with their contexts are picked up randomly from the [AsoSoft text corpus](https://github.com/AsoSoft/AsoSoft-Text-Corpus).  If the random word was not a CK word, we replaced it by picking up another random one. Also, since we were not evaluating spelling correction, we corrected the spelling mistakes. Then the authors (all native speakers of Kurdish) manually checked the selected words within the given context, and they picked one correct morphological analysis for each word.

### Sample
| Result	| Word | Lemma | Analysis | Context|
|-|-|-|-|-|
| B | دینا | دینا | «دینا»[PROPN]{NE=Person} | یەکێک لە خەباتکارانی مافەکانی ژنانی میسری بەناوی دینا فەرید ڕادەگەیەنیت |
| C | دۆستۆیۆڤسکی | دۆستۆیۆڤسکی | «دۆستۆیۆڤسکی»[PROPN]{NE=Person}	| لە پەیوەندی لەگەڵ ئەو بەرهەمەدا دۆستۆیۆڤسکی دەچێتە سەردانی چیڕنیشیۆسکی. |
| A | ئەسپەکان | ئەسپ | «ئەسپ»[NOUN]«ەکە»{Definite=Def}«ان»{Number=Plur} | ئەسپەکان حەزیان لە خۆرە |


### Summary of Results
The following table shows the functional evaluation results of CKMorph (performed on 2021/05/05): 
| **Detection category** | **Tokens** | **Ratio** |
|-|-|-|
| **(A)** Correct analysis    | 959   | 95.9\% |
| **(B)** Irrelevant analyses | 5     | 0.5\% |
| **(C)** No analyses         | 36    | 3.6\% |
| Total               | 1000  |      |


## Coverage Evaluation
To evaluate the coverage of a morphological analyzer, it should be tested on real-world texts of a general corpus.
The coverage of CKMorph is evaluated on [the small version of AsoSoft corpus](https://github.com/AsoSoft/AsoSoft-Text-Corpus).
By purging the punctuation marks, the digits, and the tokens with non-Kurdish characters, we extracted 4,220,805 tokens. A frequency list was prepared to be analyzed by the morphological analyzer.

### Sample
| Frequncy | Detection Result | Token |
|-|-|-|
| 17858 | A | کوردستان |
| 5 | A | ئەگەڕایەوە |
| 4 | B | ناخۆشیەکانی |
| 45 | C | هەوڵبدەن |
| 2 | D | کۆتوزنجیری |
| 1 | X | سنۆن |

### Summary of Results
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
