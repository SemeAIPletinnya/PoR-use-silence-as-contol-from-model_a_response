# Dynamic Thresholds

## Concept

Thresholds may need to adapt based on:
1. Context length
2. Task complexity
3. User tolerance for silence

## Context-Adaptive

```python
def dynamic_coherence_threshold(context_length: int) -> float:
    """Stricter thresholds for longer contexts."""
    base = 0.7
    decay = 0.005
    return min(base + decay * context_length, 0.95)
```

## Task-Based Profiles

| Task Type | Coherence | Drift | Notes |
|-----------|-----------|-------|-------|
| Creative | 0.5 | 0.5 | More tolerance |
| Factual | 0.8 | 0.2 | Less tolerance |
| Safety-critical | 0.9 | 0.1 | Very strict |
