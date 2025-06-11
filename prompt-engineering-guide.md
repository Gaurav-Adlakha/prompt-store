# Prompt Engineering Guidelines & Examples

> A living document for collecting effective prompting techniques, guidelines, and examples.

---

## 📋 Core Components of Effective Prompts

### 1. **Role and Objective**
Define the LLM's persona and goal clearly.
- Example: *"You are a helpful and creative recipe assistant..."*
- Be specific about the expertise level and tone

### 2. **Instructions / Response Rules**
Clear, specific, unambiguous directives.
- What to do
- What NOT to do
- Example: *"Always list ingredients before steps." "Do not suggest recipes requiring rare ingredients unless specified."*

### 3. **Context**
Provide relevant background information/data.
- User's constraints or preferences
- Available resources
- Example: *User's available ingredients, dietary restrictions, cooking skill level*

### 4. **Examples (Few-Shot Prompting)**
Include input-output pairs demonstrating desired format, style, and detail level.
- Shows the model exactly what you want
- Reduces ambiguity

### 5. **Reasoning Steps (Chain-of-Thought - CoT)**
For complex requests, instruct the model to "think step by step".
- Improves accuracy for multi-step problems
- Makes reasoning transparent

### 6. **Output Formatting Constraints**
Define the exact structure you want.
- Example: *"Respond in JSON with keys: 'recipe_name', 'ingredients' (as a list), 'steps' (as a list of strings)"*

### 7. **Delimiters and Structure**
Use clear markers to separate prompt sections.
- Common delimiters: `###`, ` ``` `, XML tags like `<input>`, `<task>`
- Makes prompts more parseable and organized

---

## 🏗️ Prompt Structure Templates

### System Prompt Template Example

```markdown
<style-guide>
[Define writing style preferences here]
</style-guide>

<structure-model>
[Define how content should be structured]
</structure-model>

<audience>
[Describe target audience characteristics]
</audience>

<output-format>
Markdown, quoted with ```md for easy copy-and-asting.
</output-format>

<instructions>
- Use headings, bullet points, numbered lists and **bold** or _italic_ to make the text easy to read and understand.
[Add more specific instructions]
</instructions>

<input>
[User input goes here]
</input>

<task>
1. Read <input /> carefully, your task is to edit and rewrite it to achieve a high quality, masterfully written version.
2. Read the <style-guide /> - all of your writing should follow it closely.
3. Read about the <structure-model /> - use it to structure the new version you are creating.
4. Read about the <audience /> and make sure you tailor the document to fit their needs.
5. Read <input /> again.
6. Finally, compose the new document.
7. Output in the specified <output-format />.
</task>
```

---

## ✍️ Writing Style Guidelines

### Word Choice Principles
- **Shorter words beat longer words**
- **Fewer words is better than more words** - keep writing light
- **Prioritize clarity over style** - while maintaining minimum style for engagement
- **Active voice > Passive voice**
- **Concrete > Abstract**

### Clarity Guidelines
- Lead with the main point
- One idea per sentence
- Use simple sentence structures when possible
- Break complex ideas into digestible parts

---

## 💡 Best Practices & Tips

### General Tips
- [ ] Test prompts iteratively - small changes can have big impacts
- [ ] Be explicit about edge cases
- [ ] Include "negative examples" of what you DON'T want
- [ ] Consider the model's training data when crafting prompts

### Common Pitfalls to Avoid
- Ambiguous instructions
- Conflicting requirements
- Assuming context the model doesn't have
- Over-complicating simple tasks

---

## 📚 Useful Prompt Patterns

### Pattern: receipe bot ui prompt
```
i want my interface to have
  - a single trace view, where i can cleanly visualize the entire conversation linearly, including tool calls and results, and quickly assess whether the final recipe answers the user's query well
  - an open-ended feedback box for me te provide open notes on what i did not like about the generated recipe
  - a drop down of failure modes (that should start empty and populate as i write open notes)

quality of life elements
- hotkeys to quickly navigate traces
- progress bar to see how may i have created.
- automatically save traces to the data/labeled_trace_latesst.csv

I want the vibe to look like a terminal there, but easy on the eyes. monospace any code (e.g., tool calls)

Tech Stack
• Backend: A lightweight FastAPI server (Python) to serve the trace data and save your labels. This seems like a good fit given your experience with Python.
• Frontend: A single-page application using vanilla HT ML, CSS, and Javalcript. This will keep it simple, fast, and easy to run without a complex build process.

```

### Pattern: Persona-Task-Format
```
You are a [ROLE]. Your task is to [SPECIFIC TASK]. 
Format your response as [FORMAT SPECIFICATION].
```

### Pattern: Context-Constraints-Output
```
Given the following context: [CONTEXT]
With these constraints: [CONSTRAINTS]
Provide: [DESIRED OUTPUT]
```

### Pattern: Step-by-Step Reasoning
```
Please solve this step-by-step:
1. First, identify [X]
2. Then, analyze [Y]
3. Finally, produce [Z]
Show your reasoning for each step.
```

---

## 🗂️ Examples Collection

### Example 1: [Add Title]
```
[Add your favorite prompt example here]
```

### Example 2: [Add Title]
```
[Add another example]
```

---

## 📝 Notes & Observations

- [Add your observations about what works well]
- [Note any surprising discoveries]
- [Document model-specific quirks]

---

## 🔗 Resources & References

- [Add links to helpful resources]
- [Include references to research papers]
- [Link to tools or validators]

---

*Last Updated: [Date]*
*Contributors: [Your name]*
