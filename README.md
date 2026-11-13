# pm1 data analysis

Analysis notebooks for the Piecemaker archive of The Forsythe Company. Piecemaker was a web-based documentation tool developed by David Kern and used by the company between 2008 and 2014. It links timestamped free-text annotations to video recordings of rehearsals and performances. Annotations and video were captured simultaneously during rehearsals and synchronized via Kern's web application. The notebooks belong to my dissertation, where the interpretation of the results can be found.

## About this repository

This repository was set up for publication and is not the one in which the notebooks were developed. The history of the working repository shows parts of the archive data that are not public, so the notebooks were cleaned and committed here anew.

## Data

The annotation data are not public, so the database export the notebooks read (`pm1-tfc-2016-events.csv`, `pm1-tfc-2016-pieces.csv`) is not part of this repository. The notebooks are committed in executed form instead: all results, tables and figures are visible without the data.

`brown_lemma_freq.csv` (lemma frequencies of the Brown corpus) is included, so that the keyness reference works without rebuilding it. `figures/` holds the figures and tables used in the dissertation (German labels, print size), written by the last cell of the two per-production notebooks and of the gaps notebook.

## Notebooks

- `pm1_archive_analytics.ipynb`: metadata (scope, authorship, video durations, text lengths)
- `pm1_archive_gaps.ipynb`: gaps and unclear data (empty fields, entries without author, videos without notes, recording days, implausible values)
- `nlp_analysis_sider.ipynb`: *Sider* (2011); word frequencies, terms over time, correlation, word pairs, keyness against the Brown corpus, BERTopic
- `nlp_analysis_ta2.ipynb`: *Theatrical Arsenal II* (2009); same pipeline, German figure labels
- `nlp_archive_wide_analysis.ipynb`: keyness of each production against all others

## Environment

```
conda env create -f environment.yml
```

The spaCy model (`en_core_web_sm`) and the NLTK data are downloaded on first use.

## A note on the code

These notebooks also reflect my own self-taught use of Python and pandas. For much of it I followed online documentation, tutorial videos and existing examples found on the web. In practice, whenever I ran into errors or problems I could not resolve from those sources, I found it pragmatic to turn to large language models for help. The NLP and text-mining methods themselves were chosen deliberately and independently, on the basis of the relevant scholarly literature. One of them I did not implement myself: the functions that compute Dunning's log-likelihood ratio (G²), `compute_g2` and `g2_vec`, were written with a large language model.
