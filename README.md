# Introduction

This is a Twitter data set of tweets that contains keywords beijing and shanghai. This project is expected to be used as research material for NLP studies.

These data sets contains

- 294923 public tweets that have the keyword `beijing`
- 297784 public tweets that have the keyword `shanghai`

during the period of `2021-10-01 00:00:00 (UTC)` to `2022-01-03 22:05:09 (UTC)`.

Please notice that all personal information has been wiped to the greatest extent possible.

# Data Example

Each tweet is presented in this data set as a `json` object in the following structure.

```json
{
    "date": "2022-01-03T22:05:09+00:00",
    "lang": "in",
    "content": "🔷210927 \n\nShanghai ✈️  Beijing\n\n🛬Beijing\nhttps://t.co/OgDGuSbX75 https://t.co/IlUlGtxUVR",
    "replyCount": 0,
    "retweetCount": 0,
    "likeCount": 0,
    "quoteCount": 0,
    "user_verified": false,
    "user_followersCount": 10511
}
```

The key names should explain themselves.

Each file in this project is a `jsonl` file that is [ndjson](http://ndjson.org/) format compatible.

# Tutorial

A brief guide to importing data is shown below.

- Python

```python
import json

with open(R"beijing.json", 'r', encoding='utf8') as f:
    lines = f.read().strip().split('\n')

for line in lines:
    tweet = json.loads(line)
```

- R

```r
library("jsonlite")

beijing = jsonlite::stream_in(file("beijing.json"), pagesize = 10000)
```

