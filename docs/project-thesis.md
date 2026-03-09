# Project Thesis

## Working Title

**Chinese Fictional Emotional Reasoning Benchmark (CN-FERBench)**

Chinese: **中文虚构/角色扮演对话中的情绪-关系推理评测**

This project evaluates whether language models can correctly infer **emotion, subtext, and interpersonal logic** in fictional / roleplay-style Chinese dialogue, and then generate responses that remain **in character** without major out-of-character (OOC) distortion.

## Core Problem

Current dialogue evaluation usually does a decent job on broad categories such as:

- general fluency
- instruction following
- emotional support in real-world scenarios
- safety behavior
- coarse persona consistency

But fictional / roleplay dialogue exposes a different class of failure.

A model may sound fluent, kind, and even emotionally competent while still failing the scene by:

- misreading the actual feeling beneath indirect wording
- flattening relationship dynamics into generic comfort or advice
- applying modern therapist-style language where it is OOC
- violating worldview, lore, or character-specific emotional logic
- resolving tension too quickly and thereby destroying characterization

This benchmark exists to evaluate that narrower but practically important failure mode.

## Core Research Question

The main question is not:

> Can a model produce a nice or supportive reply?

The main question is:

> Can a model correctly infer what a character is really feeling, why they are speaking this way, what relational move the utterance makes, and what kind of response would preserve the scene's emotional and interpersonal logic?

## Why This Project Matters

Existing public work on role-playing LLMs, persona fidelity, and character knowledge has already established that roleplay is a real evaluation domain. However, there still appears to be a gap around **fictional emotional reasoning under character and relationship constraints**, especially in Chinese dialogue where indirectness, restraint, hierarchy, and loaded subtext are common.

This project focuses on that gap.

It is motivated by failure patterns commonly observed in roleplay / OC / TRPG-style chat communities:

- the model reads surface wording but misses in-world meaning
- the model gives a socially polished but emotionally wrong reply
- the model becomes too therapist-like, too modern, or too morally sanitized
- the model preserves niceness but breaks character
- the model knows the lore but fails the human logic of the scene

## Scope

This benchmark is **in scope** for:

- Chinese fictional dialogue
- roleplay-style interaction
- subtext-sensitive emotional inference
- relationship-aware reasoning
- in-character response generation
- explicit OOC failure analysis

This benchmark is **not primarily about**:

- generic emotional support quality
- clinical psychology correctness
- broad chatbot safety evaluation
- generic sentiment classification
- all-purpose roleplay quality across every scenario
- only persona profile consistency
- only character knowledge error detection
- training a roleplay model

## Benchmark Tasks

The benchmark should be structured as two separate tasks.

### Task A — Scene Understanding

Given scene context and an utterance, the model should infer:

- the speaker's likely emotional state
- mixed or masked emotions
- subtext
- likely motive, fear, or relational intention
- the relationship logic relevant to interpretation
- what a good response should preserve or avoid

This task measures whether the model actually understands the scene.

### Task B — In-Character Response

Given the same context, the model should generate the next reply as the target character.

This task measures whether the model can:

- maintain character voice
- preserve emotional logic
- preserve relationship dynamics
- obey worldview / lore constraints
- continue the scene naturally without major OOC distortion

Separating the two tasks is important because a model can understand the scene but still generate a bad reply, or generate a plausible reply by accident while misunderstanding the scene.

## Distinction from Existing Work

This project should position itself as adjacent to, but distinct from, several nearby lines of work.

### Broad role-playing benchmarks

These evaluate general role-playing ability across multiple role types and interaction settings. They are useful, but they do not fully isolate emotional subtext, relational logic, and OOC emotional failure in fictional scenes.

### Persona fidelity evaluation

These evaluate whether a model stays aligned with an assigned persona. This is relevant, especially for OOC detection, but it does not fully capture whether the model read the scene's emotional logic correctly.

### Character knowledge error evaluation

These focus on whether the model respects what a character should or should not know. That is one important dimension, but knowledge fidelity is not the same as emotional and relational fidelity.

### Character / roleplay agent training

These aim to build better role-playing agents. This project is different: it is an evaluation benchmark, not a model-training framework.

## Hypothesis

A useful benchmark can reveal that model quality in fictional dialogue is not captured well by surface helpfulness, broad persona alignment, or lore recall alone.

In particular, strong models may still fail on:

- indirect hurt
- defensive politeness
- concealed care
- hierarchy-sensitive scenes
- betrayal and restraint
- taboo or asymmetrical intimacy
- scenes where a "healthy" response would still be wrong in character

## Intended Contribution

The intended contribution of the repo is:

> a Chinese benchmark for fictional dialogue that evaluates whether language models can infer emotion, subtext, and interpersonal logic under character and world constraints, and generate in-character responses without major out-of-character distortions such as therapist-mode intrusion, relationship flattening, or premature emotional resolution.

## Design Principles

The project should follow several principles.

### 1. Sharp scope beats broad scope

It is better to evaluate one hard, distinctive failure mode well than to claim to measure everything about roleplay.

### 2. Interpretive competence and generative competence must be separated

Scene understanding and in-character response are related but not identical.

### 3. Fine-grained failures matter

A response can be partially in character and partially OOC. The benchmark should support hard-fail tags and failure analysis instead of collapsing everything into one vague score.

### 4. Ambiguity should be represented, not erased

Some fictional scenes are intentionally layered. Gold annotations should not pretend that every case has one perfectly explicit emotional reading.

### 5. Good RP quality is not the same as emotional niceness

A reply can sound mature, kind, and articulate while still being fundamentally wrong for the character, relationship, or world.

## Near-Term Plan

Before further public-facing README changes, the repo should first stabilize its internal design through the following docs:

- `docs/literature-map.md`
- `docs/case-schema.md`
- `docs/annotation-guidelines.md`
- `docs/failure-taxonomy.md`

Then the pilot case set can be built around a stable thesis rather than a moving target.
