# Tokenization
- Tokenization: breaking down text into smaller units, which are called tokens, can be words, characters, or even sentences 
- character level tokenization 
	- handles out of vocabulary problem
- whitespace tokenization
	- semantic meaning are preserved 
- subword level tokenization -- Byte Pair Encoding(BPE algorithm) which builds a vocabulary of frequent character pairs
# word2vec
- word embeddings with Word2Vec
- 1. prepare a corpus
- 2. train Word2Vec(Skip-gram) using gensim.  It learns vector representations of words based on the context in which they appear, allowing similar words to have closer vectors in the embedding space
- 3. inspect vectors and similarities, we can visualize the embedding space with dimensionality reduction technique
# application 
- sentence similarity 
	- embeddings are vectors of numbers which means we can use mathematical operations  
	- by averaging the word vectors 
- classification task: sentiment analysis
	- movie reviews labeled as positive and negative, using word vectors as features
