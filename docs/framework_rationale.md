# Framework Rationale

This document explains why the benchmark is structured around **fictional emotional reasoning**, **relationship logic**, and **in-character response fidelity**, rather than vague ideas like whether a reply sounds mature, warm, or generally high-EQ.

## Positioning

The benchmark does not evaluate abstract "emotional intelligence" in the broadest sense.

It evaluates whether a model can handle a specific kind of difficult fictional dialogue, where quality depends on:

- reading indirect and masked feeling
- understanding why the line is said this way
- respecting hierarchy, intimacy, resentment, taboo, or dependency
- staying inside the target character's voice and worldview
- avoiding subtle OOC responses that sound fluent but break the scene

## Why This Framework Exists

### 1. Fictional dialogue failure is not the same as generic dialogue failure

A model may perform well on broad conversational metrics while still failing badly in RP-style scenes.

Typical examples:

- it reads literal wording but misses subtext
- it gives emotionally supportive advice when the scene requires restraint or character-specific defensiveness
- it sounds polished but flattens the relationship dynamic
- it preserves fluency while violating the emotional logic of the moment

This means generic helpfulness or broad empathy evaluation is not enough.

### 2. Persona fidelity alone is not enough

Broad persona consistency is useful, but it does not fully capture scene-level failure.

A model can remain broadly aligned with a persona while still:

- misreading the speaker's real feeling
- failing to recognize what relational move the speaker is making
- resolving tension in a way the character never would
- applying modernized emotional norms that do not fit the world

That is why the benchmark combines character fidelity with emotional and relational reasoning.

### 3. Lore correctness alone is not enough

Roleplay quality is not exhausted by whether the model remembers facts.

A model can know the world and still fail the scene by:

- misunderstanding hidden hurt
- ignoring shame or pride
- treating unequal relationships like equal ones
- becoming too therapist-like or too explicit

This is why lore / worldview adherence is one dimension, not the entire framework.

### 4. Nice-sounding outputs are often the wrong outputs

One of the most important motivations for this benchmark is that roleplay models often fail in a deceptively polished way.

The reply may be:

- kind
- articulate
- emotionally literate
- conflict-reducing

—and still be wrong.

Wrong because it:

- erases tension
- overstates what should remain unspoken
- makes the character too healthy or self-aware
- imposes contemporary communication norms on the setting
- treats a loaded fictional scene like a customer-support conversation

This is why the benchmark must distinguish **supportive but wrong** from genuinely scene-faithful quality.

## Why the Benchmark Is Split into Two Tasks

### Task A — Scene Understanding

This task measures whether the model actually understands:

- the emotional state
- the subtext
- the motive or defense pattern
- the relationship logic
- what a good response should preserve or avoid

This matters because response quality cannot be diagnosed cleanly if interpretive competence is hidden.

### Task B — In-Character Response

This task measures whether the model can then produce a reply that remains:

- in character
- emotionally plausible
- relationship-aware
- world-consistent
- natural as a continuation of the scene

Separating the tasks helps distinguish:

- misunderstanding failures
- generation failures
- mixed failures

## Why Fine-Grained Failure Analysis Matters

Whole-response scoring is too blunt for this domain.

A reply can be:

- partly in character, partly OOC
- emotionally accurate but stylistically wrong
- stylistically accurate but relationally wrong
- lore-consistent but emotionally dead

That is why the benchmark should combine:

- dimension scores
- hard-fail tags
- qualitative failure analysis

This is more useful than pretending a single total score explains everything.

## Chosen Evaluation Priorities

### 1. Emotion inference

Because a model cannot respond well if it misreads the core feeling.

### 2. Subtext recognition

Because many fictional scenes rely on what is implied rather than stated.

### 3. Relationship logic

Because the same sentence means different things under different histories, power structures, and intimacy levels.

### 4. Character voice fidelity

Because fluent generic language is not enough in roleplay.

### 5. Worldview and lore adherence

Because fictional meaning depends partly on what the world allows and what the character can know.

### 6. Scene continuation quality

Because a good reply should feel like the next move in the scene, not like an outside analysis or therapy script.

## What the Framework Intentionally Does Not Prioritize

### 1. Warmth as a standalone metric

Warmth can be faked and can even hide dependency-building or character flattening. The benchmark cares more about whether warmth is appropriate to the character and scene.

### 2. Human-likeness in the abstract

A reply does not need to sound maximally human. It needs to sound like the correct character in the correct world at the correct moment.

### 3. Generic helpfulness

This is too broad and tends to drag the benchmark back toward assistant-style evaluation.

### 4. One single total quality number

The project should support summary scores, but not at the cost of hiding the exact failure mode.

## Design Implications

This rationale supports the following design choices:

- narrow scope instead of broad roleplay benchmarking
- separate Task A and Task B
- explicit failure taxonomy
- case schema that encodes scene logic, not just prompts
- pilot cases that target hard RP-native failure modes
- reporting that includes both scores and hard-fail patterns

## Bottom Line

The benchmark is built on one central idea:

> In fictional dialogue, the hardest failures are often not crude mistakes. They are fluent, polished, emotionally competent-seeming replies that still break character, relationship logic, or scene tension.

That is exactly what this framework is meant to catch.
