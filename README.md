# LLM

Day 1

Understanding LLM's
LLM understands and generates human-readable TEXT. It basically predicts next token in the sequence. Generative AI is a broader category that includes LLMs and other deep learning models (for images, audio, video, etc.)
LLM's have two phases of training: pretraining and fine-tuning. The pre-trained models are the fundamental models like gpt's but if want to use the models for some domain specific tasks, fine tuning the models with appropriate data is required.

Understanding Transformers:
Step 1 - Giving input
Step 2 - Preprocess the input by breaking them into tokens and assigning every token with an id.
Step 3 - Preprocessed data is given to encoder which converts them into vector embeddings capturing the semantic mmeaning of the tokens.
Step 4 - The vector embeddings are passed to the decoder which also recieves already predicted tokens(partial output) as input and collectively it predicts the next token. 
Transformers can also be used for computer vision and they are called as vision Transformers. They model global relationships better than the CNN's. Not all transformers are LLM's and not all LLM's are transformers.

BERT v/s GPT
-> BERT is Bidirectional Encoder Representations from Transformers which is trained to identify missing words in a sentence. It is bidirectional so it is a better choice for sentimental analysis.
By looking at the entire sentence from both directions, it can essentially capture relationships between words so it will have rich contexual understanding. It has only encoder.
-> GPT is Generative Pre-trained Transformer which is trained to predict the next token of a sentence. It works with only decoder.

Understanding GPT's:
Zero-shot and few-shot learning
GPT's are self-supervised and auto-regressive. It generates one token at a time and every output(token generated) is given as an input to the next iteration. It has a decoder-only structure. GPT is only trained for next word prediction but it can still perform all other. This behaviour is known as "emergent behavior".

Tokenization:
1. Splitting text into individual words and sub words
2. Giving them id's
3. Converting them into vector embeddings

Day 2

There are three types of tokenizations:
1. Word-based tokenization - Advantages -> can capture the meaning of the words.
                             Disadvantages -> can cause problems for unknown words in input, similar words like bag, bags can have completely different vector embeddings.
2. Character-based tokenization - Advantages -> very small vocab size
                                  Disadvantages -> can't capture semantic meaning of the word
3. Subword-based tokenization - RULE 1: if a word/subword is occuring frequently, don't split it.
                                RULE 2: Rare words are split into smaller frequent pieces.
                                Advantages -> can have similar vector embeddings for similar words hence captures the semantic meaning more accurately.
                                Disadvantages -> longer token sequences.

Byte pair encoding (BPE)
It is an algorithm which is based on subword-based tokenization.
first it starts by making a frequency distribution of all the characters in the input text. Then, it looks at the most frequently appearing byte pair and replaces them with merged characters and recalculates the frequency of the occurance of those individual characters. This process is repeated until common words stay as tokens and rare/unseen words are broken into smallest possible tokens.

Input-target data pairs:
After tokenizing the entire input, we can take two lists: x and y. If the input is the first 3 tokens the output would be the fourth token. This is how the prediction happens. So, x[:i] is the ith token of list y (y[i]).

Token Embedddings:
Token embeddings are matrices of size (vocab_size, dimensions). Each token in the vocabulary will be corresponding to an array of n dimensions and all the weights in the matrix are randomly generated. The torch library in python gives an embedding matrix which acts like a lookup matrix.

Positional Encoding:


