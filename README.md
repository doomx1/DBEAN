# Dynamic Bidirectional Elman Attention Networks (DBEAN)  
**A Hybrid Framework for Efficient and Interpretable Text Classification**  

### Acknowledgments 
We would like to express our gratitude to the MindSpore Community for their inval-uable support and resources throughout this research. Thanks for the support provided by MindSpore Community

---

## Method Overview  
DBEAN addresses limitations of traditional recurrent neural networks (RNNs) and transformer-based models by integrating **bidirectional temporal modeling** with **adaptive self-attention mechanisms**. The core design balances computational efficiency, contextual depth, and interpretability through three synergistic components:  

### 1. **Bidirectional Elman Networks (Bi-Elman)**  
• **Dual-pathway RNNs**: Simultaneously process input sequences in forward (left-to-right) and backward (right-to-left) directions to capture bidirectional contextual dependencies (e.g., grammatical structures and semantic associations).  
• **Parameter Efficiency**: Shares weight matrices between forward and backward paths to reduce redundancy while maintaining expressive power.  
• **Limitations Addressed**: Mitigates vanishing gradients through simplified gating mechanisms compared to LSTMs/GRUs.  

### 2. **Dynamic Attention Fusion**  
• **Adaptive Weighting**: Computes time-step-specific attention scores using a lightweight self-attention mechanism to dynamically emphasize salient contextual segments (e.g., negation cues in sentiment analysis).  
• **Contextual Refinement**: Re-weights the concatenated bidirectional hidden states to prioritize task-relevant information, improving feature discriminability.  
• **Scalability**: Maintains linear complexity with sequence length (vs. quadratic cost of full self-attention).  

### 3. **Hybrid Architecture**  
• **End-to-End Learning**: Combines bidirectional recurrence and attention in a unified framework to avoid information loss from static feature fusion.  
• **Interpretability**: Attention weights provide insights into critical tokens driving classifications (e.g., highlighting "COVID-19" in pandemic-related texts).  

---

## Key Innovations  
• **Dynamic Context Fusion**: Replaces static concatenation with learned attention weights to adaptively fuse bidirectional features.  
• **Test-Time Adaptation**: Injects test samples into the forward pass and updates parameters incrementally to refine contextual representations.  
• **Resource Efficiency**: Achieves 30% fewer parameters than comparable transformers (e.g., BERT-base) while maintaining competitive accuracy.  

---

## Advantages Over Prior Work  
| Approach          | Context Modeling | Attention |
|-------------------|------------------|-----------|
| **DBEAN**         | Bidirectional    | Adaptive  |
| Transformer-based | Bidirectional    | Static    |
| LSTM              | Unidirectional   | None      |

---

## Applications  
• **Domain-Specific Text Classification**: Legal, medical, and financial texts with complex terminology.  
• **Low-Resource Environments**: Optimized for edge devices and real-time systems.  
• **Explainable AI**: Attention heatmaps aid in understanding model decisions.  

---

## Citation  
```bibtex
@article{xu2022dynamic,
  title={Dynamic Bi-Elman Attention Networks: A Dual-Directional Context-Aware Test-Time Learning for Text Classification},
  author={Xu, Dong and Liao, Mengyao and Lai, Zhenglin},
  journal={arXiv preprint arXiv:xxxx.xxxxx},
  year={2025}
}
```
