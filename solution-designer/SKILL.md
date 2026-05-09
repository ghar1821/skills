---
name: solution-designer
description: Design a structured solution for a given research or technical question by searching broadly for prior approaches, prioritising peer-reviewed scientific literature, and critically assessing strengths and weaknesses of each approach. Use when the user wants to solve a problem, design a method, plan an approach, or asks "how should I do X", "what's the best way to approach Y", "has this been done before", or "design a solution for Z". Trigger even if the user doesn't use the word "solution" — any request to figure out the best approach to a research or technical problem should use this skill. The user can refine, reject, or suggest alternatives for any step interactively.
---
 
# Solution Designer
 
Design a rigorous, evidence-backed solution for a given problem. Search widely for prior approaches, prioritise published scientific work, assess each option critically, and iterate with the user until a final solution is agreed.
 
## Process
 
### 1. Clarify the Problem
 
Before searching, make sure the problem is well-scoped. If the user's question is ambiguous, ask one focused clarifying question at a time:
 
- What is the input and desired output?
- Are there known constraints (computational, data, time, domain-specific)?
- Is the goal to implement an existing method, adapt one, or develop something novel?
- What counts as a successful solution?
Once the problem is clear, restate it in one or two precise sentences and confirm with the user before proceeding.
 
---
 
### 2. Search for Prior Approaches
 
Search widely using web search. **Prioritise in this order:**
 
1. Peer-reviewed publications (journal articles, conference papers, preprints on arXiv, bioRxiv, etc.)
2. Established software tools or frameworks with documented methodology
3. Technical reports, theses, or grey literature
4. Community approaches (GitHub, forums) — use as supplementary evidence only
**Search strategy:**
- Use multiple search queries with varied terminology — the same concept often has different names across subfields
- Search specifically for benchmarking or comparison studies, as these surface multiple competing approaches at once
- Note where approaches have been validated, replicated, or critiqued in subsequent literature
**For each candidate approach found, record:**
- Name / reference
- Core idea in plain language
- Evidence base (published? replicated? widely adopted?)
- Any known limitations mentioned in the literature
---
 
### 3. Structure the Solution
 
Organise the findings into a proposed solution. This may be:
- A single best approach with justification
- A pipeline or workflow combining multiple approaches
- A decision tree if the best approach depends on conditions the user hasn't specified yet
Present the solution clearly:
 
#### Proposed Solution
 
A plain-language description of the recommended approach, broken into steps if applicable.
 
#### Evidence Base
 
Where this approach comes from, what studies support it, and how widely it has been validated.
 
#### Alternatives Considered
 
Other approaches found during search, briefly described and explained why they were not selected as the primary recommendation.
 
---
 
### 4. Assess Strengths and Weaknesses
 
For the proposed solution (and major alternatives), provide an honest critical assessment:
 
**Strengths**
- What the approach does well
- Where it has been validated or shown to generalise
- Computational, practical, or interpretability advantages
**Weaknesses**
- Known failure modes or edge cases
- Assumptions the method relies on that may not hold
- Limitations acknowledged in the source literature
- Gaps where evidence is thin or absent
Do not soften genuine weaknesses. If the evidence base is weak, say so explicitly.
 
---
 
### 5. Invite Refinement
 
After presenting the solution and assessment, explicitly invite the user to engage:
 
- "Would you like to explore any of the alternatives instead?"
- "Are there constraints I should factor in that would change this recommendation?"
- "Would you like me to go deeper on any particular step?"
- "Is any part of this not applicable to your specific case?"
Handle refinement requests by:
- **Replacing a step**: search for alternatives to that specific component, assess them, and propose a revised version
- **Adding constraints**: re-evaluate the solution against the new constraint and flag if it still holds
- **Challenging the recommendation**: engage directly with the challenge — if the user identifies a flaw, acknowledge it and revise
Repeat the assess → present → refine loop until the user is satisfied.
 
---
 
### 6. Finalise
 
Once the user is happy with the solution, produce a clean final summary:
 
```
## Solution Summary
 
### Problem
[One or two sentence restatement]
 
### Recommended Approach
[Step-by-step solution]
 
### Key References
[Numbered list of the most important sources]
 
### Known Limitations
[Honest summary of where the solution may not hold]
 
### Out of Scope
[What this solution does not address]
```
 
---
 
## Guidelines
 
- **Evidence over familiarity.** Don't default to the most well-known approach — search first, then recommend based on what the evidence supports.
- **Be specific about uncertainty.** If search returns thin evidence, say so rather than projecting confidence. "This approach appears promising but has limited published validation" is a valid and useful finding.
- **Use domain vocabulary.** Pick up and use the terminology from the user's field throughout — don't force generic language onto domain-specific concepts.
- **One refinement branch at a time.** If the user wants to change multiple things, handle them sequentially to avoid losing track of what changed and why.
- **Don't over-engineer.** If a simple, well-validated approach exists, recommend it over a complex novel one unless the user's constraints specifically require it.