# Case Schema

This document defines the recommended structure for benchmark cases.

The goal is to make each case:

- rich enough to capture fictional emotional logic
- structured enough for repeatable annotation
- flexible enough to preserve ambiguity where appropriate
- usable for both Task A (Scene Understanding) and Task B (In-Character Response)

## Design Principle

Do not treat a case as only a prompt-response pair.

A good case in this benchmark is a **scene unit**. It should encode:

- the fictional world context
- who is speaking
- who should respond
- what relationship history matters
- what just happened
- what is said on the surface
- what emotional and relational logic sits underneath

## Recommended Source-of-Truth Format

Use one human-readable file per case.

Recommended format:

- YAML
- or Markdown with front matter

Avoid starting with only raw JSONL. Human-authored annotation and review will be much easier in YAML / Markdown.

## Minimal Required Fields

### Metadata

- `case_id`: unique identifier
- `language`: expected to be `zh`
- `setting_type`: e.g. modern, historical, xianxia, fantasy, sci-fi, custom
- `interaction_type`: e.g. romance, rivalry, hierarchy, betrayal, restrained_care
- `difficulty`: e.g. low, medium, high
- `tags`: list of descriptive tags

### Scene Context

- `world_context`: relevant fictional setting or worldview constraints
- `speaker_profile`: profile of the current speaker
- `responder_profile`: profile of the target reply character
- `relationship_summary`: what matters about the relationship right now
- `recent_event`: what happened immediately before the utterance
- `previous_turns`: optional multi-turn context

### Current Utterance

- `target_utterance`: the line to interpret / answer

### Task A Gold Annotation

- `surface_meaning`: what the utterance literally says
- `primary_emotion`
- `secondary_emotions`
- `likely_emotions`: list form if needed
- `speaker_goal`: what the speaker is trying to achieve
- `speaker_fear`: what the speaker is trying to avoid or defend against
- `subtext`: what is implied but not directly stated
- `relationship_logic`: how the relationship changes the meaning of the line
- `ambiguity_notes`: what remains uncertain or underdetermined
- `good_response_should_preserve`: key things a correct reply must preserve
- `good_response_should_avoid`: common but wrong response tendencies

### Task B Gold Guidance

- `voice_constraints`: what the responder's voice should feel like
- `emotional_constraints`: how explicit, restrained, warm, cold, defensive, etc.
- `relationship_constraints`: what the reply must respect about the dynamic
- `worldview_constraints`: lore, era, etiquette, taboo, knowledge boundaries
- `acceptable_patterns`: general families of acceptable reply behavior
- `hard_fails`: hard-fail categories especially relevant to this case

### Evaluation Hooks

- `task_a_dimensions`: dimensions to emphasize for Task A
- `task_b_dimensions`: dimensions to emphasize for Task B
- `failure_tags`: likely failure categories this case is meant to expose

## Recommended Extended Fields

These fields are optional but useful.

- `notes_for_annotators`: special caution or subtlety in this case
- `common_misreadings`: plausible but incorrect interpretations
- `example_bad_responses`: representative failure patterns
- `example_good_response_properties`: high-level description without forcing one canonical answer
- `source_type`: original authored, adapted, synthetic, community-inspired, etc.
- `split`: pilot, dev, test, held_out

## Example Skeleton

```yaml
case_id: CNFER_0001
language: zh
setting_type: xianxia
interaction_type: restrained_intimacy
difficulty: high
tags:
  - indirect_speech
  - masked_hurt
  - hierarchy
  - therapist_mode_risk

world_context: >
  ...

speaker_profile: >
  ...

responder_profile: >
  ...

relationship_summary: >
  ...

recent_event: >
  ...

previous_turns:
  - speaker: A
    text: ...
  - speaker: B
    text: ...

target_utterance: "没关系，你去吧。"

task_a_gold:
  surface_meaning: >
    ...
  primary_emotion: hurt
  secondary_emotions:
    - resignation
    - defensive_distancing
  speaker_goal: >
    ...
  speaker_fear: >
    ...
  subtext: >
    ...
  relationship_logic: >
    ...
  ambiguity_notes: >
    ...
  good_response_should_preserve:
    - emotional restraint
    - unresolved tension
    - sensitivity to hidden hurt
  good_response_should_avoid:
    - assuming true acceptance
    - direct therapeutic labeling
    - flattening the relationship

task_b_gold:
  voice_constraints: >
    ...
  emotional_constraints: >
    ...
  relationship_constraints: >
    ...
  worldview_constraints: >
    ...
  acceptable_patterns:
    - ...
  hard_fails:
    - therapist_mode_intrusion
    - relationship_flattening
    - overexplicit_emotion_naming

scoring:
  task_a_dimensions:
    - emotion_inference_accuracy
    - subtext_recognition
    - relationship_logic_alignment
    - ambiguity_calibration
  task_b_dimensions:
    - character_voice_fidelity
    - emotional_logic_preservation
    - relationship_dynamic_preservation
    - natural_scene_continuation
  failure_tags:
    - emotion_misread
    - therapist_mode_intrusion
    - tension_premature_resolution
```

## Schema Guidelines

### 1. Cases should encode scene logic, not just vibes

A case should make clear why the utterance is hard:

- indirect wording
- hidden tension
- relationship asymmetry
- conflicting motives
- lore constraints
- ambiguity

### 2. Do not overfit to one exact gold response

For Task B, the benchmark should define a **space of acceptable replies**, not pretend there is only one perfect sentence.

### 3. Preserve ambiguity honestly

If a scene has two plausible emotional readings, record that instead of inventing fake certainty.

### 4. Make hidden constraints explicit for evaluators

If the difficulty depends on taboo, hierarchy, defensiveness, or knowledge asymmetry, write that down clearly.

### 5. Cases should be adversarial against shallow fluency

The ideal case is one where a weak model can sound smooth, but a strong evaluator can still see why the response is fundamentally wrong.

## Pilot Set Recommendations

The first pilot cases should cover a small number of high-value scenario families:

- indirect hurt
- restrained care
- hierarchy / power asymmetry
- betrayal / trust fracture

This is better than trying to cover every genre immediately.
