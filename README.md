# General 

This file documents a general description of my work on the NLP final project.

# Author
```
Name:			Yiyan Zhang
```

# Objective

Test the performance of nerual network based Question Answering (QA) systems, and compare the models with or without attention mechanism on the SQuAD dataset (SQuAD1.1 and SQuAD2.0).

# Models Implemented and Tested

- BiDAF Model: A complex model (containing GloVe, CNN and LSTM) with bi-directional attention (Q2C and C2Q), published by University of Washington in 2016. The model is trained for 30 epochs on SQuAD1.1 and SQuAD2.0.
- Bi-LSTM Model: Referring to BiDAF but remove the bi-attention structure, extract features of the embedded sequence with bi-LSTM only.
- BERT Model: A transformer-based DNN model for comprehensive NLP tasks, created and published by Google in 2018. The model is fine-tuned for SQuAD1.1 and SQuAD2.0 locally based on download pre-trained model. Referring to SpanBERT.


# Simulation Results
```
		Model 	Bi-LSTM			BiDAF			BERT
Dataset			F1		EM		F1		EM		F1		EM
SQuAD 1.1		58.21	56.73	74.18	63.89	93.96	88.10
SQuAD 2.0		52.16	52.11	58.95 	55.34	87.53	84.33
```

# Analysis

The reason why BERT Model outperforms others:
- LSTM layer turns into bi-directional Transformer layer (self-attention structure).
- Pre-trained by masked token and next sentence, on a very large data set for language modeling, and fine-tuned for specific task then.
- Document-level corpus for better context perceiving.

# Submission Online

The result json file is submitted to CodeLab (https://worksheets.codalab.org/home) for online performance test.
```
- For SQuAD1.1:
	{"exact_match": 85.4872280037843, "f1": 92.06525821221844}

- For SQuAD2.0:
	{
	  "exact": 85.09222605912575, 
	  "f1": 88.16202969905443, 
	  "total": 11873, 
	  "HasAns_exact": 80.54993252361673, 
	  "HasAns_f1": 86.6983432214702, 
	  "HasAns_total": 5928, 
	  "NoAns_exact": 89.6215306980656, 
	  "NoAns_f1": 89.6215306980656, 
	  "NoAns_total": 5945
	}
```
