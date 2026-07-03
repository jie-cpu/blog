# Neural Machine Translation with Attention(English --German)
- data preparation and preprocessing 
	- goal: convert raw text pairs into tensors that can be fed to the model
	- tokenize source and target sentences
	- build vocabularies 
	- add special tokens 
	- pad/ trim to a max length
# Sequence-to-Sequence Models(Seq2Seq)
- it is designed to transform one sequence into another 
- translation, summarizing a paragraph, converting speech to text
- two components
	- Encoder: reads and processes the input sequence, one token at a time, as it reads, it updates the hidden state to capture the meaning of what it has seen so far, after the last token it produces a context vector which acts as a summary of the entire input
	- Decoder: generates the output sequence(the translated texts) using the context vector that encoder produced, it predicts one token at a time
# the bottleneck Problem
- the encoder compresses the whole input as a single fixed size vector, it may struggle to remember all the important details, especially for long or complex sentences
- making it hard for the decoder to reproduce accurate or fluent outputs when the input is lengthy
# Attention Mechanisms
- solution
	- to solve the bottleneck, using attention mechanisms instead of relying on a single vector 
	- the decoder learns to focus on different parts of the input sequence at each step
    3 types of attention
	- dot product attention (luong attention) and scaled dot product attention : scaled one prevents the attention in a reasonable range, softmax not so peaked
	- multi-head attention (used in Transformers)
	- self- attention encoder
- all modern mechanisms are built around 3 core components
	- Query --what we are trying to find information for, from decoder's current hidden state
	- Key: what each source position offers-- used for comparison with the key 
	- Value: the actual information retrieved from the encoder outputs
	- the attention mechanism compares the query with all keys (via dot products), applies a softmax to obtain weights and then takes a weighted average of the values
	- the idea is that the decoder looks at the encoder to decide which input words to focus on
- multihead attention: 
	- performs several scaled dot product attention in parallel. each head has its own learned projections of QKV allowing it to capture different types of relationships 
		- one head might focus on syntactic structure
		- another might capture semantic similarity 
		- others can model long range dependencies
	- finally the output of all heads are concatenated and projected to form a unified of richer contextual information
- self attention encoder 
	- the encoder itself can use attention to understand relationships within the input sentence because the input sequence serves as queries, keys and values at the same time, each token compares itself to all other tokens in the sentence to decide how much attention to pay attention to
- the core idea of transformer encoder is that it uses layers of multi-head self -attention followed by a small feed forward networks

# training the Seq2Seq Model 
- teacher forcing 
	- during training we dont always feed the decoder its own predictions because it will be slow 
	- with teacher forcing, feed a probability of p to the decoder of true token, with 1-p of probability of its own predictions 
	- the mix helps the model learn faster and prevents it from drifting too far when it makes mistakes
- mixed precision training 
	- when running on GPU, we can use Automatic Mixed Precision to speed up training
	- using 16 bit floating point numbers where possible, reducing memory usage and increasing efficiency 
	- keeping 32 bit precision for important operations like gradient updates
- visualizing attention weights
	- attention scores: weights that tell us where the model is looking when predicting each target word
	- heatmap diagonal pattern
	- for multihead attention: attention map for each head separately and average attention map across all heads
	- visualization helps us interpret what the model learned
- no attention model relies on a single context vector which can lose information on long sentences
- the attention models dynamically focus on different source words, offering both better performance and interpretability

# visualizing attention in a pretrained transformer T5.
- text to text Transfer Transformer 
- it uses self attention in both the encoder and decoder
- cross-attention between the decoder and encoder 
- multiple layers and heads each captures different linguistic patterns
- combine all these ideas into deep, scalable architectures that dominate modern NLP tasks such as translation, summarization and question answering