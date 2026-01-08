# Drift Metric

## Definition

Drift measures accumulated deviation from the conversation trajectory over time.

## Key Property

Drift is **longitudinal** — it compounds across turns.

## Calculation

```python
def drift(context_history: list) -> float:
    """Accumulated semantic distance from starting context."""
    if len(context_history) < 2:
        return 0.0
    
    start = embed(context_history[0])
    current = embed(context_history[-1])
    
    distance = 1 - cosine_similarity(start, current)
    return min(distance, 1.0)
```

## Accumulation Model

```python
drift_t = drift_t-1 + delta(context_t, context_t-1)
```

## Threshold

`DRIFT_THRESHOLD = 0.3`

Above this → SILENCE
