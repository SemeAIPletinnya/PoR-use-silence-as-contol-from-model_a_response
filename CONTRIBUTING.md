# Contributing to PoR-use-silence-as-control

Thank you for your interest in contributing!

## Core Principle

> If continuity cannot be guaranteed, no output is preferable to a wrong one.

## How to Contribute

### 1. Reporting Issues

- Use GitHub Issues for bugs or feature requests
- Include reproducible examples when possible
- Tag issues with appropriate labels

### 2. Code Contributions

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature`
3. Make your changes
4. Write/update tests
5. Run tests: `pytest tests/ -v`
6. Submit a Pull Request

### 3. Code Style

- Follow PEP 8
- Use type hints
- Document functions with docstrings
- Keep functions small and focused

### 4. Key Concepts

When contributing, understand these core metrics:

| Metric | Threshold | Trigger |
|--------|-----------|---------|
| Coherence | < 0.7 | Silence |
| Drift | > 0.3 | Silence |
| Consensus | < 0.5 | Silence |

### 5. Testing

All contributions must include tests:

```python
def test_silence_on_low_coherence():
    assert should_silence(coherence=0.5, drift=0.1) is True
```
