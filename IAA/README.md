## Format:
The IAA file coref-5-heb-iaa.jsonl is formatted as JSONL, where each line is specified as:
``{$annotator_1: $doc_1, ..., $annotator_N: $doc_N}``.
The documents within the same line are equivalent but annotated by different annotators.

## Metric:
We report the CoNLL-2012 F1 score [1].

## Hebrew:
CoNLL-2012 F1 score: 0.669; evaluated 148 pairs.

## References
[1] [Scoring Coreference Partitions of Predicted Mentions: A Reference Implementation](https://aclanthology.org/P14-2006) (Pradhan et al., ACL 2014)
