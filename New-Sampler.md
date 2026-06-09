

```
typical_p = 0.9  # strong but not absolute
min_p = 0.05      # very weak filter, just remove nonsense
temperature = 0.55 # slight randomness
top_p = 0.95      # almost all tokens
dry (with multiplier 0.3-0.5)  # better than rep_pen
mirostat with tau=3, eta=0.2  # gentle coherence
repeat_penalty = 1.1
```
