# Style Guidelines

This document defines the writing and aesthetic standards for benchmark cases and gold responses.

The benchmark is about fictional emotional reasoning, not cheap genre signaling. Cases should therefore sound real, grounded, and semantically loaded.

## Core Principle

A scene should feel alive because the emotional and relational logic is real.

It should not feel intense merely because it uses familiar dramatic phrases.

## Target Register

For the pilot benchmark, the preferred register is:

- natural contemporary Chinese dialogue
- emotionally precise rather than florid
- restrained where restraint is appropriate
- dark when the scene is dark, but not decorative for its own sake

Cases may later include other registers, but the default standard should remain grounded rather than performatively literary.

---

## What Good Benchmark Writing Should Do

### 1. Carry actual scene information

Every line should help establish:

- feeling
- motive
- pressure
- relationship state
- implied meaning

### 2. Sound like something a person in that scene would actually say

Even in stylized settings, dialogue should feel earned by the character and world.

### 3. Preserve restraint when restraint is part of the point

Not all emotional accuracy requires emotional explicitness.

### 4. Use style to support meaning, not replace it

Aesthetic wrapper is allowed. Aesthetic emptiness is not.

---

## What the Benchmark Should Avoid

### 1. Webnovel register contamination

The benchmark should explicitly avoid prefab webnovel / cheap online-fiction language that sounds dramatic without carrying real scene logic.

Examples of the problem type:

- "眸色暗了暗"
- "那是猎人看见猎物的眼神"
- other stock dangerous-man / prey metaphors inserted without earned context

This kind of language is often:

- semantically vague
- emotionally generic
- overfitted to internet genre residue
- falsely intense

When it appears without real support from the scene, it should be treated as a quality failure, not a style flourish.

### 2. Aestheticized vagueness

Avoid lines that sound pretty or heavy but say very little.

Bad benchmark writing should not be able to hide behind texture.

### 3. Borrowed intimacy

Avoid generic seductive, obsessive, or dangerous phrasing that is not grounded in the characters' actual relationship.

### 4. Genre pastiche instead of character logic

A scene should not become "dark romance mode" or "predator-prey mode" just because the model has seen those patterns in training data.

### 5. Overexplaining the psychology

Do not let benchmark cases or gold responses become mini-essays about what everyone feels.
The scene should remain a scene.

---

## Benchmark-Relevant Style Failure Labels

The following style-contamination errors are important enough to track explicitly.

### `webnovel_register_contamination`

The output slips into stock webnovel phrasing or melodramatic residue that is not contextually earned.

### `aestheticized_vagueness`

The output sounds emotionally loaded or literary, but carries weak actual meaning.

### `borrowed_intimacy`

The output uses canned seductive / dark / obsessive language without grounding in character logic.

### `genre_pastiche_overreach`

The output overperforms a genre mask instead of responding to the actual scene.

---

## Guidelines for Case Authors

When authoring benchmark cases:

- prefer concrete, natural, emotionally legible lines
- avoid decorative metaphors unless the character would genuinely think or speak that way
- do not import stock internet romance language as shortcut texture
- if a line is stylized, make sure the stylization itself carries information
- if a setting is historical or speculative, keep the diction controlled and meaningful rather than faux-epic

---

## Guidelines for Gold Responses

When writing ideal response properties:

- optimize for character and scene truth, not prettiness
- do not reward lines just because they sound quotable
- preserve subtext where subtext matters
- allow silence, deflection, terseness, or logistical care if those are more character-faithful than verbal tenderness

---

## Notes on Darkness

The benchmark is allowed to include dark, possessive, coercive, or psychologically unstable material when relevant.

However, darkness should be treated as content, not as style permission.

A dark scene still needs:

- coherent motive
- relationship logic
- believable voice
- contextual meaning

Darkness is not an excuse for sloppy language.

---

## Bottom Line

The benchmark should reject fake intensity.

If a line feels dramatic only because it smells like recycled web fiction, it is probably not good enough.

The target is not generic prettiness. The target is scene truth.
