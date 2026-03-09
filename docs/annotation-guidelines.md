# Annotation Guidelines

This document explains how to author and annotate benchmark cases for fictional emotional reasoning and in-character response evaluation.

The benchmark is designed for scenes where models often sound fluent but fail the actual emotional and relational logic.

## Annotation Philosophy

The goal is not to reward whatever sounds most mature, nice, or emotionally articulate.

The goal is to judge whether a model understood and preserved:

- the speaker's actual feeling
- the speaker's motive or defensive posture
- the relationship dynamic
- the world / lore constraints
- the target character's believable response style

A response can be well-written and still be wrong.

## Overall Workflow

Recommended annotation flow:

1. author the case
2. write Task A gold interpretation
3. write Task B response constraints
4. identify common wrong readings
5. identify relevant hard-fail patterns
6. run model samples if available
7. revise the case or rubric if necessary

## Part I — Writing Task A Gold Interpretation

Task A is about scene understanding.

Annotators should answer the following questions.

### 1. What does the line say literally?

Write a brief `surface_meaning`.

This prevents annotators from jumping straight into subtext and losing the literal layer.

### 2. What is the speaker actually feeling?

Record:

- `primary_emotion`
- `secondary_emotions`
- intensity or masking notes if needed

Try to avoid overly generic labels when the case supports something sharper.

Bad:
- sad
- angry

Better:
- hurt with defensive withdrawal
- restrained jealousy masked as politeness
- shame mixed with dependence

### 3. What is the speaker trying to do?

Record `speaker_goal`.

Possible goals include:

- testing the other person
- protecting pride
- asking for reassurance indirectly
- creating distance
- preserving dignity
- punishing without admitting it
- offering care while hiding vulnerability

### 4. What is the speaker trying to avoid?

Record `speaker_fear` when relevant.

Examples:

- fear of rejection
- fear of looking needy
- fear of losing status
- fear of emotional exposure
- fear of violating role obligations

### 5. What is the subtext?

Record `subtext` as the implied meaning beneath the literal line.

This should capture what a good reader would hear but the text does not say directly.

### 6. How does the relationship change the meaning?

Record `relationship_logic`.

This should answer:

- why this line means something different in this relationship than it would in a generic conversation
- what intimacy, history, power, duty, taboo, or betrayal adds to interpretation

### 7. What remains ambiguous?

Use `ambiguity_notes`.

Do not fake certainty.

If the scene supports more than one plausible reading, record that honestly.
The benchmark should reward calibrated interpretation, not just confident overreach.

## Part II — Writing Task B Gold Guidance

Task B is about in-character response generation.

The goal is not to define one exact canonical sentence. The goal is to define what a correct response must preserve and what common failure patterns look like.

### 1. Define voice constraints

Record `voice_constraints`.

Examples:

- terse, controlled, emotionally indirect
- formal but intimate beneath the surface
- dry, proud, not likely to self-disclose directly
- gentle in action but not verbally soft

### 2. Define emotional constraints

Record `emotional_constraints`.

Examples:

- should acknowledge hurt without naming it too explicitly
- should not become suddenly warm or confessional
- should preserve the speaker's defensive dignity
- should remain restrained even if caring

### 3. Define relationship constraints

Record `relationship_constraints`.

Examples:

- preserve power asymmetry
- do not erase mistrust
- do not treat them like equal casual friends
- must respect existing intimacy but not overstep taboo

### 4. Define worldview constraints

Record `worldview_constraints`.

Examples:

- avoid modern therapy language
- respect historical etiquette
- do not use knowledge the character should not have
- do not impose contemporary moral assumptions on the scene

### 5. Define acceptable response patterns

Record `acceptable_patterns` as general families, not one perfect line.

Examples:

- indirect reassurance
- restrained acknowledgment
- logistical care instead of explicit affection
- deflection plus small concession
- formal wording with hidden softness

### 6. Define hard fails

Record `hard_fails` relevant to the case.

Typical hard fails include:

- therapist_mode_intrusion
- ooc_modernization
- relationship_flattening
- lore_violation
- meta_or_exposition_leak
- overexplicit_emotion_naming
- tension_premature_resolution

## Part III — Common Annotation Mistakes

### Mistake 1: rewarding emotional niceness instead of scene fidelity

A response can be kind, healthy, and articulate while still being wrong for the character.

### Mistake 2: collapsing indirect feeling into literal meaning

If a character says "没关系" that does not automatically mean acceptance.

### Mistake 3: treating all close relationships the same

Romantic tension, loyalty, dependency, resentment, hierarchy, and taboo are not interchangeable.

### Mistake 4: over-explaining hidden feelings

A model should not automatically score higher for stating the psychology more explicitly.
Sometimes explicitness is itself OOC.

### Mistake 5: ignoring ambiguity

Some cases are intentionally layered. The benchmark should allow partially uncertain but well-calibrated interpretations.

## Part IV — Adjudication Rules

When annotators disagree, resolve in this order:

1. check whether both readings are actually plausible under the written context
2. prefer the reading that is better grounded in relationship logic and recent event history
3. if ambiguity is genuinely unresolved, encode that ambiguity instead of forcing one reading
4. revise the case if the intended reading is too under-specified

## Part V — Recommended Quality Checklist for Each Case

Before a case is finalized, ask:

- Is the scene hard for the right reason?
- Is the emotional logic actually legible to a careful human reader?
- Is the relationship dynamic clear enough to matter?
- Does the case expose a known RP-native failure mode?
- Would a generic high-EQ response potentially fail here?
- Are acceptable responses broader than one exact line?
- Are hard fails clearly defined?

## Part VI — Suggested Pilot Annotation Strategy

For the first pilot set:

- start with 12 cases
- annotate them manually
- run several strong models
- inspect where the rubric breaks
- revise taxonomy and case wording before scaling up

The point of the pilot is not volume. The point is to make the benchmark semantically sharp before it becomes large.
