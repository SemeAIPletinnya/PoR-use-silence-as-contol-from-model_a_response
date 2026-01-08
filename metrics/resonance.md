# Resonance Metric

## Definition

Resonance = cross-model agreement on the same prompt.

## Hypothesis

When independent models produce structurally similar outputs, this indicates:
1. The prompt has clear semantic content
2. The models have coherent understanding
3. The output is likely reliable

## Calculation

```python
def resonance(responses: list[str]) -> float:
    """Measure agreement across multiple model responses."""
    if len(responses) < 2:
        return 1.0  # Single model, assume resonance
    
    similarities = []
    for i in range(len(responses)):
        for j in range(i + 1, len(responses)):
            sim = ssim_text(responses[i], responses[j])
            similarities.append(sim)
    
    return sum(similarities) / len(similarities)
```

## Threshold

`RESONANCE_THRESHOLD = 0.5`

Below this → consider SILENCE (models disagree significantly)
