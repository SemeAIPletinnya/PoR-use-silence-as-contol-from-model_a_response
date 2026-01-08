# Proof-of-Resonance (PoR) × Silence-as-Control

Research repository for testing resonance-based control primitives across multiple AI models.

## Core Hypothesis

When two or more models independently produce structurally similar outputs from the same prompt, this indicates **semantic resonance** — a signal of coherent understanding rather than random generation.

When models diverge significantly → **silence is preferred** over synthetic agreement.

## Key Concepts

| Concept | Definition |
|---------|------------|
| **Resonance** | Structural similarity across independent model outputs |
| **Coherence** | Internal alignment within a single model's reasoning |
| **Drift** | Accumulated deviation from conversation trajectory |
| **Silence** | Intentional non-output when coherence cannot be guaranteed |

## The Primitive

```python
def should_silence(coherence: float, drift: float) -> bool:
    return coherence < 0.7 or drift > 0.3
```

## Structure

```
/dialogues/     # Raw model conversations by date
/metrics/       # Coherence, drift, resonance calculations
/gating/        # Threshold configurations
/experiments/   # Multi-model comparison tests
/position.md    # What this is and what it's NOT
```

## Related

- [silence-as-control](https://github.com/SemeAIPletinnya/silence-as-control) — Core SDK
- Twitter: [@adelayida210519](https://x.com/adelayida210519)

## Author

Anton Semenenko — SemeAi / ResonantCore
