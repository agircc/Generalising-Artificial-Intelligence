### Context Limitation Due to Autoregressive Mechanism

Description: Because LLMs generate text token by token in an autoregressive manner, they must process and attend to all prior tokens at each step. This leads to a quadratic scaling of computation and memory with context length.

Impact: Limits how much prior context (e.g., long documents, chat history) the model can handle in a single pass.

Research Directions: Efficient transformers (e.g., Longformer, FlashAttention, Mamba) aim to reduce this bottleneck.