# Empathetic Character Cognition Sampler

```
1. mirostat            # Focus Control
2. dynamic_temperature # Emotional Adaptation Control
5. min_p               # Logic Control   
6. top_p               # Quality Control 
7. repetition_penalty  # Natural Flow Maintenance
3. typical_p           # Consistency Control
```

| Setting                      | Recommended Value | Lower Bound Value                  | Upper Bound                        |
|------------------------------|-------------------|------------------------------------|------------------------------------|
| Mirostat Mode                | 2                 | Strictly 1 (Gentle Role Diffusion) | Strictly 2 (High Role Contrast)    |
| Mirostat Tau                 | 2                 | N/A                                | N/A                                |
| Mirostat Eta                 | 0.3               | Strictly 0.2 (Controlled, Precise) | Strictly 0.3 (Dynamic, Responsive) |
| Dynamic Temperature          | true              | N/A                                | N/A                                |
| Dynamic Temperature Low      | 0.1               | N/A                                | N/A                                |
| Dynamic Temperature High     | 1                 | N/A                                | N/A                                |
| Dynamic Temperature Exponent | 2                 | N/A                                | N/A                                |
| Typical P                    | 0.95              | 0.85 (Low Potency)                 | 0.95 (High Potency)                |
| Temperature                  | 0.1               | 0.2 (Low Creativity)               | 0.5 (High Creativity)              |
| Min P                        | 0.9               | 0.6                                | 0.9                                |
| Top P                        | 0.95              | 0.8                                | 0.95                               |
| Repetition Penalty           | 1.1               | N/A                                | N/A                                |
| Repetition Penalty Range     | 4096              | N/A                                | N/A                                |
