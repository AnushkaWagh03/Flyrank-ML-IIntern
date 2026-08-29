# Prompt Engineering Ladder

## Task

Improving an AI prompt for analyzing search-performance data and identifying what should be prioritized for improvement.

---

## Run 0 — Weak Baseline

### Named Layer

None — intentionally weak baseline

### Prompt

Analyze this data and tell me what I should do.

### Output

Once you provide it, I'll give you a practical analysis in this format:

- What the data shows — key patterns and insights
- What's working well — strengths to maintain
- What's not working — weaknesses/problems
- What should be prioritized — ranked by importance
- What you should do next — specific actionable steps
- Reasoning — why each recommendation matters

Send the data, and I'll analyze it rather than giving generic advice.

### Notes

#### What changed in the prompt?

Nothing. This is the intentionally weak baseline prompt.

#### What actually improved in the output?

This is the baseline run, so there is no previous output to compare against.

#### What still failed?

The model could not perform the requested analysis because no actual data or context was provided. Instead of producing insights or recommendations, it asked for the missing information and only described the type of analysis it could perform.

#### What would I try next?

Add a clearer goal so the model understands exactly what kind of analysis and decision-making support is expected.

---

## Run 1 — Clearer Goal

### Named Layer

Clearer Goal

### Prompt

Analyze this data and identify the most important issues, patterns, and priorities for improvement.

### Output

Please upload or paste the data you want me to analyze (CSV, Excel, table, screenshot, or raw text).

Once provided, I'll analyze it using this structure:

1. Key patterns — what the data is showing
2. Most important issues — biggest weaknesses or anomalies
3. Root causes / possible explanations
4. Priorities for improvement — ranked by impact
5. Recommended actions — specific next steps
6. Quick wins vs. long-term improvements
7. Final priority ranking — what to do first, second, and third

I’ll focus on actionable insights rather than just describing the numbers.

### Notes

#### What changed in the prompt?

Added a clearer goal by specifying that the analysis should identify important issues, patterns, and priorities for improvement.

#### What actually improved in the output?

The response became more focused on the type of analysis required. Instead of giving a general description of what it could do, it outlined specific areas such as patterns, issues, priorities, root causes, and actionable recommendations.

#### What still failed?

The model still could not perform the actual analysis because it had no data or domain context. Although the requested goal was clearer, the output remained a request for additional information rather than useful analysis.

#### What would I try next?

Add real context about the data so the model understands what kind of information it is supposed to analyze.

---

## Run 2 — Real Context

### Named Layer

Real Context

### Prompt

Analyze this data and identify the most important issues, patterns, and priorities for improvement.

Context: The data represents search-performance information for web pages. Each row represents a page and includes information related to search visibility, traffic trends, rankings, and content performance.

### Output

I can do that, but I don't yet see the actual data table/file to analyze.

Please upload or paste the search-performance data (CSV, Excel, screenshot, or table). Once provided, I'll analyze it using this structure:

#### 1. Most Important Issues

- Pages losing traffic
- Significant ranking declines
- High-impression but low-click pages
- Underperforming content
- Pages with poor visibility despite potential

#### 2. Key Patterns

- Overall traffic trends
- Ranking distribution patterns
- Pages consistently improving vs declining
- Content types/topics performing best and worst
- Potential correlation between rankings, impressions, and clicks

#### 3. Priority Actions

I'll categorize findings into:

**High Priority** — likely biggest impact

**Medium Priority** — worthwhile optimization

**Low Priority** — monitor or optimize later

#### 4. Recommended Actions

For each major issue, I'll provide:

- What is happening
- Why it matters
- Which pages should be prioritized
- What action to take

Upload the data, and I'll give you a specific, evidence-based prioritization rather than generic SEO advice.

### Notes

#### What changed in the prompt?

Added real context by explaining that the data represents search-performance information for web pages, including visibility, traffic trends, rankings, and content performance.

#### What actually improved in the output?

The output became domain-specific. Instead of suggesting generic data analysis, it identified search-performance issues such as ranking declines, high impressions with low clicks, traffic loss, and poor search visibility.

#### What still failed?

The model still could not analyze the actual situation because no real dataset or values were provided. It understood the domain but could only describe the analysis it would perform.

#### What would I try next?

Specify a clear output format so that once the analysis is performed, the results are structured consistently and easy to compare.

---

## Run 3 — Specified Output Format

### Named Layer

Specified Output Format

### Prompt

Analyze this data and identify the most important issues, patterns, and priorities for improvement.

Context: The data represents search-performance information for web pages. Each row represents a page and includes information related to search visibility, traffic trends, rankings, and content performance.

Present the analysis as a table with these columns:

- Priority
- Issue or Pattern
- Why It Matters
- Recommended Action

### Output

Please upload or paste the data table/file you want me to analyze.

Once I have the data, I'll return a prioritized table like this:

| Priority | Issue or Pattern | Why It Matters | Recommended Action |
|---|---|---|---|
| High | Significant traffic decline on key pages | Indicates potential ranking, indexing, or intent problems | Investigate affected queries, rankings, competitors, and recent page changes |
| High | High impressions but low CTR | Pages are visible but failing to attract clicks | Improve titles, meta descriptions, and SERP alignment |
| Medium | Rankings just outside page 1 | Small improvements could generate substantial traffic gains | Optimize content around target queries and strengthen internal links |
| Medium | Declining content performance | May indicate outdated content or stronger competitors | Refresh content and improve topical coverage |
| Low | Low visibility pages with weak potential | May not justify immediate investment | Evaluate whether to consolidate, improve, or deprioritize |

Send the CSV, Excel file, screenshot, or pasted table, and I'll analyze the actual patterns and priorities.

### Notes

#### What changed in the prompt?

Added a specified output format by requesting the analysis in a table with Priority, Issue or Pattern, Why It Matters, and Recommended Action.

#### What actually improved in the output?

The response became much more structured and easier to scan. Instead of only describing what the analysis would contain, the model demonstrated how findings would be organized and connected each issue with its importance and recommended action.

#### What still failed?

The model still did not have actual data to analyze, so the table contained hypothetical examples rather than evidence-based findings from real pages.

#### What would I try next?

Add constraints to ensure the model clearly distinguishes between actual evidence from the data and assumptions or hypothetical recommendations.

---

## Run 4 — Constraints

### Named Layer

Constraints

### Prompt

Analyze this data and identify the most important issues, patterns, and priorities for improvement.

Context: The data represents search-performance information for web pages. Each row represents a page and includes information related to search visibility, traffic trends, rankings, and content performance.

Present the analysis as a table with these columns:

- Priority
- Issue or Pattern
- Why It Matters
- Recommended Action

Constraints:

- Do not invent findings that are not supported by the provided data.
- Clearly distinguish between confirmed issues and areas that require further investigation.
- Avoid generic SEO recommendations unless they are connected to an observed pattern.

### Output

Please upload or paste the data table/file you want me to analyze.

Once you provide it, I’ll return a prioritized table in exactly this format:

| Priority | Issue or Pattern | Why It Matters | Recommended Action |
|---|---|---|---|
| High | Confirmed issue based on the data | Evidence-based impact | Specific action tied to the finding |
| Medium | Pattern requiring investigation | Why it may affect performance | Investigation steps |
| Low | Secondary opportunity | Potential impact | Targeted improvement |

I’ll ensure the analysis:

- Uses only findings supported by the data
- Labels findings as Confirmed or Requires Investigation
- Prioritizes issues by likely impact
- Avoids generic SEO advice not supported by observed patterns

### Notes

#### What changed in the prompt?

Added constraints that required the model to avoid unsupported findings, distinguish confirmed issues from areas requiring investigation, and avoid generic recommendations.

#### What actually improved in the output?

The output became more careful and evidence-focused. It explicitly committed to separating confirmed findings from issues requiring investigation and avoided presenting hypothetical SEO problems as facts.

#### What still failed?

The response was still unable to perform the actual analysis because no dataset was available. The constraints improved reliability, but they also made the output more cautious and less actionable.

This partially made the result worse: the model avoided unsupported assumptions, but because no actual data was available, the additional caution mostly produced another request for data rather than a more useful response.

#### What would I try next?

Add quality criteria that define what a useful final analysis should look like, especially how findings should be prioritized and explained.

---

## Run 5 — Quality Criteria

### Named Layer

Quality Criteria

### Prompt

Analyze this data and identify the most important issues, patterns, and priorities for improvement.

Context: The data represents search-performance information for web pages. Each row represents a page and includes information related to search visibility, traffic trends, rankings, and content performance.

Present the analysis as a table with these columns:

- Priority
- Issue or Pattern
- Why It Matters
- Recommended Action

Constraints:

- Do not invent findings that are not supported by the provided data.
- Clearly distinguish between confirmed issues and areas that require further investigation.
- Avoid generic SEO recommendations unless they are connected to an observed pattern.

Quality criteria:

- Prioritize findings based on likely impact rather than listing everything equally.
- Explain the evidence or reasoning behind each recommendation.
- Prefer specific actions over vague advice.
- Make uncertainty explicit when the available information is insufficient.

### Output

Please upload or paste the data table/file you want me to analyze.

Once you provide the data, I'll return a prioritized analysis in this format:

| Priority | Issue or Pattern | Why It Matters | Recommended Action |
|---|---|---|---|
| High | Confirmed issue supported by the data | Evidence-based impact | Specific action tied to the finding |
| Medium | Pattern requiring investigation | Why it may matter | Validation steps before acting |
| Low | Secondary opportunity | Lower expected impact | Targeted improvement |

I’ll distinguish clearly between **confirmed findings** and **areas requiring further investigation**, and I won’t make unsupported assumptions.

### Notes

#### What changed in the prompt?

Added quality criteria defining how findings should be prioritized, explained, and handled when the available information is insufficient.

#### What actually improved in the output?

The response became more disciplined about uncertainty. It clearly separated confirmed findings from areas requiring further investigation and connected priority levels with evidence-based actions.

#### What still failed?

The main limitation remained unchanged: without the actual dataset, the model could not produce a real analysis. The quality criteria improved how the model would structure its future response but did not solve the missing-data limitation.

#### What would I try next?

For a real analysis task, I would provide the actual dataset and require the model to verify every recommendation against the available metrics before prioritizing actions.

---

# Final Reusable Prompt

Analyze the provided search-performance data and identify the most important issues, patterns, and priorities for improvement.

## Context

The data represents search-performance information for web pages. Each row represents a page and may include metrics related to search visibility, traffic trends, rankings, impressions, clicks, and content performance.

## Task

Identify the findings that should receive the highest priority and recommend appropriate actions.

Present the analysis as a table with these columns:

- Priority
- Issue or Pattern
- Why It Matters
- Recommended Action

## Requirements

- Do not invent findings that are not supported by the provided data.
- Clearly distinguish between confirmed issues and areas requiring further investigation.
- Avoid generic recommendations unless they are connected to an observed pattern.
- Prioritize findings based on likely impact.
- Explain the evidence or reasoning behind each recommendation.
- Prefer specific, actionable recommendations over vague advice.
- Make uncertainty explicit when the available information is insufficient.

## Data

[PASTE SEARCH-PERFORMANCE DATA HERE]