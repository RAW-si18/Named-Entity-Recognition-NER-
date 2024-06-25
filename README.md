# Named Entity Recognition (NER)

## Introduction

Named Entity Recognition (NER) is a crucial task in natural language processing (NLP) that identifies and categorizes named entities in text into predefined categories such as organizations, persons, locations, dates, etc.

### Example:
Consider the sentence:

**"Many French citizens are going to Morocco for Christmas."**

NER labels this as:

- French: geopolitical entity
- Morocco: geographic entity
- Christmas: time indicator

Tokens not recognized as named entities are labeled with `O`.

## Exploring the Data

The dataset consists of four columns: sentence number, word, part-of-speech tag, and the NER tags. Examples of NER tags include:

- geo: geographical entity
- org: organization
- per: person
- gpe: geopolitical entity
- tim: time indicator
- art: artifact
- eve: event
- nat: natural phenomenon
- O: not a named entity

The `tag_map` dictionary maps these tags to numerical indices for prediction.

### Tagging Convention:

Tags indicate if a token is the beginning (`B-`) or inside (`I-`) of an entity. For instance, in the sentence:

**"Sharon Floyd flew to Miami on Friday."**

The tags would be:

- Sharon B-per
- Floyd I-per
- flew O
- to O
- Miami B-geo
- on O
- Friday B-tim

If "Sharon Floyd" were part of the sentence, "Floyd" would be tagged as `I-per` indicating it's inside the person entity initiated by "Sharon".
