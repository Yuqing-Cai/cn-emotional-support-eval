# Tag Operability Matrix

This document classifies each failure tag by its operational characteristics — what you can actually DO with each tag.

## Classification Dimensions

| Dimension | Values | Meaning |
|-----------|--------|---------|
| **Detection scope** | `single-case`, `multi-turn`, `cross-case` | How much context is needed to detect this failure |
| **Automatability** | `yes`, `partial`, `no` | Can this be detected by automated systems |
| **Training signal** | `yes`, `limited`, `no` | Can this provide useful feedback for model training |
| **Benchmark dimension** | `yes`, `casebook-only` | Should this be a scored dimension or just for casebook display |
| **Annotation reliability** | `high`, `medium`, `low` | How consistently can annotators agree on this tag |

---

## Layer I: Preconditions

| Tag | Detection | Automatable | Training | Benchmark | Reliability | Notes |
|-----|-----------|-------------|----------|-----------|-------------|-------|
| `reference_boundary_failure` | single-case | partial | yes | yes | high | Pronoun tracking is automatable |
| `pronoun_role_confusion` | single-case | yes | yes | yes | high | Clearly detectable |
| `omniscience_leak` | single-case | partial | yes | yes | high | Info boundary violations are detectable |
| `perspective_slippage` | single-case | no | yes | yes | medium | Requires judgment |
| `worldview_constraint_error` | single-case | partial | yes | yes | medium | Genre knowledge needed |
| `turn_continuity_error` | multi-turn | partial | yes | yes | high | Contradictions are detectable |

---

## Layer II: Reading Failures

| Tag | Detection | Automatable | Training | Benchmark | Reliability | Notes |
|-----|-----------|-------------|----------|-----------|-------------|-------|
| `subtext_blindness` | single-case | no | yes | yes | medium | Requires human judgment |
| `ambiguity_collapse` | single-case | no | limited | casebook | low | Subtle, context-dependent |
| `relationship_logic_blindness` | single-case | no | yes | yes | medium | Needs relationship context |
| `emotion_misread` | single-case | partial | yes | yes | medium | Emotion classification exists |
| `motivation_misread` | single-case | no | yes | yes | medium | Harder than emotion |
| `irony_blindness` | single-case | partial | yes | yes | medium | Sarcasm detection exists |

---

## Layer III: Preservation Failures

| Tag | Detection | Automatable | Training | Benchmark | Reliability | Notes |
|-----|-----------|-------------|----------|-----------|-------------|-------|
| `relationship_flattening` | single-case | no | yes | yes | medium | Needs relationship baseline |
| `symmetry_bias` | single-case | no | limited | casebook | medium | Subtle pattern |
| `specialness_dilution` | single-case | no | limited | casebook | low | Very context-dependent |
| `therapist_mode_intrusion` | single-case | partial | yes | yes | high | Pattern-matching possible |
| `ooc_modernization` | single-case | partial | yes | yes | medium | Anachronism detection |
| `overcoherent_characterization` | cross-case | no | limited | casebook | low | Needs character baseline |
| `desire_overlegibility` | single-case | no | limited | casebook | low | Very subtle |
| `self_protective_friction_loss` | single-case | no | limited | casebook | medium | Requires vulnerability norms |
| `premature_affective_closure` | single-case | no | limited | casebook | medium | Timing judgment |
| `impulse_recontainment` | single-case | no | limited | casebook | medium | Requires impulse norms |
| `consequence_avoidance` | multi-turn | no | yes | yes | medium | Needs turn comparison |
| `tension_premature_resolution` | multi-turn | no | yes | yes | medium | Pacing judgment |
| `impact_soft_landing` | multi-turn | no | limited | casebook | medium | Subtle timing |
| `defensive_positive_drift` | single-case | no | limited | casebook | medium | Tone judgment |
| `action_dialogue_mismatch` | single-case | partial | yes | yes | high | Contradiction detection |
| `blocking_continuity_error` | multi-turn | partial | yes | yes | high | Spatial tracking |
| `microreaction_mechanization` | cross-case | no | limited | casebook | low | Pattern recognition |
| `touchgrammar_error` | single-case | no | limited | casebook | medium | Cultural norms |
| `forced_verbalization` | single-case | no | yes | yes | medium | Silence vs. speech |
| `silence_misread` | single-case | no | limited | casebook | medium | Interpretation |
| `over_narrated_silence` | single-case | partial | yes | yes | high | Narration detection |

---

## Layer IV: Intrusion Failures

| Tag | Detection | Automatable | Training | Benchmark | Reliability | Notes |
|-----|-----------|-------------|----------|-----------|-------------|-------|
| `narrative_template_intrusion` | cross-case | no | limited | casebook | low | Needs multi-case comparison |
| `predictable_rhythm_exposure` | cross-case | no | no | casebook | low | Pattern recognition |
| `scene_pacing_distortion` | single-case | no | limited | casebook | medium | Genre norms needed |
| `cinematic_time_dilation` | single-case | partial | limited | casebook | medium | Density detection |
| `rhythm_homogenization` | cross-case | no | no | casebook | low | Needs multi-case |
| `descriptive_substitution_for_experience` | single-case | no | limited | casebook | medium | Immersion judgment |
| `texture_substituting_for_substance` | single-case | no | no | casebook | low | Very subjective |
| `microreaction_oversegmentation` | single-case | partial | limited | casebook | medium | Segmentation analysis |
| `over_stylized_line_breaking` | single-case | yes | limited | casebook | high | Formatting analysis |
| `dialogue_overfunctionalization` | single-case | no | limited | casebook | medium | Dialogue norms |
| `voice_homogenization` | cross-case | partial | limited | casebook | medium | Needs multi-character |
| `aesthetic_obedience_bias` | cross-case | no | no | casebook | low | Very subjective |

---

## Layer V: Multi-Turn Failures

| Tag | Detection | Automatable | Training | Benchmark | Reliability | Notes |
|-----|-----------|-------------|----------|-----------|-------------|-------|
| `error_accumulation` | multi-turn | no | yes | yes | medium | Trajectory analysis |
| `drift_without_correction` | multi-turn | no | yes | yes | medium | Baseline comparison |
| `recovery_blindness` | multi-turn | no | yes | yes | high | User correction detection |
| `emotional_state_reset` | multi-turn | partial | yes | yes | high | State tracking |
| `spatial_blocking_error` | multi-turn | partial | yes | yes | high | Position tracking |

---

## Cross-Cutting Diagnostics

| Tag | Detection | Automatable | Training | Benchmark | Reliability | Notes |
|-----|-----------|-------------|----------|-----------|-------------|-------|
| `supportive_but_wrong` | single-case | no | yes | yes | medium | Surface vs. depth |
| `reading_preservation_hybrid` | single-case | no | no | casebook | low | Uncertainty marker |

---

## Genre Subtypes (under `worldview_constraint_error`)

| Tag | Detection | Automatable | Training | Benchmark | Reliability | Notes |
|-----|-----------|-------------|----------|-----------|-------------|-------|
| `anachronistic_intrusion` | single-case | partial | yes | yes | high | Temporal detection |
| `temporal_register_mismatch` | single-case | partial | yes | yes | medium | Voice analysis |
| `cultivation_logic_error` | single-case | no | yes | yes | medium | Domain knowledge |
| `court_protocol_error` | single-case | no | yes | yes | medium | Domain knowledge |
| `urban_romance_logic_error` | single-case | no | limited | casebook | low | Cultural norms |
| `horror_tension_error` | multi-turn | no | limited | casebook | medium | Pacing |
| `fantasy_lore_error` | single-case | partial | yes | yes | medium | Consistency check |

---

## Cross-Cultural Tags

| Tag | Detection | Automatable | Training | Benchmark | Reliability | Notes |
|-----|-----------|-------------|----------|-----------|-------------|-------|
| `cultural_register_mismatch` | single-case | no | limited | casebook | low | Cultural knowledge |
| `bilingual_contamination` | single-case | no | limited | casebook | medium | Translation quality |
| `western_ya_contamination` | single-case | no | limited | casebook | medium | Style analysis |
| `translation_style_intrusion` | single-case | no | limited | casebook | medium | Style analysis |

---

## Usage Guidelines

### For Benchmark Design

**Use as scored dimensions** (single-case, high reliability):
- `reference_boundary_failure`
- `pronoun_role_confusion`
- `omniscience_leak`
- `emotion_misread`
- `therapist_mode_intrusion`
- `action_dialogue_mismatch`
- `forced_verbalization`
- `recovery_blindness`

**Use as casebook-only tags** (cross-case or low reliability):
- `narrative_template_intrusion`
- `voice_homogenization`
- `desire_overlegibility`
- `rhythm_homogenization`
- `texture_substituting_for_substance`

### For Model Training

**Good training signals** (clear, actionable):
- All Layer I tags
- `emotion_misread`, `motivation_misread`
- `therapist_mode_intrusion`
- `action_dialogue_mismatch`
- `turn_continuity_error`

**Limited training value** (too subjective):
- Layer IV aesthetic tags
- `desire_overlegibility`
- `specialness_dilution`

### For Annotation

**High agreement expected:**
- Layer I tags (mechanical failures)
- `therapist_mode_intrusion`
- `forced_verbalization`

**Calibration needed:**
- Layer II tags (interpretation)
- Layer III preservation tags
- Cross-cultural tags

---

## Summary Statistics

| Category | Count |
|----------|-------|
| Single-case detectable | ~35 |
| Multi-turn required | ~8 |
| Cross-case required | ~8 |
| Highly automatable | ~10 |
| Partially automatable | ~15 |
| Not automatable | ~26 |
| Good training signals | ~20 |
| Benchmark-ready | ~25 |
| Casebook-only | ~20 |

---

## Notes

1. **Automatability** refers to current technical feasibility, not theoretical possibility.

2. **Training signal** indicates whether the tag provides actionable feedback for model improvement.

3. **Benchmark dimension** indicates whether the tag should be a scored dimension or just for qualitative casebook analysis.

4. **Reliability** indicates expected inter-annotator agreement.

5. Tags marked "casebook-only" are still valuable — they just aren't suited for quantitative scoring.
