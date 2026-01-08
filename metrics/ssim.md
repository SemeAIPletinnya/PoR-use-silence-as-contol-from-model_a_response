# Structural Similarity Index (SSIM) for Text

## Concept

Borrowed from image processing — measures structural similarity between two outputs.

## Adapted for Text

```python
def ssim_text(response_a: str, response_b: str) -> float:
    """Structural similarity between two model responses."""
    # Extract structural features
    structure_a = extract_structure(response_a)  # headings, lists, paragraphs
    structure_b = extract_structure(response_b)
    
    # Compare structures
    return jaccard_similarity(structure_a, structure_b)
```

## Resonance Interpretation

- SSIM > 0.7 → High resonance (models agree structurally)
- SSIM < 0.3 → Low resonance (models diverge)
- SSIM 0.3-0.7 → Uncertain
