# Ontology Adaptation

This document explains how the OC-axis system should be adapted for the fictional emotional reasoning benchmark.

The goal is not to turn the benchmark into a character-generator project. The goal is to use the existing axis system as an underlying ontology for:

- coverage planning
- case metadata design
- failure analysis
- pilot set balancing

The OC-axis system is valuable because it does not merely list tropes. It decomposes fictional relationship design into interacting dimensions of world, motive, emotional processing, power structure, love logic, sacrifice, and aesthetic wrapper.

That is a much stronger foundation than flat trope lists or broad labels like "dominance" or "comfort."

---

## 1. Why This Ontology Matters for the Benchmark

The benchmark evaluates whether a model can correctly infer:

- what a character is actually feeling
- why they are expressing it this way
- what the relationship dynamic is doing to the line
- what kind of reply preserves the character and scene

Those questions require a deeper structure than generic emotion labels.

The OC-axis system already provides that structure.

Examples:

- `E + J` explains why emotional communication fails or lands
- `D + V` explains why the same line has radically different meanings in different relationships
- `L` explains whether attachment is person-directed, function-directed, or projection-directed
- `M + C + X` explains what love threatens, what the character would choose, and what the cost means

This is exactly the kind of hidden logic the benchmark needs.

---

## 2. The Benchmark Should Use the OC Axes as Hidden Design Infrastructure

The axes should not necessarily appear as front-page branding or be forced into every public case file.

Instead, they should serve as:

- design variables when writing cases
- metadata fields when useful
- interpretation aids for annotators
- analysis hooks when diagnosing model failures

The benchmark should remain scene-centered and human-readable.

---

## 3. Axis Categories for Benchmark Use

For benchmark purposes, the axes can be grouped into four functional families.

### A. Structural Context Axes

These define the outer conditions shaping scene meaning.

- `W` World — what kind of world the characters live in; what external pressure exists
- `B` Body — embodiment and touchability; what physical interaction means
- `P` Power — what kind of force or competence the character possesses
- `R` Role — whether the character upholds, breaks, or is abandoned by the current order

These axes often determine what counts as plausible behavior or allowable intimacy.

### B. Psychological / Relational Core Axes

These are the most important axes for scene-level interpretation.

- `M` Motive — what the character fundamentally lives for
- `C` Choice — how the character behaves when motive is threatened by love or attachment
- `E` Expression — how the character outputs feeling
- `J` Judgment / empathy — how the character receives or interprets feeling
- `S` Sanity — psychological stability or fracture pattern
- `D` Dynamic — power structure in the relationship
- `V` View — what the other person is in the character's eyes
- `L` Love — whether attachment is real, functional, or projected
- `A` Achilles — what breaks or destabilizes the character most deeply

These axes are the most directly useful for Task A and Task B benchmark design.

### C. Narrative Arc / Consequence Axes

These are especially useful for broader or more advanced cases.

- `T` Time — temporal cruelty, mismatch, memory, looping, life-span asymmetry
- `G` God-mode — scope of authority / ability to alter the system
- `X` eXchange — what cost the character pays
- `F` Finale — what relationship endpoint or form is implied or foreshadowed

These axes are less necessary for every short pilot scene, but very useful for richer datasets.

### D. Aesthetic Wrapper Axis

- `Palette` — aesthetic register or artistic wrapper

This axis matters, but it should stay orthogonal to emotional logic.

A model should not be rewarded merely for imitating palette. It should be rewarded for understanding the scene.

---

## 4. Priority Axes for the Pilot Benchmark

Not every axis needs equal weight in the pilot set.

The most important axes for the first pilot cases are:

### Highest priority

- `M` Motive
- `C` Choice under pressure
- `E` Expression
- `J` Judgment / empathy style
- `D` Dynamic
- `V` View / gaze
- `L` Love authenticity
- `S` Sanity / stability pattern
- `A` Achilles / weakness trigger

### Medium priority

- `W` World
- `R` Role
- `B` Body
- `P` Power

### Lower priority for initial pilot, higher priority later

- `T`
- `G`
- `X`
- `F`
- `Palette`

This prioritization keeps the pilot dataset centered on scene-level emotional and relational reasoning rather than sprawling immediately into long-arc narrative design.

---

## 5. Key Axis Interactions the Benchmark Should Reuse

The OC system is especially strong because it defines interactions between axes, not just isolated categories.

These interactions should directly inform benchmark construction.

### `E + J` = communication mode

This interaction explains many scene failures:

- indirect expression + low empathy leads to misread reassurance attempts
- defensive expression + overactive empathy leads to overinterpretation
- cold expression + high empathy can produce hidden care

This should become a major source of benchmark difficulty.

### `D + V` = relationship dynamic

Power alone is too broad. View / gaze explains what kind of power it is.

Examples:

- superior + anchor is very different from superior + prey
- subordinate + medicine is very different from subordinate + curse

This interaction is highly useful for both case metadata and gold interpretation.

### `L + A` = relationship depth and rupture risk

Love authenticity plus Achilles weakness determines whether the relationship is real attachment, dependency, projection, destabilization, or some mix.

This is especially valuable for darker cases.

### `M + C + X` = conflict logic

This interaction helps determine:

- what love threatens
- how the character reacts when destabilized
- what kind of sacrifice is meaningful or plausible

This is useful for advanced cases and for explaining why some generated replies feel fundamentally wrong.

---

## 6. How the Ontology Maps to Benchmark Tasks

### Task A — Scene Understanding

The ontology helps define what the model should infer:

- `E`, `J`, `S` help explain the emotional surface and distortion pattern
- `M`, `C`, `A` help explain underlying motive, pressure, and defense
- `D`, `V`, `L` help explain relationship meaning
- `W`, `R`, `B`, `P` help explain world and role constraints

### Task B — In-Character Response

The ontology helps define what the model must preserve:

- `E` constrains voice and expression style
- `J` constrains how emotionally perceptive the responder should sound
- `D`, `V`, `L` constrain the relationship logic of the reply
- `M`, `C`, `S`, `A` constrain the responder's plausible move under pressure
- `W`, `R`, `B`, `P` constrain worldview and role consistency

---

## 7. What the Benchmark Should Not Do with the Ontology

### 1. Do not force every case to instantiate every axis

That would make cases bloated and artificial.

### 2. Do not turn case files into taxonomic essays

Cases must stay readable and scene-centered.

### 3. Do not reward style imitation over semantic understanding

`Palette` should not dominate scoring.

### 4. Do not mistake trope presence for emotional logic

A case is not good just because it contains a dark trope. The benchmark cares about whether the model understands what the trope is doing in context.

---

## 8. Recommended Benchmark Metadata Derived from the Ontology

The benchmark should likely add a metadata section that captures a small subset of axis information per case.

Suggested fields:

- `world_axis`
- `motive_axis`
- `expression_axis`
- `empathy_axis`
- `dynamic_axis`
- `view_axis`
- `love_axis`
- `stability_axis`
- `weakness_axis`
- `palette_axis` (optional)

This allows later analysis such as:

- which models fail most on `E1 + J1` combinations
- whether `V2 you are medicine` cases trigger therapist-mode intrusion more often
- whether `L2 love your function` scenes are flattened into healthy romance by frontier models

---

## 9. Bottom Line

The OC-axis system should become the benchmark's hidden ontology.

It is better than generic trope lists because it captures:

- internal motive structure
- communication style
- power and gaze logic
- authenticity of attachment
- instability and rupture points
- narrative consequence
- aesthetic wrapper without confusing it for substance

This gives the benchmark a principled way to grow without becoming arbitrary or genre-biased.
