# Taxonomy v2 Proposal — Toward a Complete Failure Atlas

This document proposes refinements to the Chinese Fictional Dialogue Failure Atlas taxonomy based on identified gaps.

The goal is not to replace v1 but to extend it where coverage is thin, clarify boundaries where annotation is ambiguous, and add operational guidance for benchmark use.

---

## Core Philosophy: What Makes a Taxonomy "Complete"?

A comprehensive taxonomy should:

1. **Name everything that matters** — If experienced readers can feel a failure but can't name it, the taxonomy is incomplete.
2. **Distinguish everything that's different** — If two failures have different causes or require different fixes, they need separate tags.
3. **Guide annotation** — An annotator should be able to look at a case and reliably assign tags without guessing.
4. **Support benchmark design** — Each tag should have a clear answer to: "Can this be scored on a single case, or does it require cross-case comparison?"
5. **Point toward success** — A failure atlas without a sense of what "good" looks like risks becoming a list of sins without a path to virtue.

---

## Proposed Structural Changes

### 1. Add Layer V: Multi-Turn / Temporal Failures

The current taxonomy treats failures as single-beat events. But fictional RP unfolds across turns. New layer:

#### V-A. Accumulation Failures

**Anchor: `error_accumulation`**
Small misunderstandings compound over multiple turns into a scene that has drifted far from its intended trajectory.

Typical cases:
- Turn 1: slight emotion misread → Turn 3: completely wrong emotional register → Turn 5: scene is now a different genre
- Each individual turn is defensible, but the cumulative effect is derailment

**Derived: `drift_without_correction`**
The model fails to notice or correct gradual shifts in tone, relationship, or world logic over multiple turns.

**Derived: `recovery_blindness`**
When a user attempts mid-scene correction, the model either ignores it or over-corrects, breaking scene continuity.

Typical cases:
- User: "She wouldn't say that, she's more guarded"
- Model: "Oh! You're right. Let me restart." (breaks immersion)
- Or: Model continues as if the correction never happened

---

#### V-B. Continuity Failures

**Anchor: `turn_continuity_error`**
Information, emotional state, or physical positioning from previous turns is lost or contradicted.

Typical cases:
- Character was crying in turn 3, suddenly composed in turn 4 with no transition
- An object was placed on the table, now it's in someone's hand
- A decision was made, now it's treated as unresolved

**Derived: `emotional_state_reset`**
A character's emotional arc is reset to baseline without narrative justification.

**Derived: `spatial_blocking_error`**
Physical positions, movements, or staging are inconsistent across turns.

---

### 2. Expand Layer I-B: World Constraint Failures with Genre Subtypes

`worldview_constraint_error` is doing too much work. Add sub-classifications:

#### I-B-1. Temporal/Period Failures
- `anachronistic_intrusion`: Modern norms in historical settings
- `temporal_register_mismatch`: Contemporary voice in non-contemporary setting

#### I-B-2. Genre-Specific Logic Failures
- `cultivation_logic_error`: Xianxia-specific (cultivation stages, sect rules, karmic debt)
- `court_protocol_error`: Historical court drama (honor, face, indirectness rules)
- `urban_romance_logic_error`: Modern romance-specific (dating norms, social expectations)
- `horror_tension_error`: Horror/thriller-specific (information withholding, dread maintenance)
- `fantasy_lore_error`: Western fantasy-specific (magic systems, world rules)

#### I-B-3. Cultural Boundary Failures
- `western_ya_contamination`: Chinese characters speaking like Western YA protagonists
- `translation_style_intrusion`: English webnovel phrasing patterns in Chinese RP
- `cultural_script_mismatch`: Collectivist vs. individualist reasoning errors

---

### 3. Add Physical Action and Staging Failures (New Section III-E)

The current taxonomy is dialogue-heavy. Add:

#### III-E. Physical and Staging Preservation Failures

**Anchor: `action_dialogue_mismatch`**
Character's described physical action contradicts their spoken words, and the model doesn't notice.

Typical cases:
- "[steps back]" + "Come closer"
- "[looking away]" + "Look at me"
- Action shows comfort, dialogue shows tension (or vice versa) without intentional irony

**Anchor: `blocking_continuity_error`**
Spatial relationships change impossibly across turns.

Typical cases:
- Character was across the room, now suddenly touching without movement described
- Two characters can't both be where the model says they are

**Anchor: `microreaction_mechanization`**
Physical reactions follow a template rather than responding to scene specifics.

Typical cases:
- Every emotional beat gets: eyes → breath → hands → silence → posture
- Reactions feel assembled from parts rather than lived

**Derived: `touchgrammar_error`**
Models mishandle physical contact—who touches whom, when, how, and what it means.

Typical cases:
- Touch introduced too early for the relationship stage
- Touch withdrawn when it should continue
- Touch meaning misread (comfort vs. control vs. intimacy)

---

### 4. Add Silence and Non-Response Failures (New Section III-F)

Silence is a major communicative tool in Chinese fictional dialogue. Add:

#### III-F. Silence and Non-Response Failures

**Anchor: `forced_verbalization`**
Model makes a silent character speak when silence was the point.

Typical cases:
- Character is meant to be speechless; model gives them articulate response
- Pause is filled with explanation when it should remain empty

**Anchor: `silence_misread`**
Model interprets silence as agreement / anger / indifference without scene justification.

Typical cases:
- Silence as punishment read as acceptance
- Silence as overwhelm read as coldness
- Silence as processing read as rejection

**Anchor: `over_narrated_silence`**
Model describes silence in a way that destroys its weight.

Typical cases:
- "The silence stretched between them, heavy with unspoken words" (tells instead of lets it land)
- Silence explained immediately after it occurs
- Multiple paragraphs about what the silence means

**Derived: `pause_timing_error`**
Model doesn't know when to pause vs. when to continue.

---

### 5. Add Humor, Irony, and Tonal Failures (New Section II-D)

The taxonomy assumes emotionally heavy scenes. Add:

#### II-D. Humor and Tone Reading Failures

**Anchor: `irony_blindness`**
Model misses sarcasm, irony, or playful banter.

Typical cases:
- Sarcastic compliment taken literally
- Playful teasing read as genuine criticism
- Deadpan humor treated as serious statement

**Anchor: `tonal_whiplash`**
Model introduces levity where there should be tension, or vice versa.

Typical cases:
- Joke inserted into heavy scene
- Heavy exposition inserted into light scene
- Emotional register shift without transition

**Anchor: `deflection_blindness`**
Model misses when a character uses humor to deflect from vulnerability.

Typical cases:
- Character jokes to avoid answering; model takes joke at face value
- Deflection read as genuine topic change

---

### 6. Expand Power Dynamics (Under III-A)

Current `symmetry_bias` is good but narrow. Add:

#### III-A-Expanded. Power and Desire Dynamics

**Anchor: `seduction_logic_error`**
Model mishandles pursuit, resistance, escalation, or retreat in desire-driven scenes.

Typical cases:
- Pursuit becomes aggression
- Resistance becomes rejection (when it's actually invitation)
- Escalation happens too smoothly without friction

**Anchor: `manipulation_blindness`**
Model misses or sanitizes manipulation patterns.

Typical cases:
- Gaslighting not recognized as such
- Guilt-tripping read as genuine concern
- Emotional blackmail treated as normal request

**Anchor: `consent_flattening`**
Scenes with ambiguous, shifting, or contested consent are resolved too cleanly.

Typical cases:
- Ambiguity collapsed into clear yes or no
- Withdrawn consent not recognized
- Enthusiastic consent assumed without basis

**Derived: `power_romanticization`**
Unequal power dynamics are written as more romantic or acceptable than the scene supports.

---

### 7. Clarify Layer II vs. Layer III Boundary

Add explicit diagnostic questions:

#### II vs. III Diagnostic Protocol

When annotating, ask in order:

1. **Did the model demonstrate understanding anywhere in the response?**
   - If yes → likely Layer III (preservation failure)
   - If no → likely Layer II (reading failure)

2. **Can I point to a specific line where the model showed it understood?**
   - If yes → Layer III
   - If no → Layer II

3. **If the model had been asked to explain the scene, would it get it right?**
   - This is hypothetical but helps: if you think the model "knows better" but wrote it wrong anyway → Layer III

4. **Is the failure about input (understanding) or output (generation)?**
   - Input → Layer II
   - Output → Layer III

**Hybrid Tag: `reading_preservation_hybrid`**
When it's genuinely impossible to distinguish, use this tag plus the most likely layer.

---

### 8. Add Success Patterns Document

Create companion document `docs/success-patterns.md`:

#### What Success Looks Like

**Scene Understanding Success:**
- Correctly identifies primary and secondary emotions
- Recognizes subtext and explains the surface/depth gap
- Understands how relationship transforms meaning
- Identifies the character's actual goal vs. stated goal

**In-Character Response Success:**
- Sounds like the character, not the model
- Preserves relationship asymmetry without flattening
- Maintains world constraints naturally
- Takes appropriate action (not too much, not too little)
- Leaves appropriate residue (doesn't over-resolve)

**Multi-Turn Success:**
- Maintains continuity across turns
- Notices and corrects drift
- Builds on previous turns without repetition
- Knows when to escalate, maintain, or de-escalate

---

### 9. Add Tag Operability Matrix

Create `docs/tag-operability.md`:

| Tag | Single-case detectable? | Automatable? | Training signal? | Benchmark dimension? |
|-----|------------------------|--------------|------------------|---------------------|
| `reference_boundary_failure` | Yes | Partially | Yes | Yes |
| `subtext_blindness` | Yes | No | Yes | Yes |
| `relationship_flattening` | Yes (with context) | No | Yes | Yes |
| `narrative_template_intrusion` | No (needs cross-case) | No | Limited | Casebook only |
| `voice_homogenization` | No (needs multi-character) | No | Limited | Casebook only |
| `error_accumulation` | No (needs multi-turn) | No | Yes | Yes (multi-turn) |
| ... | ... | ... | ... | ... |

This tells users what each tag is actually useful for.

---

### 10. Cross-Cultural Edge Cases

Add under I-B:

#### I-B-4. Cross-Cultural RP Failures

**Anchor: `cultural_register_mismatch`**
Character from Culture A speaks with Culture B's conversational norms.

Typical cases:
- Chinese historical character with Western individualist reasoning
- Western fantasy character with Chinese webnovel pacing

**Anchor: `bilingual_contamination`**
When RP involves code-switching or translation, meaning is lost.

Typical cases:
- Chinese emotion expressed in English loses nuance
- English concept translated to Chinese feels off

---

## Recommended Top-Level Index Tags (v2)

Updated from v1:

**Layer I: Preconditions**
- `reference_boundary_failure`
- `worldview_constraint_error` (with genre subtypes)
- `turn_continuity_error` (NEW)

**Layer II: Reading**
- `subtext_blindness`
- `emotion_misread`
- `motivation_misread`
- `relationship_logic_blindness`
- `irony_blindness` (NEW)

**Layer III: Preservation**
- `relationship_flattening`
- `overcoherent_characterization`
- `desire_overlegibility`
- `self_protective_friction_loss`
- `consequence_avoidance`
- `tension_premature_resolution`
- `action_dialogue_mismatch` (NEW)
- `forced_verbalization` (NEW)

**Layer IV: Intrusion**
- `narrative_template_intrusion`
- `scene_pacing_distortion`
- `descriptive_substitution_for_experience`
- `dialogue_overfunctionalization`
- `voice_homogenization`

**Layer V: Multi-Turn** (NEW)
- `error_accumulation`
- `drift_without_correction`
- `recovery_blindness`

**Cross-Cutting Diagnostic:**
- `supportive_but_wrong`
- `reading_preservation_hybrid` (NEW)

---

## Implementation Priority

**Phase 1 (High priority, benchmark-ready):**
- Layer V additions (multi-turn failures)
- II vs. III boundary clarification
- Success patterns document

**Phase 2 (Medium priority, casebook enrichment):**
- Physical action failures
- Silence failures
- Humor/irony failures

**Phase 3 (Lower priority, genre-specific):**
- Genre subtypes under worldview_constraint_error
- Cross-cultural edge cases

**Phase 4 (Infrastructure):**
- Tag operability matrix
- Annotation guidance updates

---

## Open Questions

1. Should genre-specific subtypes be separate tags or modifiers (e.g., `worldview_constraint_error:cultivation`)?
2. How do we handle cases where multiple failures in the same turn have different layers?
3. Should success patterns be integrated into the taxonomy or kept separate?
4. What's the minimum number of turns needed to detect Layer V failures?

---

This proposal extends the taxonomy without breaking existing annotations. All v1 tags remain valid; new tags fill gaps.
