# intro
- what is llm?
	- A language model is a type of artificial intelligence (Al) system designed to understand, generate, and manipulate human language. At its core, a language model predicts the next word in a sequence of words, based on the words that came before it. By doing this, it can produce coherent and contextually relevant text, answer questions, translate languages, summarize content, and even have conversations.
	-  LLMs are statistical models that learn a probability distribution over a sequence of words and that predict the next token for a given input.
- LLM's application?
	- NLP, data management and Machine Learning
# word representation
1. What is meant by sparse vs. dense embeddings? What are advantages of either?
	-   **Sparse (e.g., TF-IDF):** High-dimensional; dimensions represent specific words; mostly zeros.
	- **Dense (e.g., BERT):** Low-dimensional; every entry is a non-zero real number.
	- **Advantages:**
    - **Sparse:** Strong **exact keyword matching**; highly interpretable.    
    - **Dense:** Strong **semantic understanding**; captures relationships between different words.
2. What is meant by normalization of embeddings by vector length, versus by IDF? Why do both matter?
	-  Eliminate the influence of document length.
	- Distinguish term importance by rewarding rare words and penalizing frequent words.
	- **IDF ensures precision (keywords), while length normalization ensures fairness (comparison).**
3. Why do we need dedicated tokenizers? Why not just split at word borders?
	- Splitting on spaces is too naive. Dedicated tokenizers handle **subwords, punctuation, multilingual texts, normalization, and mapping to model vocabularies**, making them essential for modern NLP. 

![[Pasted image 20260204021008.png]]
# Data
1. Which three kinds of training data do LLMs need?

2. Where can we get each from?

What can we synthesize?

3. What are important filters on web data?

![[Pasted image 20260204023439.png]]
# training
1. What is the relation between parameters, data, training time, and LLM performance?

2. If you were to lead the development of GPT-6, how would you make design choices
regarding model hyperparameters?
3. How many days to train a 1B model on 1B tokens, on a normal laptop (100 GFLOPs)

![[Pasted image 20260204023824.png]]

# evaluation
- 1. Why do we want to evaluate LLMs? What differing goals can we have?

2. What are common metrics to evaluate LLM responses?

What is the challenge in long-answer evaluation?

3. Why is it so difficult to design durable benchmarks?

![[Pasted image 20260204024124.png]]

# RAG
1. What advantages does RAG offer over LLMs in isolation?

2. Why do we need query expansion and reformulation?

3. What are important parameters in modern RAG systems?

![[Pasted image 20260204024721.png]]
# application

![[Pasted image 20260204025031.png]]
# Vision LLMs
![[Pasted image 20260204025113.png]]
# Agents

![[Pasted image 20260204025234.png]]