1. Token: units of language made by Tokenizer；Token 是由分词器（Tokenizer）根据特定规则将文本拆分得到的最小语言单位，可能是一个词、词的一部分、标点符号或空格。它们是语言模型处理和学习的基础单位。
2. TokenEmbedding 是一个形状为 [50257, 768] 的矩阵 有50257个token 每一行都是一个token
3. 向量的维度就是里面数字的数量
4. TokenEmbedding is a matrix with (number of token) rows and (dimensions of each vector)columns. Each row represents 1 token in the form of a vector. 
5. Typical GPT-2 small model has 50257 tokens in its vocabulary, and each token is represented by a 768-dimensional embedding vector.
6. 在一个训练好的模型中：
每个 token ID 对应的 Token Embedding 是固定的 
每个 位置 index（比如第 0 位、第 1 位）对应的 Positional Embedding 也是固定的 


Input: "Hello world"

1.  Tokenizer cut input to tokens
    ["Hello", "world"] → token IDs: [15496, 995]

2.  search for TokenEmbedding[15496]（语义向量）based on token ID,
    search for PositionalEmbedding[0](位置向量) based on position index 
    add up these two matrixes we get Embedding for a token

3.  Transformer block
    a.  Masked Multi-head Attention
    b.  FeedForward
    
4.  Output layers