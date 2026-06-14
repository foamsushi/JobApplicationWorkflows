# Agentic Job Application & Interview System

This repository is a template for setting up an **Agentic Job Application & Interview Preparation System**. 

The system treats your career history as structured data, your writing preferences as rules, and the application process as an engineering pipeline. It is designed to work with agentic coding environments (like **Antigravity**, **Cursor**, or **Windsurf**) or manually with chat-based LLMs.

---

## 1. Directory Structure

Duplicate this template folder to create your job-searching repository. The directory is structured as follows:

```text
/your-job-searching-workspace
│
├── README.md                # System documentation
├── job_tracker.md           # The Dashboard (Table tracking all applications)
│
├── /masterCV                # Your Source of Truth (NEVER edit these for specific jobs)
│   ├── master_skills.md     # Specialized lists (technical skills, languages, tools)
│   ├── master_work_experience.md  # Detailed, unconstrained history of all roles and metrics
│   ├── master_education.md  # Academic background, coursework, and honors
│   ├── master_awards_references.md # References and professional achievements
│   ├── master_patents_publications.md # Research publications, patents, and presentations
│   ├── master_profiles.md   # Contact info, social links, and pitch variations
│   └── writing_sample.md    # Past cover letters/writing to train the style engine
│
├── /.agent                  # The Brain (Agent workflows and constraints)
│   ├── /rules               # Static rules (e.g., anti-hallucination, writing style, profile)
│   └── /workflows           # Step-by-step pipeline workflows (/application-1, /interview-1, etc.)
│
└── /applications            # The Workspace (One subfolder per company application)
    └── .gitkeep             # Preserves directory in version control
```

---

## 2. Setup Guide

To initialize your personal agentic application workspace:

### Step 1: Set Up Your Master CV
Navigate to the `masterCV/` directory and replace the placeholders in each file with your actual records.
- Be extremely detailed in `master_work_experience.md`. Include more bullets than would fit on a traditional resume; the agent will filter and tailor them for each role automatically.
- Paste samples of your best writing (cover letters, professional posts) into `masterCV/writing_sample.md`. This is used to analyze and mimic your natural voice (avoiding generic AI-sounding text).

### Step 2: Define Your Candidate Profile
Open `.agent/rules/rule5.md` and define your **Professional Archetype/Positioning**. 
- Write a 2-3 sentence summary explaining your core domain, seniority, and primary value focus.
- This serves as the agent's north star, preventing it from framing you as a junior engineer or a support resource when you are targeting senior design or R&D roles.

### Step 3: Track Your Applications
Use `job_tracker.md` as your dashboard to organize and link all active job opportunities, updating the status as you progress.

---

## 3. The Workflows

The system features two core pipelines under `.agent/workflows/`. You can trigger them directly in your agentic IDE using their slash command shortcuts (or review the markdown files to copy prompts for standard LLM chats).

### A. The Application Pipeline

1.  **Ingestion & Classification (`/application-1`)**
    - **Input**: Target Job Description URL.
    - **Action**: Scrapes the description and runs a dual-axis capability and role gravity analysis.
    - **Output**: `gap_analysis_report.md` (Capability Score, missing keywords, and structural risks) + `role_fit_decision.md` (Classifies the job as **TARGET**, **CONDITIONAL**, or **AVOID**).
2.  **Strategic Research (`/application-2`)**
    - **Input**: Company Name.
    - **Action**: Researching the company's financial reports, news, and strategic priorities.
    - **Output**: `company_intel_brief.md` detailing structural pain points (qualification issues, supplier variability, scaling bottlenecks).
3.  **Resume Tailoring (`/application-3`)**
    - **Input**: CV + Intel Brief + Gap Analysis.
    - **Action**: Tailors bullet points to highlight skills matching the company's pain points. Enforces structural rules (methodology first, risk reduction second).
    - **Output**: `tailored_resume_[Company].md`.
4.  **Cover Letter Strategy (`/application-4`)**
    - **Input**: Intel Brief + Style Guide.
    - **Action**: Drafts a "Pain Letter" following strict structure (structural empathy, operating model, evidence, and close). Mimics writing sample tone and strips typical AI filler.
    - **Output**: `pain_letter_[Company].md`.
5.  **Sanity Check (`/application-check`)**
    - Runs final audits (checks for support-role vocabulary, ensuring system design is visible within 10 seconds).

### B. The Interview Preparation Pipeline

When you secure an interview, switch to the interview workflows:
1.  **Mode Prediction (`/interview-0`)**: Evaluates JD to predict interview questions and focus.
2.  **Risk Audit (`/interview-1`)**: Analyzes company culture stressors, firefighting risks, and team structures.
3.  **Answer Strategy (`/interview-2`)**: Drafts stories matching mandatory categories (scale-up failures, cross-functional conflicts).
4.  **Consultative Questions (`/interview-3`)**: Formulates senior-level questions to ask back.
5.  **Stress Test Simulator (`/interview-4`)**: The agent simulates a skeptical interviewer asking aggressive follow-ups.
6.  **Final Polish (`/interview-5`)**: Refines responses for brevity, removing tentative language to project calm authority.

---

## 4. Key Rules Enforced

The workspace includes custom constraints under `.agent/rules/` to guarantee quality outputs:
- **No Hallucinations (`rule1.md`)**: The agent is strictly forbidden from inventing tasks, metrics, or technologies not present in your `masterCV/`.
- **PII Protection (`rule2.md`)**: Prevents the agent from sending phone numbers, home addresses, or SSNs to external APIs.
- **Writing Engine (`general-writing.md`)**: Implements standard rules to purge high-frequency AI markers (e.g., "delve," "foster," "tapestry," "game-changer," vertical lists with bold headers) and breaks the "rule of three" to create natural, bursty paragraphs.
