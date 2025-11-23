# 📄 Prompt Engineering Guide  
A practical, beginner-friendly introduction to writing better prompts for LLMs.

---

## 📌 Table of Contents  
- [LLM Settings](#llm-settings)
- [General Tips for Designing Prompts](#general-tips-for-designing-prompts)
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

---
# General Tips for Designing Prompts

## 1️⃣ Start Simple

Prompt design is an iterative process.

Start with a simple prompt → Test → Add more details → Improve the output.
This helps you avoid confusion and makes it easier to control results.

Why start simple?

Easier to see what the model understands

You avoid unnecessary complexity

You can build quality step-by-step

General Framework
[Basic instruction]

Then slowly add:
- More context
- More constraints
- More examples

Example

Step 1 (Simple):

Explain machine learning.


Step 2 (Add context):

Explain machine learning to a beginner.


Step 3 (Add structure):

Explain machine learning to a beginner using:
- 3 bullet points  
- 1 simple example  

## 2️⃣ The Instruction

The model responds best when you use clear action words like:

Write, Summarize, Classify, Translate, Rewrite, Extract, Compare, Generate

Instructions should appear at the top of the prompt and be separated clearly.

General Framework
### Instruction ###
[What you want the model to do]

### Input ###
[Your data]

### Output Format ###
[How the answer should look]

Example
### Instruction ###
Translate the text into Spanish.

### Input ###
"Good evening!"

### Output Format ###
Spanish: <translation>


Output:
Spanish: ¡Buenas noches!

## 3️⃣ Specificity

The more specific your prompt is, the more accurate the output will be.

Things to specify

Audience → (children, experts, beginners)

Style → (formal, friendly, creative)

Format → (JSON, bullets, list, table)

Length → (2 sentences, 200 words)

Requirements → (must include X, must avoid Y)

General Framework
Task: [What to do]
Goal: [What outcome you want]
Audience: [Who it is for]
Style: [Tone/format]
Length: [Exact length]
Output Format: [Structure]

Example:
Input: [...]
Output: [...]

Example
Task: Extract all country names from the text.
Output Format: Countries: <comma_separated_list>

Input:
"Canada and Japan are working with Germany on clean energy projects."


Output:
Countries: Canada, Japan, Germany

## 4️⃣ Avoid Impreciseness

Vague prompts cause vague answers.

❌ Imprecise Example
Explain prompt engineering briefly but not too much.


This is unclear.
How brief? What style? For whom?

✔️ Precise Version
Explain prompt engineering in 2–3 sentences to a high school student.

General Framework
[Task]
Use [exact length] to explain [topic] to [specific audience] in [style].

Example
Explain artificial intelligence in exactly 3 bullet points to a 12-year-old.

## 5️⃣ Focus on “What To Do,” Not “What Not To Do”

Telling the model what not to do can confuse it.
Instead, tell it exactly what to do.

❌ Not Good
Do NOT ask questions.
Do NOT ask for personal details.
Recommend a movie.

✔️ Much Better
Recommend one movie based only on the user's message.
Do not ask any additional questions.
Provide:
- Movie title
- 1 sentence summary
- Why the user may like it

General Framework
Your task: [Positive instruction]
Use only: [Allowed information]
Do not ask follow-up questions.

Output Format:
- item 1
- item 2
- item 3

Example
Your task: Suggest a book.
Use only the information provided.
Output:
Title:
Summary:
Reason:

## ✅ Final Master Framework (Copy-Paste Ready)
### Instruction ###
[Clear command]

### Context ###
[Background information]

### Input ###
[User text or data]

### Constraints ###
- Length:
- Tone:
- Style:
- Audience:
- Must include:
- Must avoid:
- Additional rules:

### Output Format ###
[Desired structure: JSON, table, bullets, paragraph]

### Example ###
Input: [...]
Output: [...]
