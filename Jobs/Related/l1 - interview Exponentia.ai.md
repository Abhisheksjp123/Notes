Ok Interviewer was Mayank Kumar
Senior GenAI Engineer

First half of the interview was on GenAI
1. what type of transformer architecture is mistral, llama, 
   Encoder decoder or both
>[!Ans]-
>**Mistral** and **LLaMA** are both **decoder-only** transformer architectures, not encoder-decoder.
Here's the breakdown:
**Decoder-Only Architecture:**
>- **LLaMA (Large Language Model Meta AI)** - Uses a decoder-only transformer with modifications like RMSNorm, SwiGLU activation, and rotary positional embeddings (RoPE)
>- **Mistral** - Also decoder-only, incorporating techniques like sliding window attention and grouped-query attention for efficiency
>- **Key Characteristics of Decoder-Only Models:**
>- Designed for autoregressive text generation (predicting next token)
>- Use causal/masked self-attention (can only attend to previous tokens)
>- Optimized for tasks like text completion, conversation, and instruction following
>- Single unified architecture that can handle various NLP tasks through prompting
This is the same architecture family as GPT models (GPT-3, GPT-4), which revolutionized the field by showing that decoder-only models could excel at diverse language tasks without needing separate encoder-decoder architectures.
**Encoder-Decoder models** (like T5, BART) are less common in the current LLM landscape, as decoder-only architectures have proven more versatile and scalable for general-purpose language modeling.

2. Something on temperature
3. What are non linear functions like relu, leaky relu and sigmoid used as activation function
4. How can large context of tokens can be used for training the new models

Second half was on python
1. a = [1,2,3]
   b = [1,2,3]
	print(a == b)
	print(a is b)
	
	my ans - first true second false


2. what are decorator
>[!Ans]-
>**Decorators** in Python are a powerful feature that allows you to modify or extend the behavior of functions, methods, or classes without permanently changing their code. They're essentially functions that take another function as input and return a modified version.

3. Have you ever used flask
4. Can you use list as a key in dictionary

