# Coreference Project

האיגוד הישראלי לטכנולוגיות שפת אנוש
الرابطة الإسرائيلية لتكنولوجيا اللغة البشرية

The Israeli Association of Human Language Technologies
https://www.iahlt.org

Our coreference corpus for contemporary Hebrew, covering a variety of text types and genres.

## Introduction

The corpus consists of Weizmann popular science articles (43%); 910 heb articles from the All Rights
entitlements organisation  (12%), Bagatz court decisions (4%), Davar news
organisation (59%), Israel Hayom news organisation (5%), Knesset protocols
(4%), Weizmann popular science articles (4%), Hebrew Wikipedia entries (8%);.

The corpus has been annotated with morpheme-level mention spans,
assembled into coreference clusters with entity types.

## Data set

### The current release includes the following files (annotated documents):
- coref-5-heb.jsonl: Hebrew articles.
- coref-5-heb-unique.jsonl: Unique Hebrew articles (each article is annotated only once).

## Format

Each article is a single json record. Some articles have been doubly-annotated
for the purposes of inter-annotator agreement study, these articles appear
multiple times.

The jsonl structure is:
```
{
  text: str, 
  user: str,
  metadata: { source: str, doc_id: str, ... },
  clusters: [ {
    metadata: { name: str, entity: str }, 
    mentions: [ (int, int, dict) ]
  } ]
}
```

The `text` field contains the raw text of the original article. The top-level
`metadata` dictionary provides document-level metadata, minimally `source` and
`doc_id`.

The `clusters` field is a list of JSON cluster records each containing a
`metadata` and `mentions` field. The cluster-level `metadata` field has a name
for the cluster and its entity type. The `mentions` field is a list of triples:
the span indices of the text plus a metadata dictionary. We provide no
mention-level metadata in this release.

Not all clusters have been annotated for entity type; this will be completed in
a future release.

## Statistics
### coref-5-heb:
- Number of documents: 910
- Number of clusters: 28,141
- Number of mentions: 121,067
- Approximated number of sentences: 37,614
- Approximated number of unique sentences: 30,018

### coref-5-heb-unique:
- Number of documents: 658
- Number of clusters: 22,712
- Number of mentions: 97,804
- Approximated number of sentences: 30,018
- Approximated number of unique sentences: 30,018

## Code:
For a trained model, reproduction scripts, etc., [see repository](https://github.com/IAHLT/hebrew_coref).

## Acknowledgments

We would like to thank all the people who contributed to this corpus:

Emmanuelle Kowner
Israel Landau
Maayan Orner
Nick Howell
Noam Ordan
Omer Strass
Shahar Adar
Shira Wigderson
Yifat Ben Moshe
