# Interactive-Character-Cognition-Sampler

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
| Typical P                | 0.2               | 0.2 (Low Prompt Control)           | 0.3 (High Prompt Control)          |
| Temperature              | 0.4               | 0.2 (High Amplification)           | 0.3 (Low Amplification)            |
| Mirostat Mode            | 2                 | Strictly 1 (Gentle Role Diffusion) | Strictly 2 (High Role Contrast)    |
| Mirostat Tau             | 3                 | N/A                                | N/A                                |
| Mirostat Eta             | 0.2               | Strictly 0.1 (Controlled, Precise) | Strictly 0.2 (Dynamic, Responsive) |
| Repetition Penalty       | 1.1               | N/A                                | N/A                                |
| Repetition Penalty Range | 4096              | N/A                                | N/A                                |
