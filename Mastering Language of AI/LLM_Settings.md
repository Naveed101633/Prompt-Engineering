## Model Configuration Settings

When designing and testing prompts, you often interact with an LLM through an API. A few key parameters can be adjusted to influence the model’s behavior. Tweaking these settings improves reliability and output quality, and requires some experimentation based on your use case.

Below are the most common settings across LLM providers.

---

### **Temperature**
- Controls randomness in the output.  
- **Lower temperature** → more deterministic, focused, factual responses.  
- **Higher temperature** → more randomness, creativity, and diversity.

**Use cases:**  
- Low (e.g., 0.0–0.3): factual QA, summarization  
- High (e.g., 0.7–1.0): creative writing, poetry, brainstorming

---

### **Top-P (Nucleus Sampling)**
- Limits token selection to the smallest set whose cumulative probability = top_p.  
- **Low top_p** → most likely tokens only → more accurate, factual.  
- **High top_p** → includes less likely words → more variety and creativity.

**Note:**  
You generally adjust **temperature OR top_p**, not both.

---

### **Max Length**
- Sets the maximum number of tokens the model can generate.  
- Useful for preventing long, irrelevant, or costly outputs.

---

### **Stop Sequences**
- A specific string that tells the model when to stop generating.  
- Useful for controlling structure (e.g., stopping a list at a certain point).

Example:  
To limit a list to 10 items, add `"11"` as a stop sequence.

---

### **Frequency Penalty**
- Reduces the likelihood of repeating words based on how often they’ve appeared.  
- Higher penalty → less repetition of frequent words.

---

### **Presence Penalty**
- Penalizes repeated words equally, regardless of how many times they appeared.  
- Higher penalty → encourages introducing new topics or terms.  
- Lower penalty → keeps the model focused.

**Note:**  
Similar to temperature/top_p, you typically adjust **either frequency OR presence penalty**, not both.

---

## Recommended Starting Points

### **Conservative (factual, deterministic)**
- Temperature: **0.1**  
- Top-P: **0.9**  
- Top-K: **20**

### **Balanced (general use)**  
- Temperature: **0.2**  
- Top-P: **0.95**  
- Top-K: **30**

### **Creative (diverse, experimental)**  
- Temperature: **0.9**  
- Top-P: **0.99**  
- Top-K: **40**

---

## Final Note
Results may vary depending on the LLM version you use.

