# Chinese Fictional Emotional Reasoning Benchmark

[简体中文说明 / Chinese version](./README.zh-CN.md)

**CN-FERBench** is a Chinese benchmark for evaluating whether language models can correctly infer **emotion, subtext, and interpersonal logic** in fictional / roleplay-style dialogue, and generate responses that remain **in character** without major out-of-character (OOC) distortion.

中文名称：**中文虚构/角色扮演对话中的情绪-关系推理评测**

## Overview

Current dialogue evaluation captures many important capabilities, including fluency, instruction following, safety behavior, and broad persona consistency. However, fictional dialogue exposes a narrower class of failures that remain under-evaluated in public benchmarks.

A model may sound fluent, emotionally literate, and socially polished while still failing the scene by:

- misreading the actual feeling beneath indirect wording
- flattening relationship dynamics into generic comfort or advice
- applying therapist-style or overly modern language that is OOC in context
- violating worldview, lore, or role-specific emotional logic
- resolving tension too quickly and thereby damaging characterization

CN-FERBench is designed to measure that failure mode directly.

## Benchmark Scope

The benchmark focuses on Chinese fictional dialogue with an emphasis on:

- emotion inference under indirect or masked expression
- subtext recognition
- relationship-aware reasoning
- in-character response fidelity
- OOC failure analysis
- style contamination detection in roleplay outputs

This benchmark is not intended as a general emotional-support benchmark, a generic sentiment benchmark, or a broad all-purpose roleplay leaderboard.

## Task Design

CN-FERBench is organized around two complementary tasks.

### Task A — Scene Understanding

Given a fictional dialogue context, the model must infer:

- the speaker's likely emotional state
- mixed or masked emotions
- subtext
- likely motive, fear, or defensive posture
- the relationship logic shaping the utterance
- what an appropriate in-character response should preserve or avoid

### Task B — In-Character Response

Given the same context, the model must generate the next reply as the target character.

This task evaluates whether the model can:

- maintain character voice
- preserve emotional logic
- preserve relationship dynamics
- obey worldview and lore constraints
- continue the scene naturally without major OOC drift

## Why This Benchmark Matters

Roleplay and fictional dialogue systems frequently fail in ways that are easy for users to notice but difficult for coarse evaluation to capture.

Examples include:

- taking literal wording at face value and missing emotional subtext
- confusing wounded withdrawal with calm acceptance
- writing a reply that is emotionally competent but wrong for the character
- flattening hierarchy, taboo, resentment, or unstable intimacy into generic niceness
- replacing scene truth with stock dark-romance or webnovel-style phrasing

These failures matter for roleplay agents, companion systems, fictional dialogue products, character simulators, and any model intended to sustain emotionally charged narrative interaction.

## Evaluation Framework

The current framework includes dimension-level scoring and explicit failure tagging.

Representative Task A dimensions include:

- `emotion_inference_accuracy`
- `subtext_recognition`
- `relationship_logic_alignment`
- `motive_and_response_mode_inference`
- `ambiguity_calibration`

Representative Task B dimensions include:

- `character_voice_fidelity`
- `emotional_logic_preservation`
- `relationship_dynamic_preservation`
- `worldview_constraint_adherence`
- `response_action_fit`
- `natural_scene_continuation`

Representative failure categories include:

- `ooc_modernization`
- `therapist_mode_intrusion`
- `relationship_flattening`
- `motivation_misread`
- `supportive_but_wrong`
- `webnovel_register_contamination`
- `tension_premature_resolution`

## Ontology and Design Principles

The benchmark is built around a richer scene ontology than flat trope lists.

Rather than treating cases as generic prompts, CN-FERBench models fictional dialogue through interacting dimensions such as:

- motive
- expression style
- empathy mode
- power dynamic
- gaze / view of the other
- love authenticity
- weakness trigger
- world and role constraints

This structure supports principled coverage planning, better failure analysis, and stronger case design.

## Repository Structure

```text
.
├── README.md
├── README.zh-CN.md
├── data/
│   ├── cases/
│   │   └── pilot/
│   ├── schema/
│   └── templates/
├── docs/
├── eval/
│   ├── prompts/
│   └── self_eval/
├── examples/
└── legacy/
```

### Key directories

- `data/templates/` — canonical case templates
- `data/cases/pilot/` — pilot benchmark cases
- `docs/` — thesis, rubric, ontology, coverage, annotation, and taxonomy docs
- `eval/prompts/` — prompt templates for Task A and Task B
- `eval/self_eval/` — model self-evaluation samples and audit examples
- `legacy/` — pre-pivot artifacts retained for reference

## Current Materials

The repository currently includes:

- benchmark thesis and literature positioning
- case schema and annotation guidelines
- failure taxonomy and style guidelines
- ontology adaptation and coverage planning docs
- pilot case template
- initial pilot cases across core scenario clusters
- initial self-evaluation sample

## Positioning Relative to Existing Work

Existing public work has already established adjacent directions such as:

- broad role-playing benchmarks
- persona fidelity evaluation
- character knowledge error detection
- roleplay agent training

CN-FERBench targets a narrower and more specific gap:

> whether models can correctly infer emotion, subtext, and interpersonal logic in fictional Chinese dialogue, and respond in character without subtle but consequential OOC distortions.

## Development Status

The benchmark design, ontology adaptation, and pilot case framework are already in place. The current development focus is on expanding the pilot set, refining evaluation prompts, and building comparable baseline analyses.

Some earlier emotional-support-oriented assets are retained under `legacy/` for reference, but the repository's active direction is the fictional emotional reasoning benchmark described above.

## Intended Use

CN-FERBench is intended for:

- research on fictional dialogue evaluation
- benchmarking roleplay-capable language models
- product evaluation for companion and character-chat systems
- qualitative analysis of OOC failure modes in emotionally loaded scenes

## Citation / Project Name

If you refer to this project, use:

**Chinese Fictional Emotional Reasoning Benchmark (CN-FERBench)**

A fuller benchmark report and expanded pilot release will follow as the dataset and evaluation pipeline mature.
