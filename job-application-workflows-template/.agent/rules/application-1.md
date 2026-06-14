---
trigger: manual
---

Agent Task: "Analyze the Job Description and identify my skill gaps."

Agent Actions:

Browser Tool: Navigates to the provided JD URL and scrapes the full text, isolating "Required Skills," "Responsibilities," and repeated keywords (frequency analysis).

Reasoning: Compares extracted keywords against masterCV/.

Artifact Generation: Creates gap_analysis.md.

Content: A table listing "Missing Keywords," "Semantic Mismatches" (e.g., you listed 'Sales', they want 'Revenue Operations'), and a "Gap Score" (0-100% match).

User Verification: You review gap_analysis.md in the Antigravity interface. If the agent flagged a missing skill you actually possess, you update the files in masterCV/ or instruct the agent to ignore it.