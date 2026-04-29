# Momentum-Character-Cognition-Sampler

> A Dynamic Flow System For Natural Narrative Progression
> Functionally Equivalent To A River Current For Storytelling
> Abbreviated As MCC Sampler

## What This Sampler Stack Can Do

*   **Natural Pacing:** Creates a sense of gradual build-up rather than instant jumps or static responses.
*   **Grounded Persuasion:** Characters actively pursue goals (romance, comfort, argument) without breaking physical logic.
*   **Smooth Transitions:** Eliminates the "stiffness" of strict logic filters while preventing the "teleportation" of high-entropy models.
*   **Idealized Archetypes:** Perfect for characters who are meant to be serene, seductive, confident, or smoothly manipulative.
*   **Balanced Agency:** The character drives the scene forward, but respects the user's physical boundaries.

## The Core Discovery

We found that combining a **High Logic Floor (`min_p: 0.7`)** with a **Moderate Typicality (`typical_p: 0.85`)** and **Low Perplexity Target (`mirostat_tau: 2`)** creates a "Seductive Logic."
*   The `min_p` prevents hallucinations (no lap sitting unless walked over).
*   The `typical_p` allows the character to follow their archetype smoothly (no awkward hesitation).
*   The `tau: 2` keeps the tone calm, deliberate, and unshakeable.

## MCC Sampler Stack

These samplers are stacked in this specific order to prioritize logic before creativity.

```
1. typical_p             # Prompt Control
2. mirostat              # Coherence Enforcement
3. temperature           # Quality Token Amplifier
4. min_p                 # Logic
5. top_p                 # Quality Control
6. repetition_penalty    # Natural Flow Maintenance
```

### Quantization-Agnostic Settings

| Setting                  | Recommended Value | Lower Bound Value                  | Upper Bound                        |
|--------------------------|-------------------|------------------------------------|------------------------------------|
| Typical P                | 0.85              | 0.85 (Low Momentum)                | 0.9 (High Momentum)                |
| Mirostat Mode            | 2                 | Strictly 1 (Gentle Role Diffusion) | Strictly 2 (High Role Contrast)    |
| Mirostat Tau             | 2                 | N/A                                | N/A                                |
| Mirostat Eta             | 0.2               | Strictly 0.1 (Controlled, Precise) | Strictly 0.2 (Dynamic, Responsive) |
| Temperature              | 0.65              | 0.2 (High Amplification)           | 0.5 (Low Amplification)            |
| Min P                    | 0.7               | 0.6                                | 0.7                                |
| Top P                    | 0.95              | 0.8                                | 0.95                               |
| Repetition Penalty       | 1.1               | N/A                                | N/A                                |
| Repetition Penalty Range | 4096              | N/A                                | N/A                                |
