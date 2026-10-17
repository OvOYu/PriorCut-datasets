# Datasets for "When Integer Scores Tie: Top-N Ranking with Discrete Codes in Federated Recommendation"

This repository contains the four datasets and the three data splits used in the experiments of the paper.

| Dataset | Domain | Positive feedback | #Users | #Items | #User–item pairs | Origin |
|---|---|---|---:|---:|---:|---|
| ML1M | Movies | Rating > 3 | 6,040 | 3,952 | 575,281 | [MovieLens 1M](https://grouplens.org/datasets/movielens) |
| NF5K5K | Movies | Rating > 3 | 5,000 | 4,998 | 155,872 | [Netflix Prize](http://www.netflixprize.com) |
| XING5K5K | Jobs | Click, bookmark, reply | 5,000 | 5,000 | 78,294 | [XING](https://www.xing.com) |
| Amazon-KS | E-books | Rating > 3 | 9,862 | 11,298 | 245,458 | [Amazon review data, Kindle Store](https://jmcauley.ucsd.edu/data/amazon) |

\#Users and #Items are the sizes of the user and item ID ranges; the pairs are the positive pairs over the training, validation and test sets of one split.

## Files

```
datasets/<dataset>/<prefix>-copy<k>-<part>
```

- `copy<k>` is data split k of the paper (k = 1, 2, 3); `<part>` is `train`, `valid` or `test`.
- Each line is one positive user–item pair: `user_id item_id`, separated by a space.
- `SHA256SUMS.txt` lists the SHA-256 checksum of every file.

## Provenance

The files are byte-identical to the data files and splits released by Li et al. (2026) with the source code of FedHashRec (<https://github.com/YannickCodeHome/FedHashRec>, commit `e99a8a8`), whose experiments use the same splits. They follow the preprocessing of GBPR (Pan and Chen, 2013):

- NF5K5K: 5,000 users and 5,000 items sampled at random from the Netflix Prize data.
- XING5K5K: clicks, bookmarks and replies count as positive feedback; the 5,000 users with the most activity and the 5,000 items with the highest popularity are retained.
- Amazon-KS: ratings of electronic books in the Kindle Store category; records with at least ten interactions are kept.

## Terms of use

The data originate from the providers listed above, and their terms of use apply.
