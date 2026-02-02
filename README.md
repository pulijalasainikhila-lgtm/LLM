# LLM

Day 1

LLM understands and generates human-readable TEXT. It basically predicts next token in the sequence. Gen-AI is the combination of LLM's with Deep Learning which enable them to work with text as well as images, audios, videos, etc.

LLM's have two phases of training: pretraining and fine-tuning. The pre-trained models are the fundamental models like gpt's but if want to use the models for some domain specific tasks, fine tuning the models with appropriate data is required.

Understanding Transformers:
Step 1 - Giving input
Step 2 - Preprocess the input by breaking them into tokens and assigning every token an id
Step 3 - Preprocessed data is given to encoder which converts them into vector embeddings capturing the semantic mmeaning of the tokens.
Step 4 - The vector embeddings are passed to the decoder which also recieves already predicted tokens(partial output) as input and collectively it predicts the next token. 

BERT v/s GPT
-> BERT is Bidirectional Encoder Representations from Transformers which is trained to identify missing words in a sentence. It is bidirectional so it is a better choice for sentimental analysis.
By looking at the entire sentence from both directions, it can essentially capture relationships between words so it will have rich contexual understanding. It has only encoder.
-> GPT is Generative Pre-trained Transformer which is trained to predict the next token of a sentence. It works with only decoder.

Transformers can also be used for computer vision and they are called as vision Transformers. They have been less biased than the CNN's.Not all transformers are LLM's and vice-versa.

Understanding GPT's:
Zero-shot and few-shot learning
GPT's are unsupervised and auto-regressive. It generates one token at a time and every output(token generated) is given as an input to the next iteration. It has a decode-only structure. GPT is only trained for next word prediction but it can still perform all other. This behaviour is known as "emergent behavior".

Tokenization:
1. Splitting text into individual words and sub words
2. Give them id's
3. Convert them into vector embeddings
