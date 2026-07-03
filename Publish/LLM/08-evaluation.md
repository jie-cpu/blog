# multiple choice evaluation
- precision 
	- tp/(tp+fp)
	- numerator is tp
	- denominator is predicted to be true
	- 尽量选对
- recall
	- tp/(tp+fn) 
	- denominator is actually true
	- 尽量选全
- f1 score
	- (2* precision* recall)/ (precision + recall)
	- used to compute the harmonic mean of precision and recall 
- accuracy
	- (tp+tn)/(tp+tn+ft+tn) 
# open- ended generation evaluation
- 和选择题不一样，回答是开放式的，像写故事，对话生成，文本摘要等生成式内容，ai 创作新内容
- BERTScore is a model evaluation metric for text generation. It is based on cosine similarity between tokens in the candidate(generated text) and reference(ground truth) sentences and provides precision, recall and F1 score
# LLM - as - a Judge
- use cases: content moderation, automated grading, pairwise comparison