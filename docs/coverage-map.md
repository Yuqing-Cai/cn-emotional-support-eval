# Coverage Map

This document defines how the benchmark should pursue broad eventual coverage without trying to include everything at once.

The correct goal is not "cover every kink immediately."
The correct goal is:

> build a principled coverage map, then sample pilot cases across it in a controlled way.

This avoids an arbitrary or biased dataset while keeping the project feasible.

---

## 1. Coverage Philosophy

Broad coverage should come from structured sampling, not uncontrolled accumulation.

A useful benchmark should know:

- which relational logics it already covers
- which frames are overrepresented
- which failure modes have not been stress-tested yet
- which scenario types are missing

The benchmark should therefore be planned as a matrix.

---

## 2. Core Coverage Dimensions

The following dimensions should guide case selection.

### A. Emotional / Relational Logic

This is the most important dimension.

Possible values include:

- hidden hurt
- defensive distancing
- reassurance-seeking
- jealousy / rival sensitivity
- dependency panic
- shame-defense
- specialness test
- punishment through politeness
- concealed care
- reluctant protection
- dominance test
- submission through indirection
- resentment under obligation
- taboo desire with self-restraint
- emotional splitting
- controlled cruelty
- projected devotion
- functional attachment vs person-directed attachment

These categories are not all final labels, but they are the right kind of unit.

### B. Relationship Frame

Possible frames include:

- lovers
- exes
- situationship / unstable intimacy
- friends with asymmetrical attachment
- superior / subordinate
- mentor / mentee
- creator / creation
- handler / asset
- captor / captive
- owner / pet-coded dynamic
- rivals / enemies
- protector / protected
- deity / follower
- healer / patient

Relationship frame matters because the same utterance means something different in a different frame.

### C. Ontology Axes

The case set should be distributed across high-value axis combinations from the OC system.

Examples:

- `E1 + J1`: mouth-hard / emotionally illiterate
- `E5 + J2`: care through action, awkward emotional decoding
- `D1 + V2`: high-status character who sees the other as medicine
- `D2 + V1`: lower-status character for whom the other is an anchor
- `L2 + A2`: function-love with person-trigger weakness
- `M4 + C2`: ambition under pressure, logic failing under attachment

The ontology is not just metadata; it is a coverage engine.

### D. Setting / World Constraint

Possible setting lanes:

- contemporary realism
- urban hidden-world
- historical / court / jianghu / xianxia
- sci-fi / posthuman
- post-apocalyptic
- gothic / dark fantasy

World setting matters because worldview constraints affect what counts as plausible expression or reply.

### E. Style / Register Risk

The benchmark should also cover style-failure risk.

Examples:

- natural contemporary dialogue
- controlled stylization
- restrained archaic register
- dark but realistic compression
- anti-webnovel cases where false melodrama is especially tempting

### F. Failure Mode Targets

Each case should target at least one primary failure mode and optionally several secondary ones.

Primary failure targets may include:

- emotion_misread
- subtext_blindness
- relationship_logic_error
- therapist_mode_intrusion
- relationship_flattening
- supportive_but_wrong
- webnovel_register_contamination
- tension_premature_resolution

---

## 3. Pilot Coverage Strategy

The pilot should not aim for completeness.
It should aim for strategic diversity.

Recommended pilot size:

- 12 cases

Recommended pilot design:

- 4 core clusters
- 3 cases per cluster

### Cluster A — indirect hurt / defensive distancing

Focus:

- literal permission vs actual hurt
- politeness as punishment
- reassurance-seeking through withdrawal

Likely axis emphasis:

- `E1`, `E2`, `J1`, `J2`, `V1`, `V3`

Likely failure targets:

- emotion_misread
- subtext_blindness
- therapist_mode_intrusion

### Cluster B — concealed care / awkward tenderness

Focus:

- care expressed through logistics, command, or irritation
- action over verbal softness
- emotionally inarticulate protection

Likely axis emphasis:

- `E1`, `E5`, `J1`, `J2`, `L1`, `L2`

Likely failure targets:

- overexplicit_emotion_naming
- supportive_but_wrong
- voice_fidelity_failure

### Cluster C — hierarchy / asymmetry / control

Focus:

- power imbalance
- role pressure
- love under unequal authority
- lower-status transgression or higher-status restraint

Likely axis emphasis:

- `D1`, `D2`, `V1`, `V2`, `V4`, `R1`, `R2`

Likely failure targets:

- relationship_flattening
- ooc_modernization
- worldview_constraint_error

### Cluster D — fracture / jealousy / destabilization

Focus:

- betrayal
- specialness anxiety
- function-love vs real-love tension
- rupture around weakness triggers

Likely axis emphasis:

- `L2`, `L3`, `A2`, `A3`, `M2`, `M4`, `S2`, `S3`

Likely failure targets:

- motivation_misread
- supportive_but_wrong
- tension_premature_resolution
- webnovel_register_contamination

---

## 4. What Counts as Balanced Coverage

A pilot set is reasonably balanced if:

- not all scenes are the same relationship type
- not all scenes depend on the same emotion label
- not all scenes reward the same response mode
- not all scenes come from the same aesthetic register
- at least several high-value ontology interactions are tested
- the major failure categories are each targeted by at least one case

---

## 5. Expansion Strategy After Pilot

After the 12-case pilot, the next expansion should be driven by gaps in the coverage matrix.

Questions to ask:

- Which ontology combinations are not yet represented?
- Which failure modes almost never trigger?
- Are contemporary scenes overrepresented compared with historical or speculative ones?
- Are dark dependency cases overrepresented relative to cleaner hidden-hurt cases?
- Are models only failing where style risk is high, or also where logic risk is high?

Expansion should be deliberate, not additive by impulse.

---

## 6. Suggested Tracking Table

For internal planning, each case should eventually be logged in a table with columns like:

- `case_id`
- `cluster`
- `setting`
- `relationship_frame`
- `primary_logic`
- `motive_axis`
- `expression_axis`
- `empathy_axis`
- `dynamic_axis`
- `view_axis`
- `love_axis`
- `stability_axis`
- `primary_failure_target`
- `secondary_failure_targets`

This makes the benchmark auditable and easier to extend rationally.

---

## 7. Bottom Line

Coverage should be broad in principle, but selective in implementation.

The benchmark should grow by:

1. defining the ontology and coverage map
2. building a controlled pilot slice
3. analyzing model failures
4. expanding toward under-covered areas

That is how the project becomes large without becoming incoherent.
