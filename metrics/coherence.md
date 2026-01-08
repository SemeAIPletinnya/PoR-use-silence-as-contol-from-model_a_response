# Coherence Metric

## Definition

Coherence measures internal alignment within a single response.

## Calculation Methods

### 1. Embedding Similarity
```python
def coherence_embedding(context: list, response: str) -> float:
    """Cosine similarity between context centroid and response."""
    context_emb = embed(context)
    response_emb = embed(response)
    return cosine_similarity(context_emb, response_emb)
```

### 2. Self-Consistency
```python
def coherence_consistency(model, prompt, n=5) -> float:
    """Agreement across multiple samples."""
    responses = [model(prompt) for _ in range(n)]
    unique = len(set(responses))
    return 1.0 / unique
```

### 3. Entropy-Based
```python
def coherence_entropy(token_probs: list) -> float:
    """Low entropy = high confidence = high coherence."""
    entropy = -sum(p * log(p) for p in token_probs)
    return 1.0 - normalize(entropy)
```

## Threshold

`COHERENCE_THRESHOLD = 0.7`

Below this → SILENCE
