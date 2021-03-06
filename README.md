# Document retrieval for social sciences

This package provides a simple method to retrieve documents from large text corpora. For use in social  
sciences. It accompanies the paper [Finding democracy in big data: document retrieval using word-embedding] and is an implementation of the algorithm described in the paper.

### Manual

To create tfidf metrics, first pass the documents in list form to the class DocumentRetrieval at initialization. 
You can either pass a created word2vec model to the class, or let the algorithm train word embeddings for you. 
Then use the function calculate_similarity() with a keyword fo your choice to calculate the similarity between 
the documents and the query. This function will return a list of scores for each of the documents passed to the 
class at initialization.

You can use a multiple words query by simply passing it in a string format to the calculate_similarity() function.

### Proposed usage:

```python

from retfidf import doc_retrieval

df = pd.read_csv('corpus.csv')

emb_sim = doc_retrieval(df['text'])

query = 'democracy'

df['democracy_metrics'] = emb_sim.calculate_similarity(query)  
```

#### GITHUB
https://github.com/hplisiecki/document-retrieval-for-social-sciences
