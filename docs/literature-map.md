# Literature Map

This document summarizes nearby public work and clarifies how this project differs from it.

The goal is not to claim total novelty. The goal is to identify the exact gap this benchmark is trying to fill.

---

## 1. Spotting Out-of-Character Behavior: Atomic-Level Evaluation of Persona Fidelity in Open-Ended Generation

- Venue: Findings of ACL 2025
- Main focus: persona fidelity in open-ended generation
- Key contribution: proposes atomic-level evaluation for subtle OOC behavior rather than only whole-response scoring

### What it contributes

This paper is highly relevant because it treats OOC behavior as a first-class evaluation problem and argues that response-level scoring is too coarse. It proposes finer-grained evaluation that can capture subtle persona misalignment within long-form text.

This is important for the current project because fictional dialogue failure is often not uniform. A single response may contain:

- one sentence that preserves character
- another sentence that breaks character
- emotionally plausible wording with subtle relational distortion

Atomic or fine-grained thinking is therefore extremely useful.

### What it does not fully cover for this project

The paper appears to focus mainly on persona fidelity, especially whether generations remain aligned with assigned personality/persona constraints.

That is relevant, but this project targets a more specific scene-level problem:

- whether the model correctly inferred the actual feeling beneath indirect wording
- whether it preserved relationship logic
- whether it respected fictional worldview constraints
- whether it avoided therapist-style or modernized emotional flattening

In other words: persona fidelity matters, but fictional emotional reasoning is not reducible to persona consistency alone.

### What this repo should borrow

- fine-grained OOC analysis
- explicit OOC failure labeling
- the idea that a response can be partially aligned and partially misaligned

---

## 2. DMT-RoleBench: A Dynamic Multi-Turn Dialogue Based Benchmark for Role-Playing Evaluation of Large Language Model and Agent

- Venue: AAAI 2025
- Main focus: broad Chinese role-playing evaluation via dynamic multi-turn dialogue
- Key contribution: proposes a Chinese benchmark with diverse role types, evaluation intents, dynamic conversations, and a judge model / score pipeline

### What it contributes

This paper is important because it establishes that Chinese role-playing evaluation is already a legitimate benchmark direction. It also emphasizes multi-turn realism and dynamic interaction instead of static or overly artificial roleplay tests.

### What it does not fully cover for this project

DMT-RoleBench is broad. It aims to evaluate role-playing ability across many role types and interaction conditions. That makes it a useful neighboring benchmark, but not the same project.

The current repo is narrower and more specialized. It focuses on:

- fictional emotional reasoning
- subtext-sensitive interpretation
- relationship logic
- in-character response fidelity under emotional pressure
- fine-grained OOC failure modes

This distinction is important. The goal here is not to build a broad "roleplay ability" benchmark. It is to isolate a sharper and more practically felt failure mode.

### What this repo should borrow

- the legitimacy of Chinese role-playing evaluation as a benchmark lane
- the importance of multi-turn or context-rich interaction framing
- the idea that real-world user interaction should shape evaluation design

### What this repo should avoid copying blindly

- benchmark sprawl
- too many generic metrics
- broad roleplay framing that weakens the project's distinctive contribution

---

## 3. Character-LLM: A Trainable Agent for Role-Playing

- Venue: EMNLP 2023
- Main focus: training LLMs to act as specific historical or fictional people using profile, experience, and emotional-state information
- Key contribution: treats character simulation as a trainable agent problem rather than a prompt-only problem

### What it contributes

This paper helps establish that character roleplay is not a trivial gimmick. It depends on more than style imitation; profile, experience, emotional state, and knowledge boundaries all matter.

That supports the broader legitimacy of this repo's focus.

### What it does not fully cover for this project

Character-LLM is mainly about how to build or train a better role-playing agent. This repo is not a training framework. It is an evaluation benchmark.

Also, while character training and role simulation are related to the current project, they do not directly answer the question of whether a model can correctly read fictional emotional logic in a scene.

### What this repo should borrow

- language around character experience, emotional state, and knowledge boundaries
- the idea that role-playing quality depends on more than surface persona prompts
- awareness that world knowledge leakage can break character behavior

### What this repo should not become

- a character-simulacrum training project
- a general roleplay agent construction repo

---

## 4. Revealing and Mitigating the Challenge of Detecting Character Knowledge Errors in LLM Role-Playing

- Venue: EMNLP 2025
- Main focus: detecting character knowledge errors in role-playing
- Key contribution: proposes a benchmark around known knowledge errors and unknown knowledge errors in character roleplay

### What it contributes

This paper is useful because it isolates one concrete subproblem inside role-playing: whether the model respects what a character should or should not know.

It also reinforces the idea that role-playing failure should not be treated as a single monolithic concept.

### What it does not fully cover for this project

Knowledge fidelity is only one dimension of fictional dialogue quality. A model can:

- know the lore correctly
- respect knowledge boundaries
- and still completely fail the emotional or relational logic of the scene

This project therefore treats lore / knowledge adherence as one evaluation dimension, but not the whole benchmark.

### What this repo should borrow

- taxonomy thinking
- explicit separation of knowledge-boundary failure from other failure types
- the idea that role-playing requires respecting character knowledge limits

---

## Synthesis: What Gap This Repo Targets

Existing public work already covers several adjacent areas:

- broad role-playing ability
- persona fidelity
- character agent training
- character knowledge errors

However, there still appears to be a narrower underexplored gap:

> whether models can correctly infer emotion, subtext, and interpersonal logic in fictional Chinese dialogue, and generate in-character responses without subtle OOC distortions such as therapist-mode intrusion, relationship flattening, or premature emotional resolution.

That is the exact gap this repo should target.

---

## Positioning Statement for README / Paper Use

A concise positioning statement could be:

> Existing work on role-playing and persona consistency evaluates broad role-playing ability, persona alignment, or character knowledge consistency. This project focuses on a narrower but practically important failure mode: whether models can correctly infer emotion, subtext, and interpersonal logic in fictional dialogue, and respond in character without major OOC distortions.

---

## Implications for Repo Design

This literature map suggests several design decisions.

### 1. Separate interpretation from generation

Because scene understanding and response generation are related but distinct capabilities.

### 2. Use explicit failure taxonomy

Because roleplay failure is not one thing.

### 3. Keep lore as one dimension, not the whole benchmark

Because lore correctness is necessary but not sufficient.

### 4. Support fine-grained failure analysis

Because whole-response scoring alone misses subtle OOC behavior.

### 5. Stay narrow and distinctive

Because this repo's strength is not being the broadest roleplay benchmark. Its strength is targeting a sharp, psychologically and product-relevant failure mode.
