# Failure Taxonomy

This document defines the main failure modes the benchmark is designed to expose.

The goal is not to collapse all errors into one generic "bad response" label. Fictional dialogue failure is multi-dimensional. A model can be fluent, kind, and even lore-aware while still failing the scene.

The taxonomy is divided into two layers:

- interpretation failures (mainly Task A)
- response failures (mainly Task B)

---

## I. Interpretation Failures

These failures occur when the model misunderstands what the scene means.

### 1. emotion_misread

The model gets the speaker's actual feeling wrong.

Typical examples:

- reading hurt as calm acceptance
- reading defensive coldness as genuine indifference
- reading shame as anger only
- reading jealousy as simple irritation

Why it matters:

If the emotion is wrong, the response will often be wrong even if it sounds smooth.

---

### 2. subtext_blindness

The model captures only the literal meaning and misses what is implied.

Typical examples:

- taking "你去吧" as simple permission instead of hurt withdrawal
- missing that a question is actually a test
- missing that politeness is functioning as distance or punishment

Why it matters:

Many RP scenes are driven by implied meaning, not explicit wording.

---

### 3. motivation_misread

The model misunderstands what the speaker is trying to do.

Typical examples:

- treating a request for reassurance as a request for advice
- treating a defensive retreat as genuine closure
- treating provocation as casual conversation

Why it matters:

A line can be emotionally legible but still be misread functionally.

---

### 4. relationship_logic_error

The model ignores or misreads the interpersonal structure shaping the utterance.

Typical examples:

- ignoring hierarchy or power asymmetry
- treating betrayal scenes like ordinary disagreement
- ignoring taboo, dependency, resentment, or long history

Why it matters:

The same sentence means different things in different relationships.

---

### 5. worldview_constraint_error

The model interprets the scene using assumptions that do not fit the fictional setting.

Typical examples:

- assuming modern communication norms in a historical or fantasy world
- ignoring formal etiquette or role obligations
- reading emotional directness as available when the setting discourages it

Why it matters:

Meaning is shaped by world constraints, not just by sentence content.

---

### 6. ambiguity_collapse

The model acts too certain when the scene remains intentionally layered.

Typical examples:

- asserting one neat emotional explanation when several remain plausible
- overcommitting to a single motive where the case is underdetermined

Why it matters:

A strong evaluator should reward calibrated interpretation, not fake certainty.

---

## II. Response Failures

These failures occur when the model generates a reply that breaks character, logic, or scene quality.

### 1. ooc_modernization

The reply sounds like a modern internet-savvy or therapy-literate person rather than the target character.

Typical examples:

- importing contemporary self-help or communication norms into a non-modern setting
- making the character sound unusually emotionally processed or socially sanitized

Why it matters:

This is one of the most common and immersion-breaking RP failures.

---

### 2. therapist_mode_intrusion

The reply shifts into generic emotional support or counseling language that does not fit the character or scene.

Typical examples:

- "你的感受是被允许的"
- "先照顾好自己"
- reflective therapy-style summaries in situations where the character would never speak that way

Why it matters:

A response can sound emotionally competent while being catastrophically OOC.

---

### 3. relationship_flattening

The reply erases what is distinctive about the relationship.

Typical examples:

- treating a superior-subordinate dynamic like equal friendship
- erasing resentment or mistrust too quickly
- ignoring dependency, taboo, history, or specialness

Why it matters:

This failure often makes scenes feel generic and false even when the wording is smooth.

---

### 4. voice_fidelity_failure

The reply does not sound like something the target character would actually say.

Typical examples:

- wrong level of formality
- wrong pacing or emotional explicitness
- language too generic to carry character identity

Why it matters:

Character consistency is a core part of RP quality.

---

### 5. motivation_break

The response does not follow from the responder's own motives, values, fears, or role obligations.

Typical examples:

- sudden emotional honesty from a highly avoidant character
- immediate reassurance from a character who would normally deflect
- overhelpful guidance from a character who would preserve distance

Why it matters:

The response may fit the scene abstractly while still not fitting the responder.

---

### 6. lore_violation

The reply contradicts world facts, role knowledge, character knowledge boundaries, or setting rules.

Typical examples:

- using knowledge the character should not have
- violating established world logic
- implying attitudes or facts inconsistent with the setting

Why it matters:

Lore adherence is not the whole benchmark, but breaking it can strongly damage credibility.

---

### 7. meta_or_exposition_leak

The model stops sounding like a character and starts sounding like an analyst, narrator, or system.

Typical examples:

- explaining the scene instead of replying in-world
- inserting summary-style exposition
- using meta language such as "as this character"

Why it matters:

This breaks immersion and often hides weak scene modeling behind explanatory wording.

---

### 8. tension_premature_resolution

The reply resolves conflict, pain, or ambiguity too quickly.

Typical examples:

- turning a loaded scene into clean mutual understanding immediately
- healing a fracture that should remain unresolved
- collapsing romantic or hostile tension into generic safety

Why it matters:

Good RP often depends on preserving tension, not removing it.

---

### 9. overexplicit_emotion_naming

The reply says the quiet part out loud when the character or scene requires restraint.

Typical examples:

- directly labeling hidden hurt that should remain partially unspoken
- making the responder psychologically over-articulate in a way that breaks character

Why it matters:

Not every emotionally accurate response should be emotionally explicit.

---

### 10. supportive_but_wrong

The response is warm, kind, or emotionally competent on the surface but fundamentally incorrect for the character, relationship, or scene.

Typical examples:

- perfect emotional support language that destroys characterization
- comforting the speaker in a way that ignores the role dynamic
- making the response healthier than the world and people would allow

Why it matters:

This is one of the benchmark's signature failure modes. It captures why generic high-EQ outputs are not enough.

---

## III. Recommended Tagging Practice

Each evaluated output can receive:

- numerical dimension scores
- zero or more failure tags

Not every low-scoring response needs a hard-fail tag, but hard-fail tags should be used when a distinctive error pattern is clearly present.

## IV. Pilot Set Recommendations

The first pilot cases should be designed to specifically expose:

- emotion_misread
- subtext_blindness
- relationship_logic_error
- therapist_mode_intrusion
- relationship_flattening
- tension_premature_resolution
- supportive_but_wrong

These are likely to be the most visible and distinctive failure modes in early experiments.
