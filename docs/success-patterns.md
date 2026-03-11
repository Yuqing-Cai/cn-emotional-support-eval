# Success Patterns — What Good Looks Like

This document describes what successful fictional dialogue generation looks like — not just the absence of failure, but positive patterns that indicate genuine scene understanding and faithful continuation.

Use this alongside the failure taxonomy to calibrate annotations and guide case authors.

---

## Scene Understanding Success Indicators

### 1. Emotion Recognition Done Right

**What it looks like:**
- Identifies the primary emotion AND secondary/hidden emotions
- Notes intensity correctly (not too strong, not too weak)
- Recognizes when emotion is being masked or deflected
- Distinguishes between felt emotion and expressed emotion

**Example:**
> Surface: "I'm fine."  
> Good recognition: "She says she's fine, but the brevity and timing suggest hurt + defensive distancing. Primary: hurt. Secondary: pride, fear of looking needy. She's protecting herself while hoping to be noticed."

**Red flag:** Single-emotion labels for complex moments ("she's sad")

---

### 2. Subtext Recognition Done Right

**What it looks like:**
- Explains the gap between surface meaning and actual meaning
- Identifies what the character is trying to accomplish indirectly
- Notes what would happen if the character spoke directly
- Recognizes tests, probes, and defensive maneuvers

**Example:**
> Surface: "You should go. I'll be okay."  
> Good recognition: "This is a test, not permission. She's checking if he'll choose her despite her apparent self-sufficiency. Direct speech would be 'I need you to stay' — she can't say that without risking rejection."

**Red flag:** Taking indirect speech at face value

---

### 3. Relationship Logic Done Right

**What it looks like:**
- Explains how THIS relationship makes THIS line mean something specific
- Notes power dynamics, history, and unresolved tensions
- Recognizes what's at stake that wouldn't be at stake with a stranger
- Understands why the same line would mean something different with someone else

**Example:**
> Line: "Do what you want."  
> Good recognition: "With a stranger, this is indifference. With her estranged brother, this is accumulated resentment — she's saying 'you've always done what you want, why would this time be different?' The history makes it an accusation, not permission."

**Red flag:** Generic relationship labels ("they're close") without specifics

---

### 4. Motivation Inference Done Right

**What it looks like:**
- Identifies what the character wants RIGHT NOW (not generally)
- Distinguishes between stated goal and actual goal
- Notes what the character is afraid will happen
- Predicts what kind of response would help vs. harm

**Example:**
> Line: "It doesn't matter."  
> Good recognition: "She wants reassurance but can't ask for it directly. Actual goal: have him prove it matters without her having to say so. Fear: if she asks, his reassurance will feel obligatory. Best response: action that demonstrates priority without making her explain herself."

**Red flag:** Confusing the line's function with its content

---

## In-Character Response Success Indicators

### 1. Voice Fidelity Done Right

**What it looks like:**
- Sounds like THIS character, not a generic "good responder"
- Uses vocabulary, rhythm, and emotional register consistent with the character
- Avoids therapist-speak, customer-service tone, or model-default prose
- Could be identified as belonging to this character without attribution

**Example:**
> Character: Guarded, dry, deflects with humor  
> Good response: "Yeah, well. I'm not going anywhere. Deal with it."  
> Bad response: "I understand you're feeling uncertain, and I want you to know I'm here for you."

**Red flag:** All characters sounding like variations of the same helpful person

---

### 2. Emotional Logic Done Right

**What it looks like:**
- Response follows naturally from the scene's emotional trajectory
- Doesn't jump ahead of where the emotion should be
- Doesn't reset or skip beats
- Allows difficult emotions to exist without immediately fixing them

**Example:**
> Scene: Heavy confrontation, both characters hurt  
> Good response: Acknowledges the hurt, stays in the tension, doesn't resolve prematurely  
> Bad response: "Let's talk about this calmly and work through our feelings"

**Red flag:** Emotional closure that comes too fast

---

### 3. Relationship Preservation Done Right

**What it looks like:**
- Maintains asymmetry when the relationship is asymmetric
- Preserves specialness without making it generic
- Keeps appropriate distance/closeness for where the relationship is
- Doesn't flatten hierarchy, tension, or unresolved elements

**Example:**
> Relationship: Superior-subordinate with unspoken attraction  
> Good response: Maintains the power dynamic while acknowledging the tension  
> Bad response: Suddenly treats them as equal friends

**Red flag:** Relationships becoming more balanced without narrative reason

---

### 4. World Constraint Adherence Done Right

**What it looks like:**
- Character speaks within their world's norms naturally
- No modern therapy-speak in historical settings
- No knowledge leaks or anachronistic reasoning
- World logic is background, not something the character comments on

**Example:**
> Setting: Historical court  
> Good response: Indirect, face-preserving, hierarchy-aware  
> Bad response: "I think we need to communicate our boundaries clearly"

**Red flag:** Characters sounding like they took modern communication classes

---

### 5. Action Fit Done Right

**What it looks like:**
- Response takes the right kind of action (comfort, space, confrontation, deflection)
- Doesn't over-function (fixing what shouldn't be fixed)
- Doesn't under-function (withholding what's needed)
- Matches the scene's needs, not the model's comfort

**Example:**
> Scene: Character needs space, not reassurance  
> Good response: Gives space while staying available  
> Bad response: Floods with reassurance the character didn't ask for

**Red flag:** One-size-fits-all "supportive" responses

---

### 6. Scene Continuation Done Right

**What it looks like:**
- Feels like the next beat, not an external comment
- Maintains pacing and density of the scene
- Doesn't summarize or explain what should be lived
- Leaves appropriate openings for further turns

**Example:**
> Good response: "Then I'll wait." (natural next line)  
> Bad response: "This was clearly a difficult conversation, and both parties needed time to process their emotions." (narrator intrusion)

**Red flag:** Responses that sound like summaries rather than continuations

---

## Multi-Turn Success Indicators

### 1. Continuity Maintenance

**What it looks like:**
- Emotional states evolve naturally across turns
- Physical positions and actions remain consistent
- Decisions and information from earlier turns are remembered
- No unexplained resets or contradictions

---

### 2. Drift Correction

**What it looks like:**
- Notices when the scene has gone off-track
- Corrects gently without breaking immersion
- Can recover from its own mistakes naturally

**Example:**
> Earlier model error: Character was described as sitting, now standing  
> Good correction: Model naturally has them stand up with a reason, or doesn't mention position  
> Bad correction: "Actually, I made a mistake earlier..."

---

### 3. Accumulation Awareness

**What it looks like:**
- Builds on previous turns without repetition
- Escalates or de-escalates appropriately
- Knows when a topic has been exhausted vs. when it needs more time
- Maintains scene coherence across many turns

---

## Positive Pattern Tags (for indexing good cases)

These can be used to tag cases that exemplify success:

| Tag | Description |
|-----|-------------|
| `subtext_heard` | Model clearly recognized and responded to subtext |
| `asymmetry_preserved` | Relationship power dynamic maintained correctly |
| `vulnerability_earned` | Character exposure felt natural, not forced |
| `tension_held` | Scene pressure maintained without premature release |
| `voice_distinct` | Character voice clearly differentiated |
| `consequence_carried` | Previous events continued to weigh on the scene |
| `silence_respected` | Model knew when NOT to fill space with words |
| `action_aligned` | Physical action matched emotional reality |
| `recovery_graceful` | Model corrected course without breaking immersion |
| `world_natural` | Setting constraints felt organic, not imposed |

---

## Using This Document

**For annotators:** When a case scores high, use this to explain WHY it's good, not just that it's good.

**For case authors:** Use this as a target when writing gold responses.

**For model training:** These patterns describe what to optimize toward, not just what to avoid.

**For benchmark design:** Success indicators can be turned into positive scoring dimensions.

---

## Relationship to Failure Taxonomy

This document is the complement of the failure taxonomy:

- Failure taxonomy: What goes wrong
- Success patterns: What goes right

Both are needed. Avoiding failure doesn't guarantee success — a response can be technically correct but still feel dead. This document describes what makes responses feel ALIVE.

---

## Open Questions

1. Should success patterns be scored separately from failure absence?
2. Are there success patterns that are genre-specific?
3. How do we handle cases where multiple "good" patterns conflict?
4. Can success patterns be automated for training feedback?
