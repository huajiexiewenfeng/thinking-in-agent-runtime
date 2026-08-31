# Vertical Domain Agent Integrative Chapter Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Update the Thinking in Agent Runtime book architecture so a Vertical Domain Agent becomes an explicit integrative validation target, represented by a new Chapter 20 research skeleton.

**Architecture:** Preserve the book-level North Star and the existing seven Runtime capability areas. Add Chapter 20 after the Agent Infra integration chapter, then make small upstream references in the overview, ecosystem, and capability-framework chapters so Harness, Domain workload, and the integrative target do not appear without preparation.

**Tech Stack:** Markdown, Mermaid, Git, GitHub.

## Global Constraints

- Keep Agent Runtime as the book's primary research object and Agent Infra as the broader field.
- Treat Vertical Domain Agent as one downstream integrative validation target, not the sole purpose of Agent Runtime.
- Preserve the one-article-at-a-time writing workflow; Chapter 20 remains a research skeleton, not a full draft.
- Keep `llm-wiki-runtime` positioned as the Knowledge and Context Runtime evidence, not the complete Agent Runtime.
- Separate repository facts, architectural interpretation, and future hypotheses.

---

### Task 1: Update the book roadmap

**Files:**
- Modify: `README.md`

**Interfaces:**
- Consumes: Existing 19-chapter roadmap and theory-to-practice mapping.
- Produces: A 20-chapter roadmap with an explicit integrative validation target.

- [x] **Step 1:** Add a short North Star clarification stating that durable Vertical Domain Agents are one downstream target for testing whether multiple Runtime capabilities form a complete loop.
- [x] **Step 2:** Add Chapter 20, `从 Domain Workload 走向 Vertical Domain Agent`, after Chapter 19 with status `研究骨架`.
- [x] **Step 3:** Add Chapter 20 to the theory/practice mapping and explain that it integrates Chapters 04–12 and evidence from Chapters 13–19.
- [x] **Step 4:** Change references from `19 篇` to `20 篇` where the count describes the whole book.

### Task 2: Prepare the upstream conceptual path

**Files:**
- Modify: `articles/01-overview.md`
- Modify: `articles/04-agent-runtime-ecosystem.md`
- Modify: `articles/06-agent-runtime-capability-framework.md`

**Interfaces:**
- Consumes: The book's responsibility-based Runtime definition and seven capability areas.
- Produces: Explicit conceptual preparation for Harness, Domain workload, and the Chapter 20 synthesis.

- [x] **Step 1:** In Chapter 01, add a concise section explaining that a Vertical Domain Agent is one possible downstream result when Skills, Harnesses, and seven Runtime capability areas form a governed loop.
- [x] **Step 2:** In Chapter 04, add Harness and Domain workload to the ecosystem questions and boundary list.
- [x] **Step 3:** In Chapter 06, add the integrative question: how the seven capability areas support one durable Domain subject without collapsing capability boundaries into one deployment.
- [x] **Step 4:** Link all three chapters forward to Chapter 20 without presenting its hypothesis as an implemented fact.

### Task 3: Add the Chapter 20 research skeleton

**Files:**
- Create: `articles/20-domain-workloads-to-vertical-agents.md`

**Interfaces:**
- Consumes: Chapters 01, 04, 05, 06, 07–12, and implementation evidence from Chapters 13–19.
- Produces: The future writing contract for the book's integrative Vertical Domain Agent chapter.

- [x] **Step 1:** Add status, book role, core question, and thesis.
- [x] **Step 2:** Define the semantics → workload → continuity model and the responsibilities of Skill, Harness, Runtime, Human, and Vertical Domain Agent.
- [x] **Step 3:** Map Loop, State, Knowledge, Tool, Policy, Trace, and Eval to the durable Domain subject.
- [x] **Step 4:** Add minimum validation criteria, the two partial evidence cases, strongest objections, evidence boundaries, and the 14-section writing outline.
- [x] **Step 5:** State explicitly that the chapter is a North Star research skeleton and not a claim of completed implementation.

### Task 4: Verify, commit, and publish

**Files:**
- Verify: `README.md`
- Verify: `articles/01-overview.md`
- Verify: `articles/04-agent-runtime-ecosystem.md`
- Verify: `articles/06-agent-runtime-capability-framework.md`
- Verify: `articles/20-domain-workloads-to-vertical-agents.md`

**Interfaces:**
- Consumes: Tasks 1–3.
- Produces: One reviewed Git commit on `main` and a pushed GitHub update.

- [x] **Step 1:** Run `git diff --check` and require exit code 0.
- [x] **Step 2:** Verify every local Markdown link in the five changed content files resolves.
- [x] **Step 3:** Verify UTF-8 decoding, balanced code fences, Chapter 20 references, and the absence of claims that Vertical Domain Agent is the sole Runtime purpose or a completed implementation.
- [x] **Step 4:** Review `git diff --stat` and `git diff` for scope drift.
- [x] **Step 5:** Commit with `docs: add vertical domain agent integration chapter`.
- [x] **Step 6:** Push `main` to `origin` and verify the remote commit equals local HEAD.

**Execution evidence:** Content commit `34cb7612089fa37858cf4cbc9869ecf8b0f5fdff` was pushed to `origin/main` and the remote reference was verified to match.
