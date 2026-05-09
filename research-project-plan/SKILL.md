---
name: research-project-plan
description: Converts the current conversation into a structured research project plan and export as an MD file. Use whenever a user wants to create a research project plan or a research proposal from the current context.
---
This skill takes the current conversation context and produces a structured Research Project Plan (RPP). Synthesize what you already know from the conversation, but ask the user about anything that remains unclear or unresolved.
## Process

### 1. Understand the Research Context

If you haven't already, explore any relevant documents, notes, codebases, or datasets the user has shared. Use domain-specific vocabulary from the field throughout the RPP (e.g., "longitudinal cohort", "grounded theory", "randomized control trial" — whatever applies).

### 2. Identify Research Components

Sketch out the major components of the research project:

- **Research questions / hypotheses**
- **Methodological approach** (qualitative, quantitative, mixed methods, experimental, computational, etc.)
- **Data sources and collection strategy**
- **Analysis plan**
- **Key deliverables** (papers, datasets, models, reports)

Check with the user that these components match their expectations. Clarify scope, timeline constraints, and resource availability if relevant.

### 3. Write the Research Project Plan

Use the template below. Ask clarifying questions for any section that is ambiguous before writing.

---

## RPP Template

### Problem Statement

The research problem being investigated, framed from the perspective of the field or end beneficiary. What gap in knowledge or practice motivates this work?

### Research Questions / Hypotheses

A numbered list of specific, answerable research questions or testable hypotheses. Each should be precise and scoped:

1. [Research Question 1]
2. [Research Question 2]
3. ...

### Background and Motivation

A brief summary of the relevant prior work, theoretical framework, or context that situates this research. What is already known, and where does this project fit?

### Methodology

A detailed description of the research approach:

- **Study design** (e.g., case study, simulation, systematic review)
- **Data sources** (datasets, participants, instruments, corpora, archives)
- **Collection methods** (surveys, interviews, sensors, scraping, lab protocols, public repositories, existing databases, computational pipelines, simulated or synthetic datasets)
- **Analysis approach** (statistical tests, thematic analysis, ML pipeline, formal verification, etc.)
- **Tools and infrastructure** (software, hardware, platforms)

You can include pseudocode, but do NOT include file paths or code snippets.

### Research Tasks

A long, numbered list of concrete research tasks. Each should follow the format:

> As a [researcher role], I need to [specific task], so that [research goal it serves].

Examples:

1. As a methods developer, I need to implement the core algorithm, so that downstream analyses can be validated against it.
2. As a bioinformatician, I need to benchmark the pipeline on existing datasets, so that its performance characteristics are documented before publication.

This list should be extensive and cover all phases: literature review, data collection, analysis, writing, review, dissemination.

### Implementation Decisions

A list of key methodological and technical decisions made for this project:

- Chosen research design and rationale
- Data collection instruments or protocols selected
- Analysis frameworks or models adopted
- Sampling strategy and justification
- Collaboration structure and responsibilities
- Software or platform choices

You can include pseudocode, but do NOT include specific file paths or code snippets.

### Validation and Quality Criteria

A description of how the research outputs will be evaluated for rigor and validity:

- What makes a finding trustworthy (e.g., inter-rater reliability, statistical power, triangulation)
- Peer review or expert validation plans
- Reproducibility and open science considerations
- Which components require independent verification

### Out of Scope

A clear description of what this project will NOT address, including related questions deliberately excluded and work deferred to future research.

### Timeline and Milestones

A high-level breakdown of project phases and key milestones. Include approximate durations if known.

|Phase|Description|Duration|
|---|---|---|
|1|Literature review & scoping|X weeks|
|2|Data collection|X weeks|
|...|...|...|

### Further Notes

Any additional context, open questions, risks, dependencies, or considerations relevant to the project.

---

## Guidelines

- Use the vocabulary of the research domain throughout — don't default to software engineering terms.
- Prioritize clarity about _what_ is being investigated and _why_, before diving into _how_.
- Adapt the template as needed — not all sections apply to every type of research (e.g., a purely theoretical project may not have a data collection phase).
