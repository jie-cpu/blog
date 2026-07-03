# overview 
- UV
	- morden python package manager
	- 10-100x faster than pip
- self-attention: every token in the sentence looks at every other token to understand context
	- the attention score --- dot product ---determines how much each token should focus on others
- masked self attention: preventing future peeping
	- by adding a mask, when predicting the next word, you can only use past context not future words
- cross attention: common in encoder-decoder models where the decoder attends to encoder outputs
	 - applied in language translation, summarization
# architecture types
## encoder only architecture
- encoder only
	- uses bidirectional self- attention. Every token can attend to every other token (past and future)
	- use cases: classification, named entity recognition, question answering where needs full context
	- BERT and RoBERTa
- encoder variants
	- bi- encoder -- block diagonal structure
		- separate encoding, no interaction until the final comparison
		- independent attention
		- compare embeddings
		- fast but lower accuracy 
		- use case: semantic search, finding similar documents
	- cross - encoder -- full matrix all tokens interact
		- concatenate both sequences together with joint attention, direct interaction between all tokens
		- single encoder 
		- multi-head attention plays a big role
		- higher accuracy but slower
		- use case: re-ranking, precise comparison
## encoder - decoder architecture
- encoder: bidirectional self-attention(understand full input context)
- decoder: masked self attention(track all generation history, what it already generated) + cross attention to encoder(access input information, what the input says)
- use case: translation, summarization, any seq to seq task
- examples: T5, BART, original transformer
## decoder-only architecture
- uses only masked self attention(each token can only see previous tokens)
- no encoder, no cross attention
- just autoregression generation
- use cases: GPT series, LLaMA, claude