# 📄 Prompt Engineering Guide  
A practical, beginner-friendly introduction to writing better prompts for LLMs.

---

## 📌 Table of Contents  
- [LLM Settings](#llm-settings)  
- Basics of Prompting *(coming soon)*  
- Prompt Elements *(coming soon)*  
- General Tips for Designing Prompts *(coming soon)*  
- Examples of Prompts *(coming soon)*  

---

## Intro 🚀  
Prompt engineering is about writing clear instructions that help AI models respond the way you want. It’s a simple, practical skill anyone can learn — no coding needed.

## What It Is & Why It Matters 🤔  
Prompt engineering means guiding large language models (LLMs) using well-structured prompts.  
Think of it as learning how to talk to AI in a way it actually understands.

### **Why it matters:**  
- 🔍 Better prompts → better results  
- ⚡ Saves time in work, research, and everyday tasks  
- 🧠 Helps you understand model strengths and limits  
- 🛠️ Useful for developers, researchers, and beginners  
- 🔁 Improves quickly with small tweaks  

Researchers use it for safety and reasoning.  
Developers use it to build reliable AI features.  
Anyone can use it to get clearer, faster answers.

## What’s in This Repo 📚  
This guide teaches practical techniques you can apply right away. You’ll learn how to:  
- ✏️ Write clear, goal-focused prompts  
- 🔄 Refine and iterate effectively  
- 🧩 Use proven prompting patterns  
- 🧰 Build simple prompt workflows  
- ⚠️ Avoid common mistakes  

---

# LLM Settings  
Understanding these configuration settings helps you control how an LLM behaves.  
Think of them as **knobs** that adjust creativity, accuracy, and structure.

---

## 🔥 Temperature  
Controls how *random* or *creative* the model’s output is.

- **Low temperature** → predictable, factual, consistent  
- **High temperature** → creative, diverse, less predictable  

**When to use:**  
- **0.0–0.3:** math, factual questions, summarization  
- **0.7–1.0:** idea generation, poetry, creative writing  

---

## 🎯 Top-P (Nucleus Sampling)  
Limits token selection to a probability threshold.

- **Low Top-P:** sticks to the most likely words (accurate, safe)  
- **High Top-P:** considers more possible words (creative, diverse)

**Tip:**  
Adjust **Temperature OR Top-P**, not both together.

---

## 📏 Max Length  
Sets the maximum tokens the model can generate.

Use it to:  
- control output size  
- avoid long or expensive responses  
- keep answers focused  

---

## ⛔ Stop Sequences  
Tells the model when to stop generating text.

Useful for:  
- limiting list length  
- controlling output structure  

Example: stop at `"11"` to limit a list to 10 items.

---

## 🔁 Frequency Penalty  
Reduces the chance of repeating words based on how often they’ve appeared.

- Higher = less repetition  
- Good for long responses  

---

## 🎨 Presence Penalty  
Penalizes repeated words equally, encouraging new ideas or terms.

- Higher = more diverse content  
- Lower = stays focused on one idea  

**Tip:**  
Similar to Top-P + Temperature, tune **either frequency OR presence penalty**, not both.

---

## ⭐ Recommended Starter Settings

### **Conservative (factual & deterministic)**  
- Temperature: **0.1**  
- Top-P: **0.9**  
- Top-K: **20**

### **Balanced (general use)**  
- Temperature: **0.2**  
- Top-P: **0.95**  
- Top-K: **30**

### **Creative (diverse & expressive)**  
- Temperature: **0.9**  
- Top-P: **0.99**  
- Top-K: **40**

---

## 📝 Final Note  
Each model version behaves differently.  
Use these settings as a starting point, then experiment to find what works best.

