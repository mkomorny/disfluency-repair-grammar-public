---
name: disfluency-repair-grammar
description: Generates exhaustive Disfluency & Repair Grammar reports specifying false-start syntax, restart mechanisms, stutter/block behavior, filler particle frequencies per 100 words, turn-latching ms, and self-repair rewrite rules for dialogue generation. Trigger with 'disfluency grammar of', 'speech repair profile for', 'model false starts for', or '/disfluency-grammar'.
disable-model-invocation: true
---

# Disfluency & Repair Grammar

## Purpose & Scope

This skill formalizes the **syntax of human conversational disfluency, self-repair, and hesitation**. Standard AI text generators write sanitized, grammatically polished sentences that sound artificial when spoken aloud. This skill captures the organic imperfections of spontaneous human thought: false starts, mid-clause syntactic re-routing, filler particle densities, abandonment thresholds, and turn-latching tolerances.

This skill owns:
- False-start syntax and sentence abandonment rules
- Self-repair mechanisms: backtrack-and-replace vs. forward elaboration
- Quantitative filler particle densities per 100 words (*"um", "uh", "you know", "like", "listen"*)
- Prolongation and articulatory hesitation mechanics
- Turn-latching latency (ms) and overlap interruption tolerance
- LLM text-rewriting rules that turn pristine prose into authentic human dialogue

This skill does **not** own acoustic vowel qualities of fillers (owned by `temporal-pause-breath-architecture`) or general personality ethics (owned by `speaking-personality-profile`).

---

## Activation Triggers

Activate automatically when:
- User asks for conversational disfluencies, false-start habits, speech repairs, or filler word frequencies (e.g., *"disfluency grammar for [speaker]"*, *"model false starts of [subject]"*).
- User triggers `/disfluency-grammar [subject]`.
- Directing LLMs to write realistic, unpolished dramatic dialogue, podcast scripts, or conversational transcripts.
- Tuning speech synthesis prompts to inject natural syntactic revisions.

---

## Mandatory Report Schema & Structure

### 1. Filler Particle Inventory & Statistical Density
- **Filler Token Density:** Count of filler tokens per 100 words in conversational vs. monitored speech.
- **Lexical Token Distribution (%):** Relative frequency of *"uh"* vs. *"um"* vs. *"you know"* vs. *"like"* vs. *"listen"* vs. *"I mean"*.
- **Syntactic Insertion Rules:** Probability of filler occurring at clause-initial vs. pre-predicate vs. intra-constituent positions.

### 2. False-Start & Sentence Abandonment Architecture
- **False-Start Rate:** Percentage of initiated sentences that undergo mid-utterance abandonment or syntactic restructuring.
- **Restart Mechanisms:** Exact point of interruption (after subject noun, after auxiliary verb, mid-consonant block).
- **Syntactic Abandonment:** Tendency to trail off into an unfinished thought vs. forceful pivoting into a new declarative sentence.

### 3. Self-Repair Taxonomy & Rewrite Rules
- **Backtrack-and-Replace:** Repeating the preceding word with correction (e.g., *"on Thursday—on Friday morning"*).
- **Forward Elaboration:** Inserting parenthetical qualifiers without syntactic deletion.
- **Phonetic Cut-Off:** Presence of glottal stops [ʔ] or abrupt vocal fold clamps terminating the error word.

### 4. Turn-Latching, Latency & Interruption Dynamics
- **Turn-Latching Latency (ms):** Mean gap duration between interlocutor speech end and speaker speech start (negative = overlap; 0–100 ms = rapid latching; > 400 ms = delayed).
- **Interruption Strategy:** Passive retreat upon overlap vs. volume ramping and aggressive topic persistence.

### 5. Dialogue Rewrite Transformation Engine
- Set of concrete regex-like or procedural rewrite rules that take standard written English and transform it into the subject's authentic spoken cadence.

---

## Machine Output Block

```json
{
  "$schema": "https://json-schemas.voice/disfluency-grammar.v1.json",
  "speaker_id": "SPEAKER_ID",
  "filler_statistics": {
    "total_fillers_per_100_words": 5.4,
    "token_distribution": {
      "you_know": 0.38,
      "look": 0.24,
      "uh": 0.20,
      "um": 0.08,
      "listen": 0.10
    },
    "favored_insertion_point": "CLAUSE_INITIAL_OR_PRE_PREDICATE"
  },
  "false_start_metrics": {
    "abandonment_rate_percent": 14.2,
    "glottal_cutoff_frequency": 0.65,
    "mean_words_before_repair": 4.2
  },
  "turn_dynamics_ms": {
    "turn_latching_latency_mean": 65,
    "overlap_tolerance_class": "AGGRESSIVE_PERSISTENCE",
    "volume_boost_on_interruption_db": 3.5
  },
  "rewrite_rules": [
    {
      "trigger": "complex_subordinate_clause",
      "action": "SPLIT_INTO_PARATAXIS",
      "template": "Subject + Verb + Object. And let me tell you, Subject + Verb."
    },
    {
      "trigger": "sentence_start",
      "action": "INSERT_RELATIONAL_HOOK",
      "probability": 0.35,
      "tokens": ["Look,", "Listen,", "You know what?"]
    }
  ]
}
```

---

## Biometric & Personality Crosswalk

| Disfluency Parameter | Core Biometric Section | Personality Profile Section | Synthesis Compiler Target |
| :--- | :--- | :--- | :--- |
| Filler Frequencies | §5 Pause, Phrasing & Timing | §5.2 Fillers, Hesitations & Revisions | LLM Persona Prompt Template |
| Glottal Cut-Off Rate | §1 Glottal Source & Attacks | §5.3 Repair Strategies | SSML `<break>` and Phoneme Clamping |
| Latching Latency (ms) | §5 Speaking Rate & Rhythm | §5.1 Turn-Taking & Overlap Tolerance | Multi-Speaker Latency Offset |
| False-Start Rewrites | §6 Linguistic Characteristics | §2.2 Directness & Honesty | Dialogue Generator Grammar Layer |

---

## Calibration Reference Example: Queens Orator Baseline

- **Favored Discourse Markers:** Heavy predominance of pragmatic imperatives (*"Look"*, *"Listen"*) and relational hooks (*"You know it, I know it"*) serving as cognitive staging platforms rather than passive *"um"* fillers.
- **False-Start Architecture:** 15% false-start frequency where an assertion is launched, arrested by an abrupt glottal clamp after 3–5 words, and restarted with an intensified parenthetical statement.
- **Interruption Behavior:** Turn-latching latency near zero (rapid latching ~40 ms); when interrupted, volume increases by +3 dB while maintaining steady pitch, speaking through interlocutor overlap.

---

## Generation Rules

1. Define concrete numerical frequencies per 100 words for all filler tokens.
2. Provide explicit structural rewrite rules that can be parsed by an LLM prompt engine.
3. Every profile must output the machine-readable `disfluency_grammar.json` block.
