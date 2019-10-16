# Language Tech Problems
### solved
- spam detection
- parts-of-speech (POS) tagging ex. adj, noun, verb...
- Named entity recognition (NER) ex. extract people, org, location, from a sentence

### partially solved (medium effort to implement)
- Sentiment analysis
- Co-reference resolution [example](https://nlp.stanford.edu/projects/coref.shtml)
- Word sense disambiguation (WSD) ex. mammal mouse vs computer mouse
- parsing
- Machine Translation (MT) 
- Information extraction (create event date from email)

### cutting edge, high effort
- question answering
- paraphrase ( or associating 2 sentences that mean the same thing)
- summarization
- CG dialog

In general, language ambiguity is what makes NLP hard -- things we process 


# Regular Expressions (regex or regexp)
a sequence of characters that define a search pattern to be searched within a longer text.

A powerful, fundamental tool used in NLP 
- lexers 
- on off matches
The : [^A-Za-z][Tt]he[
phone number : (^\+[0-9]{2}|^\+[0-9]{2}\(0\)|^\(\+[0-9]{2}\)\(0\)|^00[0-9]{2}|^0)([0-9]{9}$|[0-9\-\s]{10}$)
https://regexr.com/

# Text Normalization

## Tokenization (segmentation)

### using `tr` and other unix tools: 
-n option to sort means
to sort numerically rather than alphabetically, 
-r option means to sort in reverse order (highest-to-lowest):

`tr -sc ’A-Za-z’ ’\n’ < sh.txt | tr A-Z a-z |sort | uniq -c | sort -n -r`

27378 the
26084 and
22538 i
...

### relation to NER
Depending on the application, tokenization algorithms may also tokenize multiword expressions like New York or rock ’n’ roll as a single token, which requires a multiword expression dictionary of some sort. Tokenization is thus intimately tied up with named entity detection, the task of detecting names, dates, and organizations 

### Lemmatization
- reduce inflections to base form
- find the correct dictionary headword form

### Morphology
- the study of morphemes: the smallest units that make up words
- stems: core meaning bearing units
- affixes: bits and pieces adhered to stems

### stemming:
- reduce terms to steps in information retrieval
- e.g. automates, automatic, automation reduced to "automat"

- Porter's algorithm is the most common english stemmer
- it's a series of steps and rules that reduce words to stems

# Sentence Segmentation
- define sentence boundaries
- some cases are easy (?, !), some cases are hard (like '.')
- use classifiers (handwritten rules, regex, ML, decision trees) to define the End 
Of Sentence (EOS)

### feature examples:
- case of word ending in period
- case of work after
### numeric features
- length of word
- trained using corpus: Probability(word with . is EOS)

Choosing features of a classifier to improve performance is the fun part.








