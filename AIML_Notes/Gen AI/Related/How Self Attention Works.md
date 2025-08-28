To understand self-attention, we first need to understand the limitations of the technology it replaced: static word embeddings.

A **word embedding** is a vector of numbers that represents the semantic meaning of a word. These are created by training neural network architectures (like **Word2Vec** or **GloVe**) on vast amounts of text, like all of Wikipedia.
The network assigns a dense vector to each word, for example:
- **king**: `[0.3, 0.9, 1.0, 0.0]`
Each number in the vector represents a learned feature of the word. The key advantage is that words with similar meanings will have vectors that are "close" to each other in this high-dimensional space. This closeness can be measured mathematically using **cosine similarity** or the **dot product**.

The major drawback of traditional word embeddings is that they are **static**. An embedding is generated once from the training data and is then used repeatedly. This means a word has only one vector representation, regardless of how it's used in a sentence.

This creates a problem for words with multiple meanings (polysemy). For example, the word "bank" has the same static embedding in both of these sentences, even though its meaning is completely different:
1. He deposited money in the **bank**.
2. He sat on the river **bank**.
## Process of Self Attention 
Self-attention solves the context problem by transforming static, context-free word embeddings into dynamic, context-dependent representations for each word in a sentence.
### First principle approach
Consider the sentence: "Humans Love Smartphones". The self-attention layer takes the initial static embedding for each word (e1​,e2​,e3​). After a series of calculations, it outputs a new set of vectors (y1​,y2​,y3​), where each output vector is now contextually aware and influenced by the others.
![[Pasted image 20250826210645.png]]

The key insight is that each new output vector is not just a modification of its original embedding, but a **weighted sum of information from all words** in the sentence. For example, the new, context-aware vector for "Love" (y2​) is conceptually formed by combining information from "Humans," "Love," and "Smartphones," with each word's contribution determined by a calculated weight.

Y2(Love) = 0.3\*e1(Humans) + 0.8\*e2(Love) + 0.4\*e3(Smartphones)

These weights (or coefficients) are calculated by measuring the similarity between words. This is done by taking the **dot product** of a **Query (Q)** vector from the current word and a **Key (K)** vector from the word it's being compared to. For example, the relevance score between "Love" (as the query) and "Humans" (as the key) would be calculated as:
0.3 = e2 . e1

To ensure the weights are consistent and sum to 1, these raw similarity scores are normalized using a **Softmax function**. This produces the final attention weights that are used to create the new output vector.

Here is the full structure of Self attention mechanism for "money bank grows"
![[Pasted image 20250826212353.png]]


Review of first principle approach:
1. Advantage | This is a parallel operation
A major advantage of self-attention is that it can be heavily **parallelized**. The contextual embedding for every word in a sentence can be calculated simultaneously, independent of the others.

This is a significant improvement over sequential models like RNNs and LSTMs. Using linear algebra and matrix operations, we can process all the words in a very long sentence at once, making the process incredibly fast and efficient, especially on modern hardware like GPUs.
![[Pasted image 20250826213055.png]]
However, this parallel approach creates a problem: the model loses all information about the **order of the words**. Without a way to account for syntax, the model would see "Humans Love Smartphones" and "Smartphones Love Humans" as the same thing. This issue is solved by adding **positional encodings** to the input embeddings.

2. Limitation: Lack of Task-Specific Learning

In this simplified model, there are no learned parameters like weights or biases. The context is derived purely from the fixed, mathematical similarity (dot product) between the initial static embeddings.

- **Consequence**: The contextualization is **general**, not **task-specific**. The model isn't learning from the patterns in the overall training data; it's only looking at the relationships within a single sentence based on pre-existing embeddings.
This leads to problems with nuanced language, like idioms. The model would likely translate "Break a leg" literally, because it has no learned parameters that have been trained on a translation dataset to understand that this phrase means "Good luck" in certain contexts.

To solve this, the next step is to introduce trainable **weights and biases**, which will allow the model to adapt and create task-specific contextual embeddings.