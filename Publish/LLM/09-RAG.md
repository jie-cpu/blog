# retrieval augmented generation
- a combination of a retrieval model(search engine) and a LLM
- retrieval model is used to find relevant documents based on a given query
- the llm is provided with top k most relevant document as context and then generates an answer based on the documents provided
- perplexity is based on rag
- gpt, gemini and claude can also use rag(but often you have to provide)
- RAG works pretty well for SAQ questions
# short answer question
- cultural question answering
# information retrieval
- index for key words
- query (ask a question)
- match (according the query, select the important info in the corpus)
- sort (score based on the similarity)
for the match part, there are two methods
- sparse retrieval
	- match exact or near - exact terms or key words between query and documents 
- dense retrieval
	- encode query and document into vector embeddings that can capture semantic meaning rather than exact wording 
- hybrid retrieval
	- combine strength of both sparse(fast and exact but no synonyms) and dense retrieval (semantic but slower)models
# Post - Generation Attribution
- first, llm generates an answer to a given query using only its knowledge without consulting external sources
- second, a retrieval system is invoked to search for relevant evidence, using original query, the generated answer or both
- the retrieved evidence is evaluated and incorporated to revise, refine or validate the initial model output
- the final answer is generated as a combination of the initial output and the supporting evidence found through retrieval

