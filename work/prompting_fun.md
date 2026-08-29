# Prompt Engineering Iteration Log

**Phase:** Foundations
**Task:** Prompt Engineering Iteration
**Repository:** FlyRank ML
**Technique Count:** 5+ iterations beyond baseline

---

## 1. Task

### FL-01 Target Task

> Build a RAG chatbot using Python and LangChain.

### Why I Selected This Task

This is a real AI/ML development task that I work with and is suitable for testing prompt engineering techniques. A RAG chatbot involves multiple technical decisions such as document ingestion, chunking, embeddings, vector storage, retrieval, LLM generation, testing, and failure handling.

The initial task description is intentionally broad, which makes it useful for measuring how different prompting techniques improve the quality and usefulness of the model's response.

### Objective

The objective of this experiment is to progressively improve a simple prompt by applying five named prompt engineering techniques:

1. Role assignment
2. Context and motivation
3. Few-shot examples
4. Output structure
5. Step decomposition

The final prompt will then be tested on both Claude and ChatGPT.

---

# 2. Version 1 — Naive Prompt

## Technique

**Baseline / Naive Prompt**

This represents the kind of prompt I would have written before studying prompt engineering.

## Prompt

```text
Build a RAG chatbot using Python and LangChain.
```

## Output

> **Paste the complete actual model output here.**

```text
[PASTE ACTUAL OUTPUT HERE]
```

## Observation

The prompt provides very little information about the desired result.

It does not specify:

* who the model should act as
* why the chatbot is being built
* who the intended users are
* what technologies should be used beyond Python and LangChain
* the expected architecture
* implementation requirements
* expected output format
* testing requirements
* failure cases

Because of this, the model has to make many assumptions about the project.

This version acts as the baseline against which the following versions will be compared.

---

# 3. Version 2 — Role Assignment

## Technique

**Role Assignment**

The model is given a specific expert role so that it approaches the task from an appropriate professional perspective.

## Prompt

```text
You are a senior Python and LangChain engineer.

Build a RAG chatbot using Python and LangChain.
```

## Output

> **Paste the complete actual model output here.**

```text
[PASTE ACTUAL OUTPUT HERE]
```

## What Changed

The main change was assigning the model the role of a senior Python and LangChain engineer.

## Observation

Compared with Version 1, the response became more focused on software engineering and the technical implementation of the RAG system.

The model was more likely to discuss technical components such as:

* document processing
* embeddings
* vector databases
* retrieval
* LLM integration
* application architecture

However, the task was still underspecified.

The model still did not know the project's purpose, intended audience, constraints, desired output structure, or implementation priorities.

### Lesson

Role assignment helps establish the perspective and expertise expected from the model, but a role alone is not enough to produce a highly controlled response.

---

# 4. Version 3 — Context + Motivation

## Technique

**Context and Motivation**

Additional information is provided about the project, its purpose, and the desired outcome.

## Prompt

```text
You are a senior Python and LangChain engineer.

I am building a RAG chatbot as a portfolio project to demonstrate
practical knowledge of Retrieval-Augmented Generation.

The chatbot should allow users to upload documents, retrieve relevant
information from those documents, and generate answers using an LLM.

Use Python and LangChain.

The goal is to create a project that is understandable to another
developer and suitable for a technical portfolio.

Provide a recommended architecture and implementation approach.
```

## Output

> **Paste the complete actual model output here.**

```text
[PASTE ACTUAL OUTPUT HERE]
```

## What Changed

This version adds:

* project context
* project motivation
* intended functionality
* intended audience
* portfolio requirement
* expected technology
* high-level goal

## Observation

Compared with Version 2, the model had a clearer understanding of why the RAG chatbot was being developed.

The response became more project-oriented rather than simply explaining how RAG works.

The model could now make recommendations based on the portfolio goal and the intended functionality of the chatbot.

However, the model was still free to choose its own response format. Important areas such as testing, failure handling, folder structure, and implementation order could still be omitted.

### Lesson

Providing context and motivation reduces ambiguity because the model understands not only **what** needs to be built but also **why** it needs to be built.

---

# 5. Version 4 — Few-Shot Examples

## Technique

**Few-Shot Prompting**

Examples are provided to demonstrate the expected type and level of response.

## Prompt

```text
You are a senior Python and LangChain engineer.

I am building a RAG chatbot as a portfolio project.

The chatbot should allow users to upload documents, retrieve relevant
information from those documents, and answer questions using an LLM.

Use Python and LangChain.

Here are examples of the type of response I want.

Example 1:

Input:
Build a document chatbot.

Preferred response:

1. Document ingestion
2. Text splitting
3. Embedding generation
4. Vector storage
5. Retrieval
6. LLM generation
7. API/UI layer

Example 2:

Input:
Recommend a RAG architecture.

Preferred response:

Documents → Document Loader → Text Splitter → Embeddings →
Vector Database → Retriever → LLM → Response

Now design the RAG chatbot for my project using Python and LangChain.
```

## Output

> **Paste the complete actual model output here.**

```text
[PASTE ACTUAL OUTPUT HERE]
```

## What Changed

Two examples were added to demonstrate:

* the desired level of detail
* the expected organization
* the preferred representation of the RAG architecture

## Observation

Compared with Version 3, the response should follow the demonstrated patterns more closely.

The examples reduce ambiguity about what a useful answer looks like.

Instead of completely inventing its own format, the model has examples that act as references for the desired response.

The response should also become more consistent in how it presents the RAG pipeline and implementation components.

### Lesson

Few-shot examples are useful when instructions alone are not enough to communicate the exact type of output expected.

---

# 6. Version 5 — Output Structure

## Technique

**Output Structure**

The model is explicitly told how to organize its response.

## Prompt

```text
You are a senior Python and LangChain engineer.

I am building a RAG chatbot as a portfolio project.

The chatbot should allow users to upload documents, retrieve relevant
information from those documents, and answer questions using an LLM.

Use Python and LangChain.

Provide the solution using exactly this structure:

1. Project Goal
2. System Architecture
3. Technology Stack
4. Data Flow
5. Project Folder Structure
6. Implementation Steps
7. Important Dependencies
8. Potential Failure Points
9. Testing Strategy
10. Expected Result

For each section, provide practical implementation-oriented
information.

Do not spend most of the response explaining basic RAG theory.
Focus on how to actually build the system.
```

## Output

> **Paste the complete actual model output here.**

```text
[PASTE ACTUAL OUTPUT HERE]
```

## What Changed

This version explicitly defines the desired output structure.

The model is required to provide:

1. Project goal
2. Architecture
3. Technology stack
4. Data flow
5. Folder structure
6. Implementation steps
7. Dependencies
8. Failure points
9. Testing strategy
10. Expected result

It also includes a constraint to prioritize practical implementation instead of excessive theoretical explanation.

## Observation

Compared with Version 4, the response became easier to scan and evaluate because the structure was explicitly defined.

Important engineering topics such as testing and failure handling are less likely to be forgotten because they are explicitly requested.

The output is also more consistent because the model does not need to invent its own organization.

### Lesson

Output structure is useful when the quality of an answer depends not only on its content but also on how that content is organized.

---

# 7. Version 6 — Step Decomposition

## Technique

**Step Decomposition**

The overall task is divided into smaller sequential stages.

## Prompt

```text
You are a senior Python and LangChain engineer.

I am building a RAG chatbot as a portfolio project.

Goal:

Build a document-based RAG chatbot that allows users to upload
documents, retrieve relevant information, and generate answers using
an LLM.

Work through the task in the following order.

Step 1 — Define the requirements

Identify the functional and technical requirements.

Step 2 — Design the architecture

Define the complete data flow from document upload to final response.

Step 3 — Select technologies

Recommend appropriate Python, LangChain, embedding, vector database,
and LLM components.

Step 4 — Design the project structure

Provide a practical folder structure.

Step 5 — Define implementation stages

Break implementation into small development stages.

Step 6 — Identify failure points

Identify likely problems such as poor retrieval, irrelevant chunks,
hallucination, missing documents, and API failures.

Step 7 — Define testing

Explain how to test ingestion, retrieval, generation, and end-to-end
responses.

Step 8 — Final implementation plan

Combine everything into a prioritized development plan.

For every step:

- State the objective.
- Provide the recommended approach.
- Identify important decisions.
- Mention potential problems.

Keep the answer practical and implementation-focused.
```

## Output

> **Paste the complete actual model output here.**

```text
[PASTE ACTUAL OUTPUT HERE]
```

## What Changed

The task was divided into eight explicit stages.

Instead of asking the model to solve the entire problem at once, the prompt provides a sequence:

```text
Requirements
     ↓
Architecture
     ↓
Technology Selection
     ↓
Project Structure
     ↓
Implementation
     ↓
Failure Analysis
     ↓
Testing
     ↓
Final Plan
```

## Observation

Compared with Version 5, the response became more actionable because the model was instructed to approach the problem in a logical development sequence.

The decomposition also makes it easier to cover important areas that might otherwise be missed.

For example, failure analysis and testing are explicitly separated from the implementation process.

This creates a more complete engineering plan rather than only a description of the RAG architecture.

### Lesson

Step decomposition is useful for complex tasks because breaking a large request into smaller stages helps the model produce a more systematic and complete response.

---

# 8. Iteration Summary

| Version | Technique            | Main Change                         | Observed Improvement                               |
| ------- | -------------------- | ----------------------------------- | -------------------------------------------------- |
| V1      | Baseline             | Simple one-line request             | Establishes baseline and exposes ambiguity         |
| V2      | Role Assignment      | Added expert role                   | More technically focused response                  |
| V3      | Context + Motivation | Added project purpose and goals     | Better understanding of the intended project       |
| V4      | Few-Shot Examples    | Added examples of desired responses | Better alignment with expected answer style        |
| V5      | Output Structure     | Defined required sections           | More organized and complete response               |
| V6      | Step Decomposition   | Divided task into sequential stages | More systematic and actionable implementation plan |

---

# 9. Cross-Model Comparison

The final Version 6 prompt was tested using the same prompt on:

* Claude
* ChatGPT

The prompt was not intentionally modified between the two models.

## Final Prompt Used

```text
You are a senior Python and LangChain engineer.

I am building a RAG chatbot as a portfolio project.

Goal:

Build a document-based RAG chatbot that allows users to upload
documents, retrieve relevant information, and generate answers using
an LLM.

Work through the task in the following order.

Step 1 — Define the requirements

Identify the functional and technical requirements.

Step 2 — Design the architecture

Define the complete data flow from document upload to final response.

Step 3 — Select technologies

Recommend appropriate Python, LangChain, embedding, vector database,
and LLM components.

Step 4 — Design the project structure

Provide a practical folder structure.

Step 5 — Define implementation stages

Break implementation into small development stages.

Step 6 — Identify failure points

Identify likely problems such as poor retrieval, irrelevant chunks,
hallucination, missing documents, and API failures.

Step 7 — Define testing

Explain how to test ingestion, retrieval, generation, and end-to-end
responses.

Step 8 — Final implementation plan

Combine everything into a prioritized development plan.

For every step:

- State the objective.
- Provide the recommended approach.
- Identify important decisions.
- Mention potential problems.

Keep the answer practical and implementation-focused.
```

---

## 9.1 Claude Output

> **Paste the relevant Claude output here.**

```text
[PASTE CLAUDE OUTPUT HERE]
```

---

## 9.2 ChatGPT Output

> **Paste the relevant ChatGPT output here.**

```text
[PASTE CHATGPT OUTPUT HERE]
```

---

# 10. Cross-Model Analysis

## Tone

### Claude

**Actual observation:**

[Describe Claude's tone based on the output.]

Example:

> Claude used a more explanatory and instructional tone, spending more
> time explaining why individual architecture decisions were appropriate.

### ChatGPT

**Actual observation:**

[Describe ChatGPT's tone based on the output.]

Example:

> ChatGPT used a more direct implementation-oriented tone and moved
> more quickly from architecture into concrete development steps.

### Comparison

[Explain which model was more suitable for your particular task and why.]

---

## Accuracy

### Claude

**Actual observation:**

[Identify specific technically correct or incorrect recommendations.]

### ChatGPT

**Actual observation:**

[Identify specific technically correct or incorrect recommendations.]

### Comparison

The comparison should focus on concrete technical differences rather
than simply stating that both models were accurate.

For example:

* Did both recommend the same retrieval approach?
* Did either model recommend outdated LangChain APIs?
* Did either model make unsupported assumptions?
* Did either model miss an important component?
* Did either model identify retrieval quality problems?

---

## Structure

### Claude

**Actual observation:**

[Explain how closely Claude followed the requested eight-step structure.]

### ChatGPT

**Actual observation:**

[Explain how closely ChatGPT followed the requested structure.]

### Comparison

[Explain which model followed the requested structure more consistently.]

---

## Failure Points

### Claude

**Actual observation:**

[Describe specific weaknesses or omissions.]

### ChatGPT

**Actual observation:**

[Describe specific weaknesses or omissions.]

### Comparison

[Explain the most important difference between the two outputs.]

---

# 11. Overall Cross-Model Conclusion

The final prompt significantly reduced ambiguity compared with the naive
prompt.

However, the two models still produced different results despite
receiving the same instructions.

**Claude's strongest area:**

[INSERT YOUR OBSERVATION]

**ChatGPT's strongest area:**

[INSERT YOUR OBSERVATION]

**Most important difference:**

[INSERT YOUR OBSERVATION]

The experiment demonstrates that prompt engineering can improve
consistency, completeness, and task alignment, but it does not make
different models produce identical results.

---

# 12. Reusable Prompt Template

The following template generalizes the techniques used throughout this
experiment so that another person can apply it to a different task.

```text
You are a [ROLE / DOMAIN EXPERT].

## Context

I am working on [PROJECT OR TASK].

The intended user/audience is [TARGET USER OR AUDIENCE].

The main goal is [GOAL].

The important constraints are:

- [CONSTRAINT 1]
- [CONSTRAINT 2]
- [CONSTRAINT 3]

## Examples

Use the following examples to understand the expected type and level
of output.

Example 1:

Input:
[EXAMPLE INPUT]

Desired output:
[EXAMPLE OUTPUT]

Example 2:

Input:
[EXAMPLE INPUT]

Desired output:
[EXAMPLE OUTPUT]

## Task

Complete the following task:

[TASK DESCRIPTION]

Break the task into the following stages:

1. [STAGE 1]
2. [STAGE 2]
3. [STAGE 3]
4. [STAGE 4]
5. [STAGE 5]

For each stage:

- State the objective.
- Provide the recommended approach.
- Identify important decisions.
- Mention potential failure points.

## Output Requirements

Return the final response using this structure:

1. [SECTION 1]
2. [SECTION 2]
3. [SECTION 3]
4. [SECTION 4]
5. [SECTION 5]

Prioritize:

- [QUALITY REQUIREMENT 1]
- [QUALITY REQUIREMENT 2]
- [QUALITY REQUIREMENT 3]

Avoid:

- [UNDESIRED BEHAVIOR 1]
- [UNDESIRED BEHAVIOR 2]

Before finalizing, verify that:

- All requested requirements are addressed.
- The requested structure is followed.
- Important constraints are respected.
- Assumptions are clearly identified.
- Potential limitations or failure points are mentioned.
```

---

# 13. Why This Template Is Reusable

The template does not depend on the original RAG chatbot task.

The following fields can be replaced for another problem:

```text
[ROLE]
[PROJECT OR TASK]
[TARGET USER]
[GOAL]
[CONSTRAINTS]
[EXAMPLES]
[TASK]
[STAGES]
[OUTPUT SECTIONS]
[QUALITY REQUIREMENTS]
[UNDESIRED BEHAVIOR]
```

For example, the same template could be used for:

* building an ML model
* debugging Python code
* analyzing a dataset
* designing an API
* creating a machine learning pipeline
* writing technical documentation
* reviewing a software architecture
* creating a testing strategy

This makes the final prompt a reusable prompt engineering pattern rather than a prompt specific to one RAG chatbot.

---

# 14. Key Learnings

## 1. A short prompt creates ambiguity

The naive prompt required the model to make many assumptions.

Adding relevant information progressively reduced the number of decisions
left to the model.

## 2. Role assignment changes the model's perspective

Defining an expert role helped orient the response toward the relevant
technical domain.

## 3. Context explains why the task matters

Providing project context and motivation allowed the model to make
recommendations that better matched the actual objective.

## 4. Examples communicate expectations

Few-shot examples were useful for showing the model what a desirable
response should look like instead of relying entirely on abstract
instructions.

## 5. Output structure improves consistency

Explicit sections made the response easier to read, evaluate, and
compare.

## 6. Decomposition helps with complex tasks

Breaking the RAG problem into requirements, architecture, technology
selection, implementation, failure analysis, testing, and final planning
produced a more systematic workflow.

## 7. Better prompting does not guarantee identical model behavior

Claude and ChatGPT can interpret the same engineered prompt differently.
The goal of prompt engineering is therefore not to force identical
outputs, but to reduce ambiguity and improve task alignment.

---

# 15. Final Takeaway

The progression from Version 1 to Version 6 demonstrates that prompt
engineering is an iterative process.

The initial prompt:

```text
Build a RAG chatbot using Python and LangChain.
```

provides only the task.

The final prompt adds:

```text
Role
+
Context
+
Motivation
+
Examples
+
Output Requirements
+
Step Decomposition
+
Constraints
+
Failure Analysis
+
Validation
```

This produces a much more controlled and useful interaction with an LLM.

The main lesson from this experiment is:

> **A good prompt does not simply ask the model to perform a task. It provides the model with the context, examples, structure, constraints, and process needed to perform that task reliably.**