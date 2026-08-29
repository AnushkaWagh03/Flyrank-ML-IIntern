# Prompt Iteration Log — FL-02

## Task

Analyze search-performance data and identify the most important issues, patterns, and priorities for improvement.

This task was selected from the FL-01 audit work because identifying actionable priorities from search-performance data is a realistic task relevant to the FlyRank track.
---

## Version 0 — Naive Baseline

### Technique

None — naive prompt

### Prompt

Analyze this data and tell me what I should do.

### Output

[Paste the actual AI output here]

### Observation

The output was broad and depended heavily on missing context. It did not clearly define what kind of issues should be prioritized or how recommendations should be structured.

### Why I Changed It Next

The next weakness was that the model had no clear perspective or expertise to apply, so I decided to add role assignment.
---

## Version 1 — Role Assignment

### Technique

Role Assignment

### Prompt

You are an SEO and search-performance analyst.

Analyze this data and tell me what I should do.

### Output

[Paste the actual AI output here]

### Observation

[Write what actually changed in the output compared with Version 0.]

### Why I Changed It Next

[Identify the biggest remaining weakness.]
---

## Version 2 — Context and Motivation

### Technique

Context and Motivation

### Prompt

You are an SEO and search-performance analyst.

Analyze this data and tell me what I should do.

Context: The data represents search-performance information for web pages. Each row represents a page and includes metrics related to search visibility, traffic trends, rankings, impressions, clicks, and content performance.

The goal is to help prioritize improvements so that effort is focused on the pages and issues most likely to have meaningful search-performance impact.

### Output

[Paste the actual AI output here]

### Observation

[Describe what improved in the actual output.]

### Why I Changed It Next

[Describe what is still weak.]
---

## Version 3 — Few-Shot Examples

### Technique

Few-Shot Examples

### Prompt

You are an SEO and search-performance analyst.

Analyze this data and tell me what I should do.

Context: The data represents search-performance information for web pages. Each row represents a page and includes metrics related to search visibility, traffic trends, rankings, impressions, clicks, and content performance.

The goal is to help prioritize improvements so that effort is focused on the pages and issues most likely to have meaningful search-performance impact.

Example of a useful finding:

Finding: A page has high impressions but a low click-through rate.

Why it matters: The page is appearing in search results but is failing to attract clicks.

Recommended action: Review the title, meta description, and alignment between search intent and page content.

Now analyze the provided data using a similar level of specificity.

### Output

[Paste the actual AI output here]

### Observation

[Describe how the example changed the output.]

### Why I Changed It Next

[Describe what is still missing.]
---

## Version 4 — Output Structure

### Technique

Output Structure

### Prompt

You are an SEO and search-performance analyst.

Analyze this data and tell me what I should do.

Context: The data represents search-performance information for web pages. Each row represents a page and includes metrics related to search visibility, traffic trends, rankings, impressions, clicks, and content performance.

The goal is to help prioritize improvements so that effort is focused on the pages and issues most likely to have meaningful search-performance impact.

Example of a useful finding:

Finding: A page has high impressions but a low click-through rate.

Why it matters: The page is appearing in search results but is failing to attract clicks.

Recommended action: Review the title, meta description, and alignment between search intent and page content.

Now analyze the provided data.

Present the results in this table:

| Priority | Finding | Evidence | Why It Matters | Recommended Action |
|---|---|---|---|---|

### Output

[Paste the actual AI output here]

### Observation

[Describe what improved.]

### Why I Changed It Next

[Describe the remaining weakness.]
---

## Version 5 — Step Decomposition

### Technique

Step Decomposition

### Prompt

You are an SEO and search-performance analyst.

Analyze this data and tell me what I should do.

Context: The data represents search-performance information for web pages. Each row represents a page and includes metrics related to search visibility, traffic trends, rankings, impressions, clicks, and content performance.

The goal is to help prioritize improvements so that effort is focused on the pages and issues most likely to have meaningful search-performance impact.

Example of a useful finding:

Finding: A page has high impressions but a low click-through rate.

Why it matters: The page is appearing in search results but is failing to attract clicks.

Recommended action: Review the title, meta description, and alignment between search intent and page content.

Analyze the data using these steps:

1. Identify significant positive and negative performance patterns.
2. Identify pages or metrics showing the largest potential problems.
3. Separate confirmed findings from observations requiring further investigation.
4. Estimate which findings are likely to have the greatest impact.
5. Recommend a specific action for each high-priority finding.
6. Rank the findings from highest to lowest priority.

Present the final results in this table:

| Priority | Finding | Evidence | Why It Matters | Recommended Action |
|---|---|---|---|---|

Do not invent findings that are not supported by the data.

### Output

[Paste the actual AI output here]

### Observation

[Describe what improved compared with Version 4.]

### Why This Is the Final Version

[Explain why this prompt is the strongest version.]