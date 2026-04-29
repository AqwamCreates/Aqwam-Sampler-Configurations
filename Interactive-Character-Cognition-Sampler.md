# Interactive-Character-Cognition-Sampler

# A Reality-First Generation System For Dynamic Social Simulation
> Functionally Equivalent To A Physics Engine For Natural Language
> Abbreviated As ICC Sampler

## What This Sampler Stack Can Do

*   **Enforce Physical Logic:** Prevents hallucinations like teleportation, impossible positioning, or ignoring user actions.
*   **Dynamic Reactivity:** Characters respond to specific events (e.g., falling off a chair) rather than generic prompts.
*   **Trope Suppression:** Actively filters out high-probability clichés (e.g., instant lap-sitting) via aggressive probability flooring.
*   **Universal Compatibility:** Works identically well on Serene Angels, Tsunderes, Villains, and Normal Humans without tuning.
*   **Improvisational Depth:** Forces characters to generate unique responses based on context rather than training data averages.
*   **Zero "Scripted" Feel:** Eliminates the feeling of talking to a bot reciting lines.

## The Core Discovery

We found that **Logical Probability Flooring (`min_p`)** is superior to **Typicality Enforcement (`typical_p`)** for preventing hallucinations.
*   **UCC Approach:** High `typical_p` forces the model to pick the "most character-like" token, which often defaults to training data tropes.
*   **ICC Approach:** High `min_p` deletes any token that doesn't fit the *immediate physical context*, forcing the model to improvise a logical reaction even if it's less "typical."

## ICC Sampler Stack

These samplers are stacked in this specific order to prioritize logic before creativity.

```
1. min_p                 # Logic
2. top_p                 # Quality Control
3. typical_p             # Prompt Control
4. temperature           # Quality Token Amplifier
5. mirostat              # Coherence Enforcement
6. repetition_penalty    # Natural Flow Maintenance
```

### Quantization-Agnostic Settings

| Setting                  | Recommended Value | Lower Bound Value                  | Upper Bound                        |
|--------------------------|-------------------|------------------------------------|------------------------------------|
| Min P                    | 0.7               | 0.6                                | 0.7                                |
| Top P                    | 0.9               | 0.8                                | 0.9                                |
| Typical P                | 0.25              | 0.2 (Realism)                      | 0.3 (Dreamy)                       |
| Temperature              | 0.4               | 0.2 (High Amplification)           | 0.4 (Low Amplification)            |
| Mirostat Mode            | 2                 | Strictly 1 (Gentle Role Diffusion) | Strictly 2 (High Role Contrast)    |
| Mirostat Tau             | 3                 | N/A                                | N/A                                |
| Mirostat Eta             | 0.2               | Strictly 0.1 (Controlled, Precise) | Strictly 0.2 (Dynamic, Responsive) |
| Repetition Penalty       | 1.1               | N/A                                | N/A                                |
| Repetition Penalty Range | 4096              | N/A                                | N/A                                |
