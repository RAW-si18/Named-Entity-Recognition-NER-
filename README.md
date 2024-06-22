STILL IN DEVELOPMENT MODE




# Named Entity Recognition (NER)

## Introduction

NER is a subtask of information extraction that locates and classifies named entities in a text. The named entities could be organizations, persons, locations, times, etc. 

For example:

**Many French citizens are going to Morocco for christmas.**

Is labeled as follows: 

- French: geopolitical entity
- Morocco: geographic entity 
- Christmas: time indicator

Everything else that is labeled with an `O` is not considered to be a named entity.

## Exploring the Data

The original data consists of four columns: the sentence number, the word, the part of speech of the word, and the tags.  A few tags you might expect to see are: 

* geo: geographical entity
* org: organization
* per: person 
* gpe: geopolitical entity
* tim: time indicator
* art: artifact
* eve: event
* nat: natural phenomenon
* O: filler word

The `tag_map` is a dictionary that maps the tags that you could have to numbers. Run the cell below to see the possible classes you will be predicting. The prepositions in the tags mean:
* I: Token is inside an entity.
* B: Token begins an entity.

If you had the sentence 

**"Sharon flew to Miami on Friday"**

The tags would look like:

```
Sharon B-per
flew   O
to     O
Miami  B-geo
on     O
Friday B-tim
```

where you would have three tokens beginning with B-, since there are no multi-token entities in the sequence. But if you added Sharon's last name to the sentence:

**"Sharon Floyd flew to Miami on Friday"**

```
Sharon B-per
Floyd  I-per
flew   O
to     O
Miami  B-geo
on     O
Friday B-tim
```

Your tags would change to show first "Sharon" as B-per, and "Floyd" as I-per, where I- indicates an inner token in a multi-token sequence.
