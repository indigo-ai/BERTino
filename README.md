#BERTino: an Italian DistilBERT model

This repository hosts BERTino, an Italian DistilBERT model pre-trained by
[indigo.ai](https://indigo.ai/en/)
on a large general-domain Italian corpus. BERTino is task-agnostic and can be 
fine-tuned for every downstream task.


###Corpus
The pre-training corpus that we used is the union of the
[Paisa](https://www.corpusitaliano.it/) and
[ItWaC](https://corpora.dipintra.it/public/run.cgi/corp_info?corpname=itwac_full)
corpora. The final corpus counts 14 millions of sentences for a total of 12 GB
of text.

###Downstream Results
To validate the pre-training that we conducted, we evaluated BERTino on the
[Italian ParTUT](https://universaldependencies.org/treebanks/it_partut/index.html),
[Italian ISDT](https://universaldependencies.org/treebanks/it_isdt/index.html),
[Italian WikiNER](https://figshare.com/articles/Learning_multilingual_named_entity_recognition_from_Wikipedia/5462500)
and multi-class sentence classification tasks. We report for comparison results
obtained by the [teacher model](https://huggingface.co/dbmdz/bert-base-italian-xxl-uncased)
fine-tuned in the same tasks and for the same number of epochs.

**Italian ISDT:**


| Model        | F1 score | Fine-tuning time | Evaluation time |
|--------------|----------|------------------|-----------------|
| BERTino      | 0,9801   | 9m, 4s           | 3s              |
| Teacher      | 0,983    | 16m, 28s         | 5s              |

**Italian ParTUT:**

| Model        | F1 score | Fine-tuning time | Evaluation time |
|--------------|----------|------------------|-----------------|
| BERTino      | 0,9268   | 1m, 18s           | 1s             |
| Teacher      | 0,9688    | 2m, 18s         | 1s              |

**Italian WikiNER:**

| Model        | F1 score | Fine-tuning time | Evaluation time |
|--------------|----------|------------------|-----------------|
| BERTino      | 0,9038  | 35m, 35s           | 3m, 1s             |
| Teacher      | 0,9178    | 67m, 8s         | 5m, 16s              |

**Multi-class sentence classification:**
| Model        | F1 score | Fine-tuning time | Evaluation time |
|--------------|----------|------------------|-----------------|
| BERTino      | 0,7788   | 4m, 40s           | 6s             |
| Teacher      | 0,7986    | 8m, 52s         | 9s              |
