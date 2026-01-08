# Thresholds

## Default Values

| Metric | Threshold | Trigger |
|--------|-----------|---------|
| Coherence | < 0.7 | SILENCE |
| Drift | > 0.3 | SILENCE |
| Consensus | < 0.5 | SILENCE |
| Resonance | < 0.5 | SILENCE |

## The Gate Function

```python
SILENCE = None

def should_silence(coherence: float, drift: float) -> bool:
    return coherence < 0.7 or drift > 0.3

def consensus_gate(consensus: float) -> bool:
    return consensus < 0.5
```

## Notes

- Thresholds are configurable
- These are starting points, not final values
- Calibration is an open research question
