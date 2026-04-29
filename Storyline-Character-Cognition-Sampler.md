# Storyline Character Cognition Sampler

> A Narrative-First Generation System For Cinematic Flow
> Functionally Equivalent To A Movie Director Guiding The Scene
> Abbreviated As SCC Sampler

## What This Sampler Stack Can Do

*   **Cinematic Pacing:** Smooths out awkward conversational gaps to create a continuous, flowing narrative.
*   **Character Agency:** Characters actively drive the plot forward with purposeful actions rather than passive reactions.
*   **Atmospheric Depth:** Prioritizes sensory details (scents, lighting, subtle gestures) that enhance the mood of the scene.
*   **Idealized Realism:** Balances physical logic with "movie magic" grace (characters move fluidly, dialogue is witty/timed perfectly).
*   **Narrative Arc:** Ensures every response contributes to a larger story beat rather than just answering the immediate prompt.

## The Core Discovery

We found that combining a **High Logic Floor (`min_p: 0.7`)** with a **Moderate Typicality (`typical_p: 0.85`)** and **Low Perplexity Target (`mirostat_tau: 2`)** creates a "Seductive Logic."
*   The `min_p` prevents hallucinations (no lap sitting unless walked over).
*   The `typical_p` allows the character to follow their archetype smoothly (no awkward hesitation).
*   The `tau: 2` keeps the tone calm, deliberate, and unshakeable.

## MCC Sampler Stack

These samplers are stacked in this specific order to prioritize logic before creativity.

```
1. typical_p             # Prompt Control
2. mirostat              # Pace Control
3. temperature           # Heat Control
4. min_p                 # Logic Control
5. top_p                 # Quality Control
6. repetition_penalty    # Natural Flow Maintenance
```

### Quantization-Agnostic Settings

| Setting                  | Recommended Value | Lower Bound Value                  | Upper Bound                        |
|--------------------------|-------------------|------------------------------------|------------------------------------|
| Typical P                | 0.95              | 0.85 (Low Momentum)                | 0.95 (High Momentum)               |
| Mirostat Mode            | 2                 | Strictly 1 (Gentle Role Diffusion) | Strictly 2 (High Role Contrast)    |
| Mirostat Tau             | 2                 | N/A                                | N/A                                |
| Mirostat Eta             | 0.2               | Strictly 0.1 (Controlled, Precise) | Strictly 0.2 (Dynamic, Responsive) |
| Temperature              | 0.65              | 0.2 (High Amplification)           | 0.5 (Low Amplification)            |
| Min P                    | 0.9               | 0.6                                | 0.9                                |
| Top P                    | 0.95              | 0.8                                | 0.95                               |
| Repetition Penalty       | 1.1               | N/A                                | N/A                                |
| Repetition Penalty Range | 4096              | N/A                                | N/A                                |
