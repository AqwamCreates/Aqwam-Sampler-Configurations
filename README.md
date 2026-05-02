# Aqwam Sampler Configurations

## Full-Stack Samplers

| Sampler Name                                                                  | Property                                                                                                                                                                       |
|-------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Universal Character Cognition](Universal-Character-Cognition-Sampler.md)     | Prompt Adherence Engine. Converts character prompts into a statistical prison that forces the model to conform strictly to the archetype, lore, and voice defined in the text. |
| [Interactive Character Cognition](Interactive-Character-Cognition-Sampler.md) | Reality Simulation Engine. Converts character prompts into dynamic agents that prioritizes physical logic, cause-and-effect, and spontaneous reaction over rigid archetypes.   |
| [Storyline Character Cognition](Storyline-Character-Cognition-Sampler.md)     | Storyline Engine. Converts character prompts into dynamic agents that turns everything into a storyline.                                                                       |
| [Empathetic Character Cognition](Empathetic-Character-Cognition-Sampler.md)   | Empathy Engine. Converts character prompts into dynamic agents that connects with you as a person by reading your subtexts and actions.                                        |
| [Kinetic Character Cognition](Kinetic-Character-Cognition-Sampler.md)         | High-Velocity Response Engine And Quantization Shield. Converts character prompts into extremely reactive agents that are resistant to quantizations.                          |

## Sampler Modules

### Quantization Denoiser

```
1. mirostat            # Focus Control
2. dynamic_temperature # Restoration Control
```

| Setting                      | Recommended Value | Lower Bound Value                  | Upper Bound Value                  |
|------------------------------|-------------------|------------------------------------|------------------------------------|
| Mirostat Mode                | 2                 | Strictly 1 (Gentle Role Diffusion) | Strictly 2 (High Role Contrast)    |
| Mirostat Tau                 | 2                 | N/A                                | N/A                                |
| Mirostat Eta                 | 0.3               | Strictly 0.2 (Controlled, Precise) | Strictly 0.3 (Dynamic, Responsive) |
| Dynamic Temperature          | true              | N/A                                | N/A                                |
| Dynamic Temperature Low      | 0.1               | N/A                                | N/A                                |
| Dynamic Temperature High     | 1                 | N/A                                | N/A                                |
| Dynamic Temperature Exponent | 2                 | N/A                                | N/A                                |

### Logic Enforcer

```
1. min_p               # Logic Control   
2. top_p               # Quality Control
```

| Setting                      | Recommended Value | Lower Bound Value                  | Upper Bound Value                  |
|------------------------------|-------------------|------------------------------------|------------------------------------|
| Min P                        | 0.9               | 0.6                                | 0.9                                |
| Top P                        | 0.9               | 0.25 (<=Q3)                        | 0.95 (>=Q4)                        |

### Consistency Controller

```
1. typical_p           # Consistency Control  
```

| Setting                      | Recommended Value | Lower Bound Value                  | Upper Bound Value                  |
|------------------------------|-------------------|------------------------------------|------------------------------------|
| Typical P                    | 0.95              | 0.85 (Low Control)                 | 0.95 (High Control)                |

## Samplers

* min_p: The tokens are only selected if it is above p% probability of the top probability token.

* top_p: The cumulative probability resulting from addition of individual token's probability (from highest to lowest) are used for selecting tokens, provided that it is under the p% cumulative probability threshold. 
