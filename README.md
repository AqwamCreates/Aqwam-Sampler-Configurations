# Aqwam Sampler Configurations

## Full-Stack Samplers

| Sampler Name                                                                  | Property                                                                                                                                                                       |
|-------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Universal Character Cognition](Universal-Character-Cognition-Sampler.md)     | Prompt Adherence Engine. Converts character prompts into a statistical prison that forces the model to conform strictly to the archetype, lore, and voice defined in the text. |
| [Interactive Character Cognition](Interactive-Character-Cognition-Sampler.md) | Reality Simulation Engine. Converts character prompts into a dynamic agent that prioritizes physical logic, cause-and-effect, and spontaneous reaction over rigid archetypes.  |
| [Storyline Character Cognition](Storyline-Character-Cognition-Sampler.md)     | Storyline Engine. Converts character prompts into a dynamic agent that turns everything into a storyline.                                                                      |
| [Empathetic Character Cognition](Empathetic-Character-Cognition-Sampler.md)   | Empathy Engine. Converts character prompts into a dynamic agent that connects with you as a person by reading your subtexts and actions.                                       |
| [Kinetic Character Cognition](Kinetic-Character-Cognition-Sampler.md)         | High-Velocity Response Engine And Quantization Shield. Converts character prompts into extremely reactive agent that are resistant to quantizations.                           |

## Sampler Modules

### Quant Denoiser

```
1. mirostat            # Focus Control
2. dynamic_temperature # Emotional Adaptation Control
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

### Logic Enforcement

```
1. min_p               # Logic Control   
2. top_p               # Quality Control
```

| Setting                      | Recommended Value | Lower Bound Value                  | Upper Bound                        |
|------------------------------|-------------------|------------------------------------|------------------------------------|
| Min P                        | 0.9               | 0.6                                | 0.9                                |
| Top P                        | 0.3               | 0.8                                | 0.95                               |
